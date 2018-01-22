---
title: 'Gewusst wie: Erstellen eines gebundenen Steuerelements und Formatieren der angezeigten Daten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6088048ed27b2021e297494275f4e80f7c0cb681
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="a1026-102">Gewusst wie: Erstellen eines gebundenen Steuerelements und Formatieren der angezeigten Daten</span><span class="sxs-lookup"><span data-stu-id="a1026-102">How to: Create a Bound Control and Format the Displayed Data</span></span>
<span data-ttu-id="a1026-103">Mit Windows Forms-Datenbindung können Sie Daten formatieren, die in einem datengebundenen Steuerelement angezeigt wird, indem die **Formatierung und erweiterte Bindung** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="a1026-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1026-104">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="a1026-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a1026-105">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a1026-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a1026-106">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="a1026-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="a1026-107">So binden Sie ein Steuerelement und Formatieren der angezeigten Daten</span><span class="sxs-lookup"><span data-stu-id="a1026-107">To bind a control and format the displayed data</span></span>  
  
1.  <span data-ttu-id="a1026-108">Stellen Sie die Verbindung zu einer Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="a1026-108">Connect to a data source.</span></span>  
  
     <span data-ttu-id="a1026-109">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit einer Datenquelle](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="a1026-109">For more information, see [Connecting to a Data Source](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2.  <span data-ttu-id="a1026-110">Wählen Sie im Formular das Steuerelement aus, und öffnen Sie dann das Eigenschaftenfenster.</span><span class="sxs-lookup"><span data-stu-id="a1026-110">In the form, select the control, and then open the Properties window.</span></span>  
  
3.  <span data-ttu-id="a1026-111">Erweitern Sie die **(DataBindings)** -Eigenschaft, und klicken Sie dann in der **(Erweitert)** klicken Sie auf die Schaltfläche mit den Auslassungspunkten (![von VisualStudioEllipsesButton] (../../../docs/framework/winforms/media/vbellipsesbutton.png " VbEllipsesButton")) zum Anzeigen der **Formatierung und erweiterte Bindung** (Dialogfeld), die eine vollständige Liste der Eigenschaften dieses Steuerelements befindet.</span><span class="sxs-lookup"><span data-stu-id="a1026-111">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>  
  
4.  <span data-ttu-id="a1026-112">Wählen Sie die Eigenschaft zu binden, und klicken Sie dann auf die **binden** Pfeil.</span><span class="sxs-lookup"><span data-stu-id="a1026-112">Select the property you want to bind, and then click the **Binding** arrow.</span></span>  
  
     <span data-ttu-id="a1026-113">Nun wird eine Liste verfügbarer Datenquellen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1026-113">A list of available data sources is displayed.</span></span>  
  
5.  <span data-ttu-id="a1026-114">Erweitern Sie die Datenquelle, die Sie für die Bindung verwenden möchten, bis Sie das gewünschte einzelne Datenelement finden.</span><span class="sxs-lookup"><span data-stu-id="a1026-114">Expand the data source you want to bind to until you find the single data element you want.</span></span>  
  
     <span data-ttu-id="a1026-115">Wenn die Bindung beispielsweise an einen Spaltenwert in einer Dataset-Tabelle erfolgen soll, erweitern Sie den Namen des Datasets, und erweitern sie dann den Tabellennamen, um die Spaltennamen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a1026-115">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
6.  <span data-ttu-id="a1026-116">Klicken Sie auf den Namen des Elements, das gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1026-116">Click the name of an element to bind to.</span></span>  
  
7.  <span data-ttu-id="a1026-117">In der **Formattyp** klicken Sie auf das Format der im Steuerelement angezeigten Daten anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a1026-117">In the **Format type** box, click the format you want to apply to the data displayed in the control.</span></span>  
  
     <span data-ttu-id="a1026-118">In jedem Fall können Sie den Wert festlegen, der im Steuerelement angezeigt wird, wenn die Datenquelle <xref:System.DBNull> enthält.</span><span class="sxs-lookup"><span data-stu-id="a1026-118">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="a1026-119">Andernfalls sind die Optionen je nach ausgewähltem Formattyp leicht abweichend.</span><span class="sxs-lookup"><span data-stu-id="a1026-119">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="a1026-120">In der folgenden Tabelle werden die Formattypen und Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1026-120">The following table shows the format types and options.</span></span>  
  
    |<span data-ttu-id="a1026-121">Formattyp</span><span class="sxs-lookup"><span data-stu-id="a1026-121">Format type</span></span>|<span data-ttu-id="a1026-122">Formatierungsoption</span><span class="sxs-lookup"><span data-stu-id="a1026-122">Formatting option</span></span>|  
    |-----------------|-----------------------|  
    |<span data-ttu-id="a1026-123">Keine Formatierung</span><span class="sxs-lookup"><span data-stu-id="a1026-123">No Formatting</span></span>|<span data-ttu-id="a1026-124">Keine Optionen.</span><span class="sxs-lookup"><span data-stu-id="a1026-124">No options.</span></span>|  
    |<span data-ttu-id="a1026-125">Numeric</span><span class="sxs-lookup"><span data-stu-id="a1026-125">Numeric</span></span>|<span data-ttu-id="a1026-126">Geben Sie die Anzahl der Dezimalstellen mithilfe **Dezimalstellen** auf-ab-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a1026-126">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="a1026-127">Währung</span><span class="sxs-lookup"><span data-stu-id="a1026-127">Currency</span></span>|<span data-ttu-id="a1026-128">Geben Sie die Anzahl der Dezimalstellen mithilfe **Dezimalstellen** auf-ab-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a1026-128">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="a1026-129">Datum/Zeit</span><span class="sxs-lookup"><span data-stu-id="a1026-129">Date Time</span></span>|<span data-ttu-id="a1026-130">Wählen Sie, wie das Datum und die Uhrzeit angezeigt werden soll, durch Auswahl eines der Elemente in der **Typ** Auswahlfeld.</span><span class="sxs-lookup"><span data-stu-id="a1026-130">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|  
    |<span data-ttu-id="a1026-131">Wissenschaftlich</span><span class="sxs-lookup"><span data-stu-id="a1026-131">Scientific</span></span>|<span data-ttu-id="a1026-132">Geben Sie die Anzahl der Dezimalstellen mithilfe **Dezimalstellen** auf-ab-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a1026-132">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="a1026-133">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="a1026-133">Custom</span></span>|<span data-ttu-id="a1026-134">Geben Sie eine benutzerdefinierte Formatzeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="a1026-134">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="a1026-135">Weitere Informationen finden Sie unter [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="a1026-135">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="a1026-136">**Hinweis:** benutzerdefinierte Formatzeichenfolgen erfolgreicher Roundtrip zwischen der Datenquelle und gebundenem Steuerelement nicht garantiert.</span><span class="sxs-lookup"><span data-stu-id="a1026-136">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="a1026-137">Behandeln Sie stattdessen das <xref:System.Windows.Forms.Binding.Parse>- oder <xref:System.Windows.Forms.Binding.Format>-Ereignis für die Bindung, und wenden Sie im Ereignisbehandlungscode eine benutzerdefinierte Formatierung an.</span><span class="sxs-lookup"><span data-stu-id="a1026-137">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|  
  
8.  <span data-ttu-id="a1026-138">Klicken Sie auf **OK** schließen die **Formatierung und erweiterte Bindung** Dialogfeld und zum Eigenschaftenfenster zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a1026-138">Click **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1026-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1026-139">See Also</span></span>  
 [<span data-ttu-id="a1026-140">Vorgehensweise: Erstellen eines einfach gebundenen Steuerelements in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="a1026-140">How to: Create a Simple-Bound Control on a Windows Form</span></span>](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [<span data-ttu-id="a1026-141">Validierung von Benutzereingaben in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a1026-141">User Input Validation in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 [<span data-ttu-id="a1026-142">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="a1026-142">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
