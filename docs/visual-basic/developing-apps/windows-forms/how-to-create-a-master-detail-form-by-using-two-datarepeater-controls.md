---
title: 'Gewusst wie: Erstellen einer Master / Detail-Formular mit zwei DataRepeater-Steuerelementen (Visual Studio) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: 7
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
ms.openlocfilehash: 4ed0b1fa0e7fac96cef3bde61efac66681f2507b
ms.contentlocale: de-de
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a><span data-ttu-id="c8fca-102">Gewusst wie: Erstellen eines Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="c8fca-102">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>
<span data-ttu-id="c8fca-103">Sie können verknüpfte Daten anzeigen, indem Sie mithilfe von zwei oder mehr <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelemente zum Erstellen eines Master/Detail-Formulars.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="c8fca-103">You can display related data by using two or more <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls to create a master/detail form.</span></span> <span data-ttu-id="c8fca-104">Beispielsweise möchten Sie zeigt eine Liste von Kunden in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, und wenn der Benutzer einen Kunden auswählt, zeigen Sie eine Liste der Aufträge dieses Kunden pro Sekunde <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="c8fca-104">For example, you might want to display a list of customers in one <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and when the user selects a customer, display a list of that customer's orders in a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
 <span data-ttu-id="c8fca-105">Verknüpfte Daten anzuzeigen, ziehen Sie Detailelemente, die die gleichen Mastertabelle befinden, aus der **Datenquellen** auf eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="c8fca-105">You can display related data by dragging detail items that share the same master table node from the **Data Sources** window onto a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="c8fca-106">Z. B. Wenn Sie eine Datenquelle, die einer Kundentabelle und einer verknüpften Auftragstabelle verfügt haben, Sie finden Sie in beide Tabellen als Knoten der obersten Ebene in der Strukturansicht der **Datenquellen** Fenster.</span><span class="sxs-lookup"><span data-stu-id="c8fca-106">For example, if you have a data source that has a Customers table and a related Orders table, you see both tables as top-level nodes in the tree view in the **Data Sources** window.</span></span> <span data-ttu-id="c8fca-107">Erweitern Sie den Knoten Kunden aus, sodass die Spalten angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="c8fca-107">Expand the Customers node so that you can see the columns.</span></span> <span data-ttu-id="c8fca-108">Beachten Sie, dass die letzte Spalte in der Liste einen erweiterbaren Knoten handelt, der die Orders-Tabelle darstellt.</span><span class="sxs-lookup"><span data-stu-id="c8fca-108">Notice that the last column in the list is an expandable node that represents the Orders table.</span></span> <span data-ttu-id="c8fca-109">Dieser Knoten entspricht den verknüpften Bestellungen eines Kunden.</span><span class="sxs-lookup"><span data-stu-id="c8fca-109">This node represents the related orders for a customer.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a><span data-ttu-id="c8fca-110">Um verknüpfte Daten in zwei DataRepeater-Steuerelementen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c8fca-110">To display related data in two DataRepeater controls</span></span>  
  
1.  <span data-ttu-id="c8fca-111">Ziehen Sie zwei <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelemente aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in ein Formular oder Containersteuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="c8fca-111">Drag two <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="c8fca-112">Ziehen Sie die Ziehpunkte Größe und Position, um die Größe der Steuerelemente und positionieren Sie diese Seite-an-Seite.</span><span class="sxs-lookup"><span data-stu-id="c8fca-112">Drag the sizing and position handles to size the controls and position them side-by-side.</span></span>  
  
3.  <span data-ttu-id="c8fca-113">Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="c8fca-113">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c8fca-114">Wenn die **Datenquellen** Fenster leer ist, fügen Sie eine Datenquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="c8fca-114">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="c8fca-115">Weitere Informationen finden Sie unter [neue Datenquellen hinzufügen](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="c8fca-115">For more information, see [Add new data sources](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="c8fca-116">In der **Datenquellen** Fenster Wählen Sie den Knoten den obersten Ebene für die Mastertabelle.</span><span class="sxs-lookup"><span data-stu-id="c8fca-116">In the **Data Sources** window, select the top-level node for the master table.</span></span>  
  
5.  <span data-ttu-id="c8fca-117">Ändern Sie den Ablagetyp der Mastertabelle in Details durch Klicken auf **Details** in der Dropdown-Liste auf den Knoten der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c8fca-117">Change the drop type of the master table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="c8fca-118">Ziehen Sie den Elementvorlagenbereich des ersten Knotens Mastertabelle <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="c8fca-118">Drag the master table node onto the item template region of the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
7.  <span data-ttu-id="c8fca-119">Erweitern Sie den Tabellenknoten für die master-, und wählen Sie den Detailknoten für die verknüpfte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c8fca-119">Expand the master table node and select the detail node for the related table.</span></span>  
  
8.  <span data-ttu-id="c8fca-120">Ändern Sie den Ablagetyp der Detailtabelle in Details durch Klicken auf **Details** in der Dropdown-Liste auf den Knoten der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c8fca-120">Change the drop type of the detail table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
9. <span data-ttu-id="c8fca-121">Wählen Sie diesen Tabellenknoten aus, und ziehen Sie es in den Elementvorlagenbereich der zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="c8fca-121">Select this table node and drag it onto the item template region of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8fca-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8fca-122">See Also</span></span>  
 <span data-ttu-id="c8fca-123"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="c8fca-123"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span></span>   
<span data-ttu-id="c8fca-124"> [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="c8fca-124"> [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="c8fca-125"> [Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="c8fca-125"> [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="c8fca-126"> [Gewusst wie: Anzeigen von verknüpften Daten in einer Windows Forms-Anwendung](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd) </span><span class="sxs-lookup"><span data-stu-id="c8fca-126"> [How to: Display Related Data in a Windows Forms Application](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd) </span></span>  
<span data-ttu-id="c8fca-127"> [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="c8fca-127"> [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="c8fca-128"> [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="c8fca-128"> [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span></span>
