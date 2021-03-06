# Vuetable - Methods

## normalizeFields
- **params:**  _none_
- **usage:**

  Parse `fields` definition to field objects usable by Vuetable. This method is called automatically "once" during 
  the `created` life cycle hook. 

  If you dynamically change the `fields` prop, you will need to manually call `normalizeFields` method to properly 
  parse the `fields` definition as Vuetable will not be able to pickup the change and will not work as expected.

## setData
- **params:** 
  - data: `Array | Object`
- **usage:**

  You can use this method to manually set the data that Vuetable will be used for table rendering instead of requesting data from the server.

  If the `data` parameter is of type Array, Vuetable will use those array as the data to render the table.

  If the `data` parameter is of type Object, it must be conform to the [Data Structure](#) that Vuetable expects (e.g. contains both data and pagination information).  

  > __Note__
  > The method will automatically set `api-mode` to `false`.

## reload
- **params:** _none_
- **usage:**

  Force Vuetable to reload the data from the server using the current value of parameters. However, the page number will not be reset.

## refresh
- **params:** _none_
- **usage:**

  Force Vuetable to reload the data from the server and the page number will be reset to 1. It's the same as using goto-page page event to load page 1.

## resetData
- **params:** _none_
- **usage:**

  This will set `tableData` and `tablePagination` to `null` resulting in not displaying any data in the table (as there is no data to display). This method will also fire `vuetable:data-reset` event which can be captured to force update pagination component accordingly.

## transform
- **params:** 
  - data: `Array`
- must return: `Array`
- **usage:**

  In case, the data returned from the server is not in the format that Vuetable expected, you can define `transform` method on the main Vue instance
  and Vuetable will automatically called it with the data from the server.

  The `transform` method must return the array of data that Vuetable expected.

  See also: Data Format (JSON)

## gotoPreviousPage
- **params:** _none_
- **usage:**

  __** API Mode Only **__

  This method will automatically request the previous page of data from the server.

## gotoNextPage
- **params:** _none_
- **usage:**

  __** API Mode Only **__

  This method will automatically request the next page of data from the server.

## gotoPage
- **params:** 
  - page: `Number`
- **usage:**

  __** API Mode Only **__

  This method will automatically request the specified page of data from the server.

## changePage
- **params:**
  - page: `String`, `Number`
- **usage:**

  __** API Mode Only **__

  This method will automatically request the specified page of data from the server. You can either pass in the page number, or 'prev' string for previous page, or 'next' string for next page.

## isVisibleDetailRow
- **params:** 
  - rowId: `RowIdentifier`
- **usage:**

  Determine if the detail row of the given row identifier is marked as visible.

  See also: [Row Identifier](Row-Identifier)

## showDetailRow
- **params:** 
  - rowId: `RowIdentifier`
- **usage:**

  Force displaying the detail row of the given row.

  See also: [Row Identifier](Row-Identifier)

## hideDetailRow
- **params:** 
  - rowId: `RowIdentifier`
- **usage:**

  Force hiding the detail row of the given row.

  See also: [Row Identifier](Row-Identifier)

## toggleDetailRow
- **params:** 
  - rowId: `RowIdentifier`
- **usage:**

  Toggle the display of the detail row of the given row.

  See also: [Row Identifier](Row-Identifier)

## showField
- **params:** 
  - index: `Number`
- **usage:**

  Force displaying the specified field.

## hideField
- **params:** 
  - index: `Number`
- **usage:**

  Force hiding the specified field.

## toggleField
- **params:** 
  - index: `Number`
- **usage:**

  Toggle display of the specified field.

