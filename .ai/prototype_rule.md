# CMS Tenant Component Catalog and Prototype Rules

Use this guide when creating a new CMS prototype in
`cms-tenant/src/components`. Match the existing application’s UI composition
and reuse its components before introducing a new one.

## Component layout

```text
common/              reusable UI primitives
shared-components/   reusable business UI
<feature>/           domain-specific screens and parts
  index / *Container  screen composition
  Filter*             search area
  *Table              result table
  *Modal / Form / New create, edit, detail, or confirmation UI
```

For a prototype, use mock props and mock data if needed. Do not add routes,
Redux state, API calls, permissions, or database changes unless requested.

## Reuse these components first

| UI need | Existing component |
| --- | --- |
| Standard content section | `common/CardCommon.tsx` |
| Primary, secondary, and loading button | `common/RsButton.tsx` |
| Text, textarea, and number fields | `common/AtndInput.tsx` (`AtndInputAreaCommon`, `AntdInputNumber`) |
| Select controls | `common/AtndSelect.tsx`, `common/SelectCommon.tsx` |
| Tenant / business-industry selector | `common/TenantCodeSelect.tsx`, `common/SelectBusinessIndustry.tsx` |
| Date or date range | `common/DatePickerCommon.tsx`, `DateRangePickerCommon` |
| Confirmation dialog | `common/ConfirmModal.tsx` |
| File upload | `common/UploadButon.tsx` |
| Page title, result header, record count | `common/PageTitle.tsx`, `Result.tsx`, `ResultCountText.tsx` |
| Link, back action, spinner, spacing | `common/TextLink.jsx`, `BackIcon.tsx`, `AtndSpin.tsx`, `Spacer.jsx` |
| Right-aligned actions | `common/index.tsx` (`ButtonEndContainer`) |
| Calculation / password dialogs | `shared-components/CalculateModal.tsx`, `ChangePasswordModal.tsx` |
| Contact table / linked-tenant select | `shared-components/ContactTable.tsx`, `SelectLinkedTenant.tsx` |

## Existing feature references

Use the closest feature as a visual and structural reference.

| Prototype type | Good references |
| --- | --- |
| Search + table + Add | `tenants/all-tenants/*`, `sales-target/*`, `directories/shopping-center/*` |
| Search + operational table + import/edit modals | `utilities/*`, `bank-remittance/*`, `adjustment-correction/*` |
| Create or edit form | `directories/locations/NewEditTenantLocation.tsx`, `directories/shopping-center/NewEditShoppingCenter.tsx`, `tenant-users/CreateEditUser.tsx` |
| Detail with related tables | `tenants/all-tenants/DetailTenantContainer.tsx`, `tenant-daily-sales/tenant-daily-sale-detail/*` |
| Filtered report and detail | `sales-report/*`, `rental-fee-report/*`, `reports/*` |
| Calculation, deduction, or month-end process | `sales-deductions/*`, `monthly-deductions/*`, `return-list/*` |

## Rule: build a responsive list prototype

Most CMS list screens follow this order:

```text
Page title (optional)
Search card
  Desktop: filter fields in a responsive grid; Search / Reset aligned right
  Mobile: one field per row; full-width actions stacked or wrapped

Results card
  Desktop: record count left, Add / Import / Export right
  Mobile: count first, actions wrap beneath it; primary Add remains visible
  Responsive Ant Design table below

Modal or separate form
  Used for create, edit, view detail, or confirmation
```

Use this base composition:

```tsx
<CardCommon>
  <Form layout="vertical">
    <Row gutter={[24, 0]}>
      <Col xs={24} sm={12} lg={8}>
        <Form.Item label="Keyword">
          <AtndInputCommon placeholder="Search..." />
        </Form.Item>
      </Col>
      <Col xs={24} sm={12} lg={8}>
        <Form.Item label="Status">
          <AtndSelectCommon options={statusOptions} />
        </Form.Item>
      </Col>
      <Col xs={24} sm={12} lg={8}>
        <Form.Item label="Date range">
          <DateRangePickerCommon style={{ width: '100%' }} />
        </Form.Item>
      </Col>
    </Row>
    <ButtonEndContainer className="gap-2 flex-wrap">
      <RsButton>Reset</RsButton>
      <RsButton color="primary">Search</RsButton>
    </ButtonEndContainer>
  </Form>
</CardCommon>

<CardCommon>
  <Result>
    <ResultCountText>{mockRows.length}</ResultCountText>
    <ButtonEndContainer className="gap-2 flex-wrap">
      <RsButton>Export</RsButton>
      <RsButton color="primary">Add</RsButton>
    </ButtonEndContainer>
  </Result>
  <Table
    rowKey="id"
    dataSource={mockRows}
    columns={mockColumns}
    scroll={{ x: 'max-content' }}
  />
</CardCommon>
```

## Responsive UI/UX rules

Design and verify each prototype at mobile and desktop widths. Use Ant Design
breakpoints instead of duplicating a mobile-only screen.

| Area | Mobile (`xs`, <576px) | Tablet (`sm`/`md`) | Desktop (`lg`+) |
| --- | --- | --- | --- |
| Page spacing | 12–16px horizontal padding | 20–24px | 24–32px |
| Filter grid | One field per row: `xs={24}` | Two fields where readable: `sm={12}` | Three or four fields: `lg={8}` or `lg={6}` |
| Search actions | Full width or wrapped below fields | Right-aligned and wrapped | Right-aligned in one row |
| Result header | Count above action buttons; buttons wrap | Count/action row may wrap | Count left, actions right |
| Primary action | Keep Add visible; use short labels/icons only when unambiguous | Standard labels | Standard labels |
| Table | Horizontal scroll; prioritise essential columns | Scroll only when needed | Show complete table columns |
| Row action | Use a compact Action column; avoid many inline buttons | Action column or dropdown | Text links/buttons are acceptable |
| Form modal | `width="calc(100% - 32px)"`; body scrolls | `width="80%"` or a sensible fixed width | Use the existing feature’s modal width |

### Table rules

1. Set `scroll={{ x: 'max-content' }}` for a multi-column table so it does not
   compress unreadably on mobile.
2. Show the most important identifier, status, and Action columns first.
3. Use short headers and truncate non-essential long text where appropriate.
4. Do not hide the Add action or the only way to view a record on mobile.

### Form and modal rules

1. Keep one input per row on mobile unless two controls are very short and
   clearly related.
2. Use `Form layout="vertical"` and inputs with `style={{ width: '100%' }}`.
3. Place Cancel and Save in the modal footer; on narrow screens let them wrap
   while keeping Save visually primary.
4. A long create/edit form should be a dedicated screen/component, not an
   oversized modal.

## Prototype rules

1. Start from the closest existing feature; preserve its visual hierarchy and
   naming style.
2. Put filters inside `CardCommon`. Use Ant Design `Form`, `Row`, and `Col`;
   use `xs={24}` and responsive `sm`/`lg` spans.
3. Keep **Search** and **Reset** in the filter card. A search action updates
   visible mock rows; Reset restores the default filter and full mock data.
4. Keep **Add**, **Import**, and **Export** beside the record count, above the
   table. Only show actions relevant to the prototype.
5. Use an Ant Design `Table` with a clear `rowKey`, readable columns, and an
   `Action` column for View/Edit when a detail flow is shown.
6. Use a modal for a short create/edit flow. Use a dedicated form component for
   long forms or forms with related sub-tables.
7. Include prototype states: populated table, no matching results, disabled or
   loading action, confirmation before destructive actions, and a mobile-width
   view.
8. Keep visible production-ready text compatible with `t('...')`.
9. Do not duplicate a shared component just to change labels, colour, or small
   spacing; pass props or compose it instead.
10. Preserve legacy import names: `UploadButon`, `AddVouncerModal`,
    `CreaditDebitInputSection`, and `AllTenents`.

## Suggested prototype file structure

```text
components/<new-feature>/
  index.tsx                  # compose the prototype screen
  Filter<Feature>.tsx        # filter controls and Search/Reset actions
  <Feature>Table.tsx         # columns, mock rows, and table actions
  CreateEdit<Feature>.tsx    # optional modal or form
```

Keep mock rows close to the prototype container or table. Replace them with a
typed API/state layer only when the task explicitly expands into production
implementation.
