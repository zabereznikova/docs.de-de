---
title: "Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, customizing
- DataRepeater, changing run time appearance
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 585ff4c942185f3199fe6e9e47a4ebd9f1f0a478
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-a-datarepeater-control-visual-studio"></a><span data-ttu-id="04807-102">Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="04807-102">How to: Change the Appearance of a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="04807-103">Sie können die Darstellung der Ändern einer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements zur Entwurfszeit durch Festlegen von Eigenschaften oder zur Laufzeit durch Behandeln der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="04807-103">You can change the appearance of a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time by setting properties or at run time by handling the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event.</span></span>  
  
 <span data-ttu-id="04807-104">Eigenschaften, die zur Entwurfszeit festgelegt werden Wenn der Elementvorlagenbereich des Steuerelements aktiviert ist, werden für jede wiederholt werden <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="04807-104">Properties that you set at design time when the item template section of the control is selected will be repeated for each <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> at run time.</span></span> <span data-ttu-id="04807-105">Darstellungseigenschaften des der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement selbst werden zur Laufzeit nur, wenn ein Teil des Containers bleibt aufgedeckt angezeigt (z. B. wenn die <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft auf einen hohen Wert festgelegt ist).</span><span class="sxs-lookup"><span data-stu-id="04807-105">Appearance-related properties of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control itself will be visible at run time only if a part of the container is left uncovered (for example, if the <xref:System.Windows.Forms.Control.Padding%2A> property is set to a large value).</span></span>  
  
 <span data-ttu-id="04807-106">Zur Laufzeit können Darstellungseigenschaften auf Bedingungen Basis festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="04807-106">At run time, appearance-related properties can be set based on conditions.</span></span> <span data-ttu-id="04807-107">Beispielsweise können in einer planungsanwendung Sie ändern die Farbe des Hintergrunds eines Elements, um Benutzer zu warnen, wenn ein Element überfällig ist.</span><span class="sxs-lookup"><span data-stu-id="04807-107">For example, in a scheduling application, you might change the background color of an item to warn users when an item is past due.</span></span> <span data-ttu-id="04807-108">In der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> Ereignishandler, d. h. Wenn Sie eine Eigenschaft wie z. B. in einer bedingten Anweisung festlegen `If…Then`, müssen Sie auch verwenden eine `Else` -Klausel, um die Darstellung festzulegen, wenn die Bedingung nicht erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="04807-108">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, if you set a property in a conditional statement such as `If…Then`, you must also use an `Else` clause to specify the appearance when the condition is not met.</span></span>  
  
### <a name="to-change-the-appearance-at-design-time"></a><span data-ttu-id="04807-109">So ändern Sie die Darstellung zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="04807-109">To change the appearance at design time</span></span>  
  
1.  <span data-ttu-id="04807-110">Wählen Sie in der Windows Forms-Designer den Elementvorlagenbereich (oberer Bereich) von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="04807-110">In the Windows Forms Designer, select the item template (upper) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="04807-111">Klicken Sie im Eigenschaftenfenster wählen Sie eine Eigenschaft, und ändern Sie den Wert.</span><span class="sxs-lookup"><span data-stu-id="04807-111">In the Properties window, select a property and change the value.</span></span> <span data-ttu-id="04807-112">Allgemeine Eigenschaften, die Darstellung beeinflussen enthalten <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, und <xref:System.Windows.Forms.Control.ForeColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="04807-112">Common properties that affect appearance include <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, and <xref:System.Windows.Forms.Control.ForeColor%2A>.</span></span>  
  
### <a name="to-change-the-appearance-at-run-time"></a><span data-ttu-id="04807-113">So ändern Sie die Darstellung zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="04807-113">To change the appearance at run time</span></span>  
  
1.  <span data-ttu-id="04807-114">Klicken Sie im Code-Editor in der Dropdownliste „Ereignis“ auf **DrawItem**.</span><span class="sxs-lookup"><span data-stu-id="04807-114">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
2.  <span data-ttu-id="04807-115">In der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> -Ereignishandler Code hinzufügen, um die Eigenschaften festlegen:</span><span class="sxs-lookup"><span data-stu-id="04807-115">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add code to set the properties:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="04807-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04807-116">Example</span></span>  
 <span data-ttu-id="04807-117">Einige allgemeine Anpassungen für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement gehört das Anzeigen von Zeilen abwechselnde Farben und die Farbe eines Felds auf Grundlage einer Bedingung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="04807-117">Some common customizations for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control include displaying the rows in alternating colors and changing the color of a field based on a condition.</span></span> <span data-ttu-id="04807-118">Das folgende Beispiel zeigt, wie diese Anpassungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="04807-118">The following example shows how to perform these customizations.</span></span> <span data-ttu-id="04807-119">In diesem Beispiel wird davon ausgegangen, dass Sie haben eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement, das die Products-Tabelle in der Northwind-Datenbank gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="04807-119">This example assumes that you have a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control that is bound to the Products table in the Northwind database.</span></span>  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-csharp[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 <span data-ttu-id="04807-120">Beachten Sie, dass für beide diese Anpassungen Sie Code zum Festlegen der Eigenschaften für beide Seiten der Bedingung angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="04807-120">Note that for both of these customizations, you must provide code to set the properties for both sides of the condition.</span></span> <span data-ttu-id="04807-121">Wenn Sie keinen angeben der `Else` Bedingung, werden Sie zur Laufzeit unerwartete Ergebnisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="04807-121">If you do not specify the `Else` condition, you will see unexpected results at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04807-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04807-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
 [<span data-ttu-id="04807-123">Einführung in das DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="04807-123">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="04807-124">Problembehandlung beim DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="04807-124">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="04807-125">Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="04807-125">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="04807-126">Gewusst wie: Anzeigen von nicht gebundenen Steuerelementen in einem DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="04807-126">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="04807-127">Gewusst wie: Anzeigen von Elementheadern in einem DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="04807-127">How to: Display Item Headers in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
