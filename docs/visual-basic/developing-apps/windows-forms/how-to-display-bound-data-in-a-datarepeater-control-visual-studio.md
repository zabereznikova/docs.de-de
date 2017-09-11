---
title: 'Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement (Visual Studio) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 677c964ee9ebbad6ec712a29c8b9c8920aa7e7ec
ms.contentlocale: de-de
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="d36a9-102">Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="d36a9-102">How to: Display Bound Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="d36a9-103">Die häufigste Verwendung von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement gebundene Daten aus einer Datenbank oder anderen Datenquelle angezeigt wird.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d36a9-103">The most common use of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control is to display bound data from a database or other data source.</span></span>  
  
 <span data-ttu-id="d36a9-104">Zusätzlich zu den gebundenen Steuerelementen sollten andere Steuerelemente hinzufügen, z. B. eine statische Bezeichnung oder ein Bild, das wiederholt wird, für jedes Element in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d36a9-104">In addition to bound controls, you may want to add other controls, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="d36a9-105">Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen nicht gebundener Steuerelemente in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="d36a9-105">For more information, see [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
 <span data-ttu-id="d36a9-106">Sie können auch Binden an eine Datenquelle zur Laufzeit durch Festlegen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>-Eigenschaft `True` und Zuweisen von einer Datenquelle, die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A>Eigenschaft.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A></span><span class="sxs-lookup"><span data-stu-id="d36a9-106">You can also bind to a data source at run time by setting the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> property to `True` and assigning a data source to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> property.</span></span> <span data-ttu-id="d36a9-107">In diesem Fall müssen Sie alle Interaktionen mit der Datenquelle verwalten.</span><span class="sxs-lookup"><span data-stu-id="d36a9-107">In this case, you will need to manage all interaction with the data source.</span></span> <span data-ttu-id="d36a9-108">Weitere Informationen finden Sie unter [Virtueller Modus im DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="d36a9-108">For more information, see [Virtual Mode in the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a><span data-ttu-id="d36a9-109">Erstellen von datengebundenen DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d36a9-109">To create a data-bound DataRepeater</span></span>  
  
1.  <span data-ttu-id="d36a9-110">Ziehen Sie ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in ein Formular oder Containersteuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d36a9-110">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="d36a9-111">Größe der Größe und Position Ziehpunkte, und platzieren Sie das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d36a9-111">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="d36a9-112">Beachten Sie, dass das Steuerelement über zwei rechteckige Bereiche verfügt.</span><span class="sxs-lookup"><span data-stu-id="d36a9-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="d36a9-113">Der obere Bereich ist die *Elementvorlage*; die Vorlage hinzugefügten Steuerelemente werden in jedem Element wiederholt die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement zur Laufzeit.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d36a9-113">The upper region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="d36a9-114">Der untere Bereich ist der *Viewport*, wo die Elemente angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d36a9-114">The lower region is the *viewport*, where the items will be displayed.</span></span>  
  
     <span data-ttu-id="d36a9-115">Sie können auch die Größe und position des Steuerelements oder der Elementvorlage durch Ändern der **Größe** und **Position** Eigenschaften im Eigenschaftenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d36a9-115">You can also size and position the control or the item template by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="d36a9-116">Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d36a9-116">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d36a9-117">Wenn die **Datenquellen** Fenster leer ist, fügen Sie eine Datenquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="d36a9-117">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="d36a9-118">Weitere Informationen finden Sie unter [neue Datenquellen hinzufügen](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="d36a9-118">For more information, see [Add new data sources](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="d36a9-119">In der **Datenquellen** Fenster Wählen Sie den Knoten den obersten Ebene für die Tabelle, die die Daten enthält, die Sie binden möchten.</span><span class="sxs-lookup"><span data-stu-id="d36a9-119">In the **Data Sources** window, select the top-level node for the table that contains the data that you want to bind.</span></span>  
  
5.  <span data-ttu-id="d36a9-120">Ändern Sie den Ablagetyp der Tabelle `Details` durch Klicken auf `Details` in der Dropdown-Liste auf den Knoten der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d36a9-120">Change the drop type of the table to `Details` by clicking `Details` in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="d36a9-121">Wählen Sie den Tabellenknoten, und ziehen Sie es in den Bereich der Item-Vorlage von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d36a9-121">Select the table node and drag it onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="d36a9-122">Sie können angeben, welche Arten von Steuerelementen für jedes Feld angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d36a9-122">You can specify which types of controls are displayed for each field.</span></span> <span data-ttu-id="d36a9-123">Weitere Informationen finden Sie unter [legen Sie das Steuerelement beim Ziehen aus dem Datenquellenfenster erstellt werden](https://docs.microsoft.com/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span><span class="sxs-lookup"><span data-stu-id="d36a9-123">For more information, see [Set the control to be created when dragging from the Data Sources window](https://docs.microsoft.com/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d36a9-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d36a9-124">See Also</span></span>  
 <span data-ttu-id="d36a9-125"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d36a9-125"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span></span>   
<span data-ttu-id="d36a9-126"> [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d36a9-126"> [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="d36a9-127"> [Gewusst wie: Anzeigen von nicht gebundenen Steuerelementen in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d36a9-127"> [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="d36a9-128"> [Gewusst wie: Erstellen einer Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span><span class="sxs-lookup"><span data-stu-id="d36a9-128"> [How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span></span>  
<span data-ttu-id="d36a9-129"> [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d36a9-129"> [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="d36a9-130"> [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="d36a9-130"> [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span></span>
