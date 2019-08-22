---
title: 'Vorgehensweise: Erstellen eines gebundenen Steuerelements und Formatieren der angezeigten Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: b5ad85a9477ca32cd28f246abe4ece3cace43182
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666775"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="d1056-102">Vorgehensweise: Erstellen eines gebundenen Steuerelements und Formatieren der angezeigten Daten</span><span class="sxs-lookup"><span data-stu-id="d1056-102">How to: Create a Bound Control and Format the Displayed Data</span></span>

<span data-ttu-id="d1056-103">Mit Windows Forms Datenbindung können Sie die Daten, die in einem Daten gebundenen Steuerelement angezeigt werden, mithilfe des Dialog Felds **Formatierung und erweiterte Bindung** formatieren.</span><span class="sxs-lookup"><span data-stu-id="d1056-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>

### <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="d1056-104">So binden Sie ein Steuerelement und Formatieren der angezeigten Daten</span><span class="sxs-lookup"><span data-stu-id="d1056-104">To bind a control and format the displayed data</span></span>

1. <span data-ttu-id="d1056-105">Stellen Sie die Verbindung zu einer Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="d1056-105">Connect to a data source.</span></span>

     <span data-ttu-id="d1056-106">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit einer Datenquelle](../data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="d1056-106">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>

2. <span data-ttu-id="d1056-107">Wählen Sie im Formular das Steuerelement aus, und öffnen Sie dann das Eigenschaftenfenster.</span><span class="sxs-lookup"><span data-stu-id="d1056-107">In the form, select the control, and then open the Properties window.</span></span>

3. <span data-ttu-id="d1056-108">Erweitern Sie die Eigenschaft **(DataBindings)** , und klicken Sie dann im Feld **(erweitert)** auf die Schaltfläche mit![den Auslassungs Punkten (die Schaltfläche mit den Auslassungs Punkten (..](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png).) im Eigenschaftenfenster von Visual Studio.), um **Formatierung und erweitert anzuzeigen.** Dialogfeld "Bindung", das eine komplette Liste der Eigenschaften für dieses Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="d1056-108">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>

4. <span data-ttu-id="d1056-109">Wählen Sie die Eigenschaft aus, die Sie binden möchten, und klicken Sie dann auf den **Bindungs** Pfeil.</span><span class="sxs-lookup"><span data-stu-id="d1056-109">Select the property you want to bind, and then click the **Binding** arrow.</span></span>

     <span data-ttu-id="d1056-110">Nun wird eine Liste verfügbarer Datenquellen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d1056-110">A list of available data sources is displayed.</span></span>

5. <span data-ttu-id="d1056-111">Erweitern Sie die Datenquelle, die Sie für die Bindung verwenden möchten, bis Sie das gewünschte einzelne Datenelement finden.</span><span class="sxs-lookup"><span data-stu-id="d1056-111">Expand the data source you want to bind to until you find the single data element you want.</span></span>

     <span data-ttu-id="d1056-112">Wenn die Bindung beispielsweise an einen Spaltenwert in einer Dataset-Tabelle erfolgen soll, erweitern Sie den Namen des Datasets, und erweitern sie dann den Tabellennamen, um die Spaltennamen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d1056-112">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

6. <span data-ttu-id="d1056-113">Klicken Sie auf den Namen des Elements, das gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="d1056-113">Click the name of an element to bind to.</span></span>

7. <span data-ttu-id="d1056-114">Klicken Sie im Feld **Formattyp** auf das Format, das Sie auf die im Steuerelement angezeigten Daten anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d1056-114">In the **Format type** box, click the format you want to apply to the data displayed in the control.</span></span>

     <span data-ttu-id="d1056-115">In jedem Fall können Sie den Wert festlegen, der im Steuerelement angezeigt wird, wenn die Datenquelle <xref:System.DBNull> enthält.</span><span class="sxs-lookup"><span data-stu-id="d1056-115">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="d1056-116">Andernfalls sind die Optionen je nach ausgewähltem Formattyp leicht abweichend.</span><span class="sxs-lookup"><span data-stu-id="d1056-116">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="d1056-117">In der folgenden Tabelle werden die Formattypen und Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d1056-117">The following table shows the format types and options.</span></span>

    |<span data-ttu-id="d1056-118">Formattyp</span><span class="sxs-lookup"><span data-stu-id="d1056-118">Format type</span></span>|<span data-ttu-id="d1056-119">Formatierungsoption</span><span class="sxs-lookup"><span data-stu-id="d1056-119">Formatting option</span></span>|
    |-----------------|-----------------------|
    |<span data-ttu-id="d1056-120">Keine Formatierung</span><span class="sxs-lookup"><span data-stu-id="d1056-120">No Formatting</span></span>|<span data-ttu-id="d1056-121">Keine Optionen.</span><span class="sxs-lookup"><span data-stu-id="d1056-121">No options.</span></span>|
    |<span data-ttu-id="d1056-122">Numeric</span><span class="sxs-lookup"><span data-stu-id="d1056-122">Numeric</span></span>|<span data-ttu-id="d1056-123">Geben Sie die Anzahl von Dezimalstellen mit dem auf-ab-Steuerelement für **Dezimalstellen** an.</span><span class="sxs-lookup"><span data-stu-id="d1056-123">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="d1056-124">Währung</span><span class="sxs-lookup"><span data-stu-id="d1056-124">Currency</span></span>|<span data-ttu-id="d1056-125">Geben Sie die Anzahl von Dezimalstellen mit dem auf-ab-Steuerelement für **Dezimalstellen** an.</span><span class="sxs-lookup"><span data-stu-id="d1056-125">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="d1056-126">Datum/Zeit</span><span class="sxs-lookup"><span data-stu-id="d1056-126">Date Time</span></span>|<span data-ttu-id="d1056-127">Wählen Sie aus, wie das Datum und die Uhrzeit angezeigt werden sollen, indem Sie eines der Elemente im Feld Typauswahl auswählen.</span><span class="sxs-lookup"><span data-stu-id="d1056-127">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|
    |<span data-ttu-id="d1056-128">Wissenschaftlich</span><span class="sxs-lookup"><span data-stu-id="d1056-128">Scientific</span></span>|<span data-ttu-id="d1056-129">Geben Sie die Anzahl von Dezimalstellen mit dem auf-ab-Steuerelement für **Dezimalstellen** an.</span><span class="sxs-lookup"><span data-stu-id="d1056-129">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="d1056-130">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="d1056-130">Custom</span></span>|<span data-ttu-id="d1056-131">Geben Sie eine benutzerdefinierte Formatzeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="d1056-131">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="d1056-132">Weitere Informationen finden Sie unter [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="d1056-132">For more information, see [Formatting Types](../../standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="d1056-133">**Hinweis**:  Bei benutzerdefinierten Formatzeichenfolgen kann ein erfolgreicher Roundtrip zwischen Datenquelle und gebundenem Steuerelement nicht garantiert werden</span><span class="sxs-lookup"><span data-stu-id="d1056-133">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="d1056-134">Behandeln Sie stattdessen das <xref:System.Windows.Forms.Binding.Parse>- oder <xref:System.Windows.Forms.Binding.Format>-Ereignis für die Bindung, und wenden Sie im Ereignisbehandlungscode eine benutzerdefinierte Formatierung an.</span><span class="sxs-lookup"><span data-stu-id="d1056-134">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|

8. <span data-ttu-id="d1056-135">Klicken Sie auf **OK** , um das Dialogfeld **Formatierung und erweiterte Bindung** zu schließen und zum Eigenschaftenfenster zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="d1056-135">Click **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1056-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1056-136">See also</span></span>

- [<span data-ttu-id="d1056-137">Vorgehensweise: Erstellen eines einfach gebundenen Steuer Elements in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="d1056-137">How to: Create a Simple-Bound Control on a Windows Form</span></span>](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [<span data-ttu-id="d1056-138">Validierung von Benutzereingaben in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d1056-138">User Input Validation in Windows Forms</span></span>](user-input-validation-in-windows-forms.md)
- [<span data-ttu-id="d1056-139">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="d1056-139">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
