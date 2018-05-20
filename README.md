# MultiSelect
A Lightning Multi-Select Picklist.

To use, simply add as part of a form (or without if you'd like):

    <aura:attribute name="selectedValues" type="String[]" />
    <aura:attribute name="options" type="List" default="[
                        {'label': 'Red', 'value': 'Red', 'selected' : false },
                        {'label': 'Green', 'value': 'Green', 'selected' : false },
                        {'label': 'Blue', 'value': 'Blue', 'selected' : false },
                         ]"/>

    <div class="slds-form-element">
        <label class="slds-form-element__label" for="my-multi-select">Label</label>
        <div class="slds-form-element__control">
            <c:MultiSelect options="{!v.options}" selectChange="{!c.handleSelectChangeEvent}" selectedItems="{!v.selectedValues}" />
        </div>
    </div>
    
The multiselect `options` are an array of type `List` and selectedItems is a comma delimited string (`String[]`).

The `handleSelectChangeEvent` method could look like this:

    //changes filter parameters
    handleSelectChangeEvent: function(component, event, helper) {
        var items = component.get("v.items");
        items = event.getParam("values");
        component.set("v.items", items);
    }


What it looks like:

[![Multiselect gif][1]][1]

  [1]: http://i.imgur.com/22RPF0k.gif



