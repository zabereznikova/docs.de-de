---
title: Binden einer benutzerdefinierten Aktivitätseigenschaft an ein Designersteuerelement
ms.date: 03/30/2017
ms.assetid: 2e8061ea-10f5-407c-a31f-d0d74ce12f27
ms.openlocfilehash: 142a9eb273a98d3a2d83a1239d6d7c891d5cc305
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468571"
---
# <a name="binding-a-custom-activity-property-to-a-designer-control"></a><span data-ttu-id="f3a22-102">Binden einer benutzerdefinierten Aktivitätseigenschaft an ein Designersteuerelement</span><span class="sxs-lookup"><span data-stu-id="f3a22-102">Binding a custom activity property to a designer control</span></span>

<span data-ttu-id="f3a22-103">Das Binden eines Textfeld-Designersteuerelements an ein Aktivitätsargument ist recht einfach. Das Binden eines komplexes Designersteuerelements (z. B. ein Kombinationsfeld) an ein Aktivitätsargument kann jedoch eine besondere Herausforderung darstellen.</span><span class="sxs-lookup"><span data-stu-id="f3a22-103">Binding a text box designer control to an activity argument is fairly straightforward; binding a complex designer control (such as a combo box) to an activity argument may present challenges, however.</span></span> <span data-ttu-id="f3a22-104">In diesem Thema wird erläutert, wie ein Aktivitätsargument an ein Kombinationsfeld-Steuerelement in einem benutzerdefinierten Aktivitätsdesigner gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="f3a22-104">This topic discusses how to bind an activity argument to a combo box control on a custom activity designer.</span></span>

## <a name="creating-the-combo-box-item-converter"></a><span data-ttu-id="f3a22-105">Erstellen des Kombinationsfeldelement-Konverters</span><span class="sxs-lookup"><span data-stu-id="f3a22-105">Creating the combo box item converter</span></span>

1. <span data-ttu-id="f3a22-106">Erstellen Sie in Visual Studio eine neue leere Projektmappe mit dem Namen "CustomProperty".</span><span class="sxs-lookup"><span data-stu-id="f3a22-106">Create a new empty solution in Visual Studio called CustomProperty.</span></span>

2. <span data-ttu-id="f3a22-107">Erstellen Sie eine neue Klasse mit dem Namen "ComboBoxItemConverter".</span><span class="sxs-lookup"><span data-stu-id="f3a22-107">Create a new class called ComboBoxItemConverter.</span></span> <span data-ttu-id="f3a22-108">Fügen Sie einen Verweis auf System.Windows.Data hinzu, und sorgen Sie dafür, dass die Klasse aus <xref:System.Windows.Data.IValueConverter> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="f3a22-108">Add a reference to System.Windows.Data, and have the class derive from <xref:System.Windows.Data.IValueConverter>.</span></span> <span data-ttu-id="f3a22-109">Implementieren Sie die Schnittstelle über Visual Studio, um Stubs für `Convert` und `ConvertBack` zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f3a22-109">Have Visual Studio implement the interface to generate stubs for `Convert` and `ConvertBack`.</span></span>

3. <span data-ttu-id="f3a22-110">Fügen Sie der `Convert`-Methode folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3a22-110">Add the following code to the `Convert` method.</span></span> <span data-ttu-id="f3a22-111">In diesem Code wird <xref:System.Activities.InArgument%601> der Aktivität vom Typ <xref:System.String> in den Wert konvertiert, der im Designer platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f3a22-111">This code converts the activity's <xref:System.Activities.InArgument%601> of type <xref:System.String> to the value to be placed in the designer.</span></span>

    ```csharp
    ModelItem modelItem = value as ModelItem;
    if (value != null)
    {
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;

        if (inArgument != null)
        {
            Activity<string> expression = inArgument.Expression;
            VisualBasicValue<string> vbexpression = expression as VisualBasicValue<string>;
            Literal<string> literal = expression as Literal<string>;

            if (literal != null)
            {
                return "\"" + literal.Value + "\"";
            }
            else if (vbexpression != null)
            {
                return vbexpression.ExpressionText;
            }
        }
    }
    return null;
    ```

     <span data-ttu-id="f3a22-112">Der Ausdruck im vorherigen Codeausschnitt kann auch mit <xref:Microsoft.CSharp.Activities.CSharpValue%601> anstelle von <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f3a22-112">The expression in the above code snippet can also be created using <xref:Microsoft.CSharp.Activities.CSharpValue%601> instead of <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span></span>

    ```csharp
    ModelItem modelItem = value as ModelItem;
    if (value != null)
    {
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;

        if (inArgument != null)
        {
            Activity<string> expression = inArgument.Expression;
            CSharpValue<string> csexpression = expression as CSharpValue<string>;
            Literal<string> literal = expression as Literal<string>;

            if (literal != null)
            {
                return "\"" + literal.Value + "\"";
            }
            else if (csexpression != null)
            {
                return csexpression.ExpressionText;
            }
        }
    }
    return null;
    ```

4. <span data-ttu-id="f3a22-113">Fügen Sie der `ConvertBack`-Methode folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3a22-113">Add the following code to the `ConvertBack` method.</span></span> <span data-ttu-id="f3a22-114">Dieser Code konvertiert das eingehende Kombinationsfeldelement wieder zurück in ein <xref:System.Activities.InArgument%601>-Element.</span><span class="sxs-lookup"><span data-stu-id="f3a22-114">This code converts the incoming combo box item back to an <xref:System.Activities.InArgument%601>.</span></span>

    ```csharp
    // Convert combo box value to InArgument<string>
                string itemContent = (string)((ComboBoxItem)value).Content;
                VisualBasicValue<string> vbArgument = new VisualBasicValue<string>(itemContent);
                InArgument<string> inArgument = new InArgument<string>(vbArgument);
                return inArgument;
    ```

     <span data-ttu-id="f3a22-115">Der Ausdruck im vorherigen Codeausschnitt kann auch mit <xref:Microsoft.CSharp.Activities.CSharpValue%601> anstelle von <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f3a22-115">The expression in the above code snippet can also be created using <xref:Microsoft.CSharp.Activities.CSharpValue%601> instead of <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span></span>

    ```csharp
    // Convert combo box value to InArgument<string>
                string itemContent = (string)((ComboBoxItem)value).Content;
                CSharpValue<string> csArgument = new CSharpValue<string>(itemContent);
                InArgument<string> inArgument = new InArgument<string>(csArgument);
                return inArgument;
    ```

## <a name="adding-the-comboboxitemconverter-to-the-custom-designer-of-an-activity"></a><span data-ttu-id="f3a22-116">Hinzufügen von ComboBoxItemConverter zum benutzerdefinierten Designer einer Aktivität</span><span class="sxs-lookup"><span data-stu-id="f3a22-116">Adding the ComboBoxItemConverter to the custom designer of an activity</span></span>

1. <span data-ttu-id="f3a22-117">Fügen Sie dem Projekt ein neues Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3a22-117">Add a new item to the project.</span></span> <span data-ttu-id="f3a22-118">Wählen Sie im Dialogfeld "Neues Element" den Knoten "Workflow" aus, und wählen Sie "Aktivitätsdesigner" als Typ des neuen Elements aus.</span><span class="sxs-lookup"><span data-stu-id="f3a22-118">In the New Item dialog, select the Workflow node and select Activity Designer as the type of the new item.</span></span> <span data-ttu-id="f3a22-119">Benennen Sie das CustomPropertyDesigner-Element.</span><span class="sxs-lookup"><span data-stu-id="f3a22-119">Name the item CustomPropertyDesigner.</span></span>

2. <span data-ttu-id="f3a22-120">Fügen Sie dem neuen Designer ein Kombinationsfeld hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3a22-120">Add a Combo Box to the new designer.</span></span> <span data-ttu-id="f3a22-121">Fügen Sie in der Items-Eigenschaft dem Kombinationsfeld einige Elemente mit den Content-Werten "Item1" und 'Item2 hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3a22-121">In the Items property, add a couple of items to the combo box, with Content values of "Item1" and 'Item2".</span></span>

3. <span data-ttu-id="f3a22-122">Ändern Sie das XAML des Kombinationsfelds, um den neuen Elementkonverter als Elementkonverter hinzuzufügen, der für das Kombinationsfeld verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f3a22-122">Modify the XAML of the combo box to add the new item converter as the item converter to be used for the combo box.</span></span> <span data-ttu-id="f3a22-123">Der Konverter wird dem ActivityDesigner.Resources-Segment als Ressource hinzugefügt und gibt den Konverter im Converter-Attribut für den <xref:System.Windows.Controls.ComboBox> an.</span><span class="sxs-lookup"><span data-stu-id="f3a22-123">The converter is added as a resource in the ActivityDesigner.Resources segment, and specifies the converter in the Converter attribute for the <xref:System.Windows.Controls.ComboBox>.</span></span> <span data-ttu-id="f3a22-124">Beachten Sie, dass der Namespace des Projekts in den Namespaceattributen für den Aktivitätsdesigner angegeben wird. Wenn der Designer in einem anderen Projekt verwendet werden soll, muss dieser Namespace geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f3a22-124">Note that the namespace of the project is specified in the namespaces attributes for the activity designer; if the designer is to be used in a different project, this namespace will need to be changed.</span></span>

    ```xaml
    <sap:ActivityDesigner x:Class="CustomProperty.CustomPropertyDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:c="clr-namespace:CustomProperty"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">

        <sap:ActivityDesigner.Resources>
            <ResourceDictionary>
                <c:ComboBoxItemConverter x:Key="comboBoxItemConverter"/>
            </ResourceDictionary>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ComboBox SelectedValue="{Binding Path=ModelItem.Text, Mode=TwoWay, Converter={StaticResource comboBoxItemConverter}}"  Height="23" HorizontalAlignment="Left" Margin="132,5,0,0" Name="comboBox1" VerticalAlignment="Top" Width="120" ItemsSource="{Binding}">
                <ComboBoxItem>item1</ComboBoxItem>
                <ComboBoxItem>item2</ComboBoxItem>
            </ComboBox>
        </Grid>
    </sap:ActivityDesigner>
    ```

4. <span data-ttu-id="f3a22-125">Erstellen Sie ein neues Element vom Typ <xref:System.Activities.CodeActivity>.</span><span class="sxs-lookup"><span data-stu-id="f3a22-125">Create a new item of type <xref:System.Activities.CodeActivity>.</span></span> <span data-ttu-id="f3a22-126">Der von der IDE für die Aktivität erstellte Standardcode ist für dieses Beispiel ausreichend.</span><span class="sxs-lookup"><span data-stu-id="f3a22-126">The default code created by the IDE for the activity will be sufficient for this example.</span></span>

5. <span data-ttu-id="f3a22-127">Fügen Sie der Klassendefinition das folgende Attribut hinzu:</span><span class="sxs-lookup"><span data-stu-id="f3a22-127">Add the following attribute to the class definition:</span></span>

    ```csharp
    [Designer(typeof(CustomPropertyDesigner))]
    ```

     <span data-ttu-id="f3a22-128">Diese Zeile verknüpft den neuen Designer mit der neuen Klasse.</span><span class="sxs-lookup"><span data-stu-id="f3a22-128">This line associates the new designer with the new class.</span></span>

 <span data-ttu-id="f3a22-129">Die neue Aktivität sollte jetzt mit dem Designer verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="f3a22-129">The new activity should now be associated with the designer.</span></span> <span data-ttu-id="f3a22-130">Sie können die neue Aktivität testen, indem Sie sie einem Workflow hinzufügen und das Kombinationsfeld auf die zwei Werte festlegen.</span><span class="sxs-lookup"><span data-stu-id="f3a22-130">To test the new activity, add it to a workflow, and set the combo box to the two values.</span></span> <span data-ttu-id="f3a22-131">Das Eigenschaftenfenster sollte aktualisiert werden, um den Kombinationsfeldwert widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="f3a22-131">The properties window should update to reflect the combo box value.</span></span>
