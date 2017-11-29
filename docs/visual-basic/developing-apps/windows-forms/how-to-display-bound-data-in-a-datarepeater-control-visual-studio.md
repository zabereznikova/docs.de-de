---
title: 'Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 770003c8879661bfc1ce683f5b6ed84483cf47ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="4da68-102">Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="4da68-102">How to: Display Bound Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="4da68-103">Die häufigste Verwendung von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement wird zum Anzeigen von gebundener Daten aus einer Datenbank oder anderen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="4da68-103">The most common use of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control is to display bound data from a database or other data source.</span></span>  
  
 <span data-ttu-id="4da68-104">Zusätzlich zur gebundene Steuerelemente möchten Sie möglicherweise andere Steuerelemente hinzufügen, z. B. eine statische Bezeichnung oder ein Bild, das wiederholt wird, für jedes Element in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4da68-104">In addition to bound controls, you may want to add other controls, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="4da68-105">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen nicht gebundener Steuerelemente in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="4da68-105">For more information, see [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
 <span data-ttu-id="4da68-106">Sie können auch Binden an eine Datenquelle zur Laufzeit durch Festlegen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> Eigenschaft `True` und Zuweisen von einer Datenquelle, die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4da68-106">You can also bind to a data source at run time by setting the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> property to `True` and assigning a data source to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> property.</span></span> <span data-ttu-id="4da68-107">In diesem Fall müssen Sie alle Interaktionen mit der Datenquelle zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="4da68-107">In this case, you will need to manage all interaction with the data source.</span></span> <span data-ttu-id="4da68-108">Weitere Informationen finden Sie unter [Virtueller Modus im DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="4da68-108">For more information, see [Virtual Mode in the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a><span data-ttu-id="4da68-109">Zum Erstellen von datengebundenen DataRepeater</span><span class="sxs-lookup"><span data-stu-id="4da68-109">To create a data-bound DataRepeater</span></span>  
  
1.  <span data-ttu-id="4da68-110">Ziehen Sie eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in einem Formular oder Containersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="4da68-110">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="4da68-111">Größe der Größe und Position Ziehpunkte, und positionieren Sie das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4da68-111">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="4da68-112">Beachten Sie, dass das Steuerelement über zwei rechteckige Bereiche verfügt.</span><span class="sxs-lookup"><span data-stu-id="4da68-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="4da68-113">Der obere Bereich ist die *Elementvorlage*; Steuerelemente hinzugefügt wurden, um die Vorlage werden in jedem Element wiederholt die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="4da68-113">The upper region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="4da68-114">Der untere Bereich ist der *Viewport*, in die Elemente angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4da68-114">The lower region is the *viewport*, where the items will be displayed.</span></span>  
  
     <span data-ttu-id="4da68-115">Sie können auch die Größe und position des Steuerelements oder der Elementvorlage durch Ändern der **Größe** und **Position** Eigenschaften im Eigenschaftenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4da68-115">You can also size and position the control or the item template by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="4da68-116">Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="4da68-116">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4da68-117">Wenn die **Datenquellen** Fenster leer ist, fügen Sie eine Datenquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="4da68-117">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="4da68-118">Weitere Informationen finden Sie unter [Neue Datenquelle hinzufügen](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="4da68-118">For more information, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="4da68-119">In der **Datenquellen** Fenster, wählen Sie den Knoten den obersten Ebene für die Tabelle, die Daten enthält, die Sie binden möchten.</span><span class="sxs-lookup"><span data-stu-id="4da68-119">In the **Data Sources** window, select the top-level node for the table that contains the data that you want to bind.</span></span>  
  
5.  <span data-ttu-id="4da68-120">Ändern Sie den Ablagetyp der Tabelle, die `Details` durch Klicken auf `Details` in der Dropdown-Liste für den Tabellenknoten.</span><span class="sxs-lookup"><span data-stu-id="4da68-120">Change the drop type of the table to `Details` by clicking `Details` in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="4da68-121">Wählen Sie den Tabellenknoten, und ziehen Sie es in den Elementvorlagenbereich von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4da68-121">Select the table node and drag it onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="4da68-122">Sie können angeben, welche Typen von Steuerelementen für jedes Feld angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4da68-122">You can specify which types of controls are displayed for each field.</span></span> <span data-ttu-id="4da68-123">Weitere Informationen finden Sie unter [festlegen, welches Steuerelement erstellt werden, beim Ziehen aus Datenquellenfenster](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span><span class="sxs-lookup"><span data-stu-id="4da68-123">For more information, see [Set the control to be created when dragging from the Data Sources window](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da68-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4da68-124">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="4da68-125">Einführung in das DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4da68-125">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="4da68-126">Gewusst wie: Anzeigen von nicht gebundenen Steuerelementen in einem DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4da68-126">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="4da68-127">Vorgehensweise: erstellen ein Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="4da68-127">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="4da68-128">Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="4da68-128">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="4da68-129">Problembehandlung beim DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4da68-129">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
