<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/202762813/26.2.3%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T807225)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
[![](https://img.shields.io/badge/💬_Leave_Feedback-feecdd?style=flat-square)](#does-this-example-address-your-development-requirementsobjectives)
<!-- default badges end -->

# Blazor Grid — Use Custom Icons as Command Buttons

A [command column](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxGridCommandColumn) displays the following predefined buttons (icons): 

- **New** (column header)
- **Edit**, **Delete** (data rows in display mode)
- **Save**, **Cancel** (data rows in `EditRow` and `EditCell` modes)

You can use [HeaderTemplate](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxGridCommandColumn.HeaderTemplate), [CellDisplayTemplate](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxGridCommandColumn.CellDisplayTemplate), or [CellEditTemplate](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxGridCommandColumn.CellEditTemplate) to change command button appearance within the DevExpress Blazor Grid.

This example uses icons from the [DevExpress Icon Library](https://docs.devexpress.com/Blazor/401749/styling-and-themes/icons#devexpress-icon-library-ctp).

![Grid with Custom Icons](images/grid-command-icons.png)

Handle button/icon click events and call [StartEditNewRowAsync](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxGrid.StartEditNewRowAsync), [StartEditDataItemAsync](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxGrid.StartEditDataItemAsync(System.Object)) and [ShowDataItemDeleteConfirmation](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxGrid.ShowDataItemDeleteConfirmation(System.Object)) methods to implement required functionality. Pass the following parameters:

* A *null* object if you want to create a new record
* An existing object if you edit or delete a record

Use the *context* object to obtain the current row object in the column [CellDisplayTemplate](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxGridCommandColumn.CellDisplayTemplate):

```Razor
<CellDisplayTemplate>
    <div class="cmd-buttons">
        <DxButton IconUrl="@Icons.EditPen.PaletteNeutral" RenderStyle="ButtonRenderStyle.None"  @onclick="@(() => MyGrid.StartEditDataItemAsync(context.DataItem))" />
        <DxButton IconUrl="@Icons.Close.PaletteNeutral" RenderStyle="ButtonRenderStyle.None"  @onclick="@(() => MyGrid.ShowDataItemDeleteConfirmation(context.DataItem))" />
    </div>
</CellDisplayTemplate>
```

## Files to Review

* [Index.razor](./CS/CommandButtonsWithIcons/Pages/Index.razor)

## Documentation

* [Blazor Grid — Command Column](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxGridCommandColumn)
* [Icons in DevExpress Blazor Components](https://docs.devexpress.com/Blazor/401749/styling-and-themes/icons)

## More Examples

* [Blazor Grid — Create a custom record deletion confirmation dialog](https://github.com/DevExpress-Examples/blazor-grid-show-custom-confirmation-dialog)
* [Blazor Grid — Use an External Popup as an Edit Form](https://github.com/DevExpress-Examples/blazor-grid-popup-edit-form-customization)

<!-- feedback -->
## Does This Example Address Your Development Requirements/Objectives?

[<img src="https://www.devexpress.com/support/examples/i/yes-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=blazor-grid-command-buttons-with-custom-icons&~~~was_helpful=yes) [<img src="https://www.devexpress.com/support/examples/i/no-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=blazor-grid-command-buttons-with-custom-icons&~~~was_helpful=no)

(you will be redirected to DevExpress.com to submit your response)
<!-- feedback end -->

