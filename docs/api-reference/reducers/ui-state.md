<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### Table of Contents

-   [uiStateUpdaters][1]
    -   [addNotificationUpdater][3]
    -   [cleanupExportImage][5]
    -   [DEFAULT_EXPORT_DATA][7]
    -   [DEFAULT_EXPORT_IMAGE][9]
    -   [DEFAULT_MAP_CONTROLS][11]
    -   [hideExportDropdownUpdater][13]
    -   [INITIAL_UI_STATE][15]
    -   [openDeleteModalUpdater][17]
    -   [setExportDataTypeUpdater][19]
    -   [setExportDataUpdater][21]
    -   [setExportFilteredUpdater][23]
    -   [setExportImageDataUri][25]
    -   [setExportSelectedDatasetUpdater][27]
    -   [setRatioUpdater][29]
    -   [setResolutionUpdater][31]
    -   [showExportDropdownUpdater][33]
    -   [startExportingImage][35]
    -   [toggleLegendUpdater][37]
    -   [toggleMapControlUpdater][39]
    -   [toggleModalUpdater][41]
    -   [toggleSidePanelUpdater][43]

## uiStateUpdaters

Updaters for `uiState` reducer. Can be used in your root reducer to directly modify kepler.gl's state.
Read more about [Using updaters][45]

**Examples**

```javascript
import keplerGlReducer, {uiStateUpdaters} from 'kepler.gl/reducers';
// Root Reducer
const reducers = combineReducers({
 keplerGl: keplerGlReducer,
 app: appReducer
});

const composedReducer = (state, action) => {
 switch (action.type) {
   // click button to close side panel
   case 'CLICK_BUTTON':
     return {
       ...state,
       keplerGl: {
         ...state.keplerGl,
         foo: {
            ...state.keplerGl.foo,
            uiState: uiStateUpdaters.toggleSidePanelUpdater(
              uiState, {payload: null}
            )
         }
       }
     };
 }
 return reducers(state, action);
};

export default composedReducer;
```

### addNotificationUpdater

Add a notification to be displayed

-   **Action**: [`addNotification`][46]

**Parameters**

-   `state` **[Object][47]** `uiState`
-   `action` **[Object][47]** 
    -   `action.payload` **[Object][47]** 

Returns **[Object][47]** nextState

### cleanupExportImage

Delete cached export image

-   **Action**: [`cleanupExportImage`][48]

**Parameters**

-   `state` **[Object][47]** `uiState`

Returns **[Object][47]** nextState

### DEFAULT_EXPORT_DATA

Default initial `exportData` settings

Type: [Object][47]

#### Properties

-   `selectedDataset` **[string][49]** Default: `''`,
-   `dataType` **[string][49]** Default: `'csv'`,
-   `filtered` **[boolean][50]** Default: `true`,
-   `config` **[boolean][50]** deprecated
-   `data` **[boolean][50]** used in modal config export. Default: `false`

### DEFAULT_EXPORT_IMAGE

Default image export config

Type: [Object][47]

#### Properties

-   `ratio` **[string][49]** Default: `'SCREEN'`,
-   `resolution` **[string][49]** Default: `'ONE_X'`,
-   `legend` **[boolean][50]** Default: `false`,
-   `imageDataUri` **[string][49]** Default: `''`,
-   `exporting` **[boolean][50]** Default: `false`

### DEFAULT_MAP_CONTROLS

A list of map control visibility and whether is it active.

Type: [Object][47]

#### Properties

-   `visibleLayers` **[Object][47]** Default: `{show: true, active: false}`
-   `mapLegend` **[Object][47]** Default: `{show: true, active: false}`
-   `toggle3d` **[Object][47]** Default: `{show: true}`
-   `splitMap` **[Object][47]** Default: `{show: true}`

### hideExportDropdownUpdater

Hide side panel header dropdown, activated by clicking the share link on top of the side panel

-   **Action**: [`hideExportDropdown`][51]

**Parameters**

-   `state` **[Object][47]** `uiState`

Returns **[Object][47]** nextState

### INITIAL_UI_STATE

Default initial `uiState`

Type: [Object][47]

#### Properties

-   `readOnly` **[boolean][50]** Default: `false`
-   `activeSidePanel` **[string][49]** Default: `'layer'`
-   `currentModal` **([string][49] | null)** Default: `'addData'`
-   `datasetKeyToRemove` **([string][49] | null)** Default: `null`
-   `visibleDropdown` **([string][49] | null)** Default: `null`
-   `exportImage` **[Object][47]** Default: [`DEFAULT_EXPORT_IMAGE`][9]
-   `exportData` **[Object][47]** Default: [`DEFAULT_EXPORT_DATA`][7]
-   `mapControls` **[Object][47]** Default: [`DEFAULT_MAP_CONTROLS`][11]

### openDeleteModalUpdater

Toggle active map control panel

-   **Action**: [`openDeleteModal`][52]

**Parameters**

-   `state` **[Object][47]** `uiState`
-   `action` **[Object][47]** 
    -   `action.payload` **[string][49]** dataset id

Returns **[Object][47]** nextState

### setExportDataTypeUpdater

Set data format for exporting data

-   **Action**: [`setExportDataType`][53]

**Parameters**

-   `state` **[Object][47]** `uiState`
-   `action` **[Object][47]** 
    -   `action.payload` **[string][49]** one of `'text/csv'`

Returns **[Object][47]** nextState

### setExportDataUpdater

Whether to including data in map config, toggle between `true` or `false`

-   **Action**: [`setExportData`][54]

**Parameters**

-   `state` **[Object][47]** `uiState`
-   `action`  

Returns **[Object][47]** nextState

### setExportFilteredUpdater

Whether to export filtered data, `true` or `false`

-   **Action**: [`setExportFiltered`][55]

**Parameters**

-   `state` **[Object][47]** `uiState`
-   `action` **[Object][47]** 
    -   `action.payload` **[boolean][50]** 

Returns **[Object][47]** nextState

### setExportImageDataUri

Set `exportImage.setExportImageDataUri` to a image dataUri

-   **Action**: [`setExportImageDataUri`][56]

**Parameters**

-   `state` **[Object][47]** `uiState`
-   `action` **[Object][47]** 
    -   `action.payload` **[string][49]** export image data uri

Returns **[Object][47]** nextState

### setExportSelectedDatasetUpdater

Set selected dataset for export

-   **Action**: [`setExportSelectedDataset`][57]

**Parameters**

-   `state` **[Object][47]** `uiState`
-   `action` **[Object][47]** 
    -   `action.payload` **[string][49]** dataset id

Returns **[Object][47]** nextState

### setRatioUpdater

Set `exportImage.ratio`

-   **Action**: [`setRatio`][58]

**Parameters**

-   `state` **[Object][47]** `uiState`
-   `action` **[Object][47]** 
    -   `action.payload` **[string][49]** one of `'SCREEN'`, `'FOUR_BY_THREE'` and `'SIXTEEN_BY_NINE'`

Returns **[Object][47]** nextState

### setResolutionUpdater

Set `exportImage.resolution`

-   **Action**: [`setResolution`][59]

**Parameters**

-   `state` **[Object][47]** `uiState`
-   `action` **[Object][47]** 
    -   `action.payload` **[string][49]** one of `'ONE_X'`, `'TWO_X'`

Returns **[Object][47]** nextState

### showExportDropdownUpdater

Hide and show side panel header dropdown, activated by clicking the share link on top of the side panel

-   **Action**: [`showExportDropdown`][60]

**Parameters**

-   `state` **[Object][47]** `uiState`
-   `action` **[Object][47]** 
    -   `action.payload` **[string][49]** id of the dropdown

Returns **[Object][47]** nextState

### startExportingImage

Set `exportImage.exporting` to `true`

-   **Action**: [`startExportingImage`][61]

**Parameters**

-   `state` **[Object][47]** `uiState`

Returns **[Object][47]** nextState

### toggleLegendUpdater

Set `exportImage.legend` to `true` or `false`

-   **Action**: [`toggleLegend`][62]

**Parameters**

-   `state` **[Object][47]** `uiState`

Returns **[Object][47]** nextState

### toggleMapControlUpdater

Toggle active map control panel

-   **Action**: [`toggleMapControl`][63]

**Parameters**

-   `state` **[Object][47]** `uiState`
-   `action` **[Object][47]** action
    -   `action.payload` **[string][49]** map control panel id, one of the keys of: [`DEFAULT_MAP_CONTROLS`][11]

Returns **[Object][47]** nextState

### toggleModalUpdater

Show and hide modal dialog

-   **Action**: [`toggleModal`][64]

**Parameters**

-   `state` **[Object][47]** `uiState`
-   `action` **[Object][47]** 
    -   `action.payload` **([string][49] | null)** id of modal to be shown, null to hide modals. One of:-   [`DATA_TABLE_ID`][65]
        -   [`DELETE_DATA_ID`][66]
        -   [`ADD_DATA_ID`][67]
        -   [`EXPORT_IMAGE_ID`][68]
        -   [`EXPORT_DATA_ID`][69]
        -   [`EXPORT_CONFIG_ID`][70]
        -   [`ADD_MAP_STYLE_ID`][71]

Returns **[Object][47]** nextState

### toggleSidePanelUpdater

Toggle active side panel

-   **Action**: [`toggleSidePanel`][72]

**Parameters**

-   `state` **[Object][47]** `uiState`
-   `action` **[Object][47]** 
    -   `action.payload` **([string][49] | null)** id of side panel to be shown, one of `layer`, `filter`, `interaction`, `map`. close side panel if `null`

Returns **[Object][47]** nextState

[1]: #uistateupdaters

[2]: #examples

[3]: #addnotificationupdater

[4]: #parameters

[5]: #cleanupexportimage

[6]: #parameters-1

[7]: #default_export_data

[8]: #properties

[9]: #default_export_image

[10]: #properties-1

[11]: #default_map_controls

[12]: #properties-2

[13]: #hideexportdropdownupdater

[14]: #parameters-2

[15]: #initial_ui_state

[16]: #properties-3

[17]: #opendeletemodalupdater

[18]: #parameters-3

[19]: #setexportdatatypeupdater

[20]: #parameters-4

[21]: #setexportdataupdater

[22]: #parameters-5

[23]: #setexportfilteredupdater

[24]: #parameters-6

[25]: #setexportimagedatauri

[26]: #parameters-7

[27]: #setexportselecteddatasetupdater

[28]: #parameters-8

[29]: #setratioupdater

[30]: #parameters-9

[31]: #setresolutionupdater

[32]: #parameters-10

[33]: #showexportdropdownupdater

[34]: #parameters-11

[35]: #startexportingimage

[36]: #parameters-12

[37]: #togglelegendupdater

[38]: #parameters-13

[39]: #togglemapcontrolupdater

[40]: #parameters-14

[41]: #togglemodalupdater

[42]: #parameters-15

[43]: #togglesidepanelupdater

[44]: #parameters-16

[45]: ../advanced-usage/using-updaters.md

[46]: ../actions/actions.md#addnotification

[47]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object

[48]: ../actions/actions.md#cleanupexportimage

[49]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String

[50]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean

[51]: ../actions/actions.md#hideexportdropdown

[52]: ../actions/actions.md#opendeletemodal

[53]: ../actions/actions.md#setexportdatatype

[54]: ../actions/actions.md#setexportdata

[55]: ../actions/actions.md#setexportfiltered

[56]: ../actions/actions.md#setexportimagedatauri

[57]: ../actions/actions.md#setexportselecteddataset

[58]: ../actions/actions.md#setratio

[59]: ../actions/actions.md#setresolution

[60]: ../actions/actions.md#showexportdropdown

[61]: ../actions/actions.md#startexportingimage

[62]: ../actions/actions.md#togglelegend

[63]: ../actions/actions.md#togglemapcontrol

[64]: ../actions/actions.md#togglemodal

[65]: ../constants/default-settings.md#data_table_id

[66]: ../constants/default-settings.md#delete_data_id

[67]: ../constants/default-settings.md#add_data_id

[68]: ../constants/default-settings.md#export_image_id

[69]: ../constants/default-settings.md#export_data_id

[70]: ../constants/default-settings.md#export_config_id

[71]: ../constants/default-settings.md#add_map_style_id

[72]: ../actions/actions.md#togglesidepanel