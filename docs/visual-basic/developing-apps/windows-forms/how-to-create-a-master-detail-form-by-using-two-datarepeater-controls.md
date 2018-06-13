---
title: 'Vorgehensweise: Erstellen einer Master / Detail-Formulars mit zwei DataRepeater-Steuerelementen (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
ms.openlocfilehash: 84639a5d49a3fa4a8c6845793c39fc8a67c31e02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590906"
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a><span data-ttu-id="c972c-102">Gewusst wie: Erstellen eines Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="c972c-102">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>
<span data-ttu-id="c972c-103">Sie können verknüpfte Daten anzeigen, indem Sie mithilfe von zwei oder mehr <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelemente zum Erstellen eines Master-/Detailformulars.</span><span class="sxs-lookup"><span data-stu-id="c972c-103">You can display related data by using two or more <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls to create a master/detail form.</span></span> <span data-ttu-id="c972c-104">Möglicherweise möchten z. B. eine Liste von Kunden in einem anzeigen <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, und wenn der Benutzer einen Kunden auswählt, zeigen Sie eine Liste der Bestellungen des Kunden in einer Sekunde <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span><span class="sxs-lookup"><span data-stu-id="c972c-104">For example, you might want to display a list of customers in one <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and when the user selects a customer, display a list of that customer's orders in a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
 <span data-ttu-id="c972c-105">Zeigen Sie verwandte Daten durch Ziehen von Detailelementen, die den gleichen Hauptschlüssel Tabellenknoten aus freigeben der **Datenquellen** auf eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="c972c-105">You can display related data by dragging detail items that share the same master table node from the **Data Sources** window onto a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="c972c-106">Z. B. Wenn Sie eine Datenquelle, die einer Customers-Tabelle und einer verknüpften Bestellungstabelle aufweist verfügen, Sie finden Sie in beide Tabellen als Knoten der obersten Ebene in der Strukturansicht in die **Datenquellen** Fenster.</span><span class="sxs-lookup"><span data-stu-id="c972c-106">For example, if you have a data source that has a Customers table and a related Orders table, you see both tables as top-level nodes in the tree view in the **Data Sources** window.</span></span> <span data-ttu-id="c972c-107">Erweitern Sie den Kunden-Knoten, sodass die Spalten angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="c972c-107">Expand the Customers node so that you can see the columns.</span></span> <span data-ttu-id="c972c-108">Beachten Sie, dass die letzte Spalte in der Liste einen erweiterbaren Knoten handelt, der die Orders-Tabelle darstellt.</span><span class="sxs-lookup"><span data-stu-id="c972c-108">Notice that the last column in the list is an expandable node that represents the Orders table.</span></span> <span data-ttu-id="c972c-109">Dieser Knoten entspricht den verknüpften Bestellungen eines Kunden.</span><span class="sxs-lookup"><span data-stu-id="c972c-109">This node represents the related orders for a customer.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a><span data-ttu-id="c972c-110">Um die Anzeige zugehöriger Daten in zwei DataRepeater-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="c972c-110">To display related data in two DataRepeater controls</span></span>  
  
1.  <span data-ttu-id="c972c-111">Ziehen Sie zwei <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelemente aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in einem Formular oder Containersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="c972c-111">Drag two <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="c972c-112">Ziehen Sie die Größe und Position Ziehpunkte, um die Größe der Steuerelemente, und positionieren Sie sie Seite-an-Seite.</span><span class="sxs-lookup"><span data-stu-id="c972c-112">Drag the sizing and position handles to size the controls and position them side-by-side.</span></span>  
  
3.  <span data-ttu-id="c972c-113">Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="c972c-113">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c972c-114">Wenn die **Datenquellen** Fenster leer ist, fügen Sie eine Datenquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="c972c-114">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="c972c-115">Weitere Informationen finden Sie unter [Neue Datenquelle hinzufügen](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="c972c-115">For more information, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="c972c-116">In der **Datenquellen** Fenster, wählen Sie den Knoten den obersten Ebene für die Mastertabelle.</span><span class="sxs-lookup"><span data-stu-id="c972c-116">In the **Data Sources** window, select the top-level node for the master table.</span></span>  
  
5.  <span data-ttu-id="c972c-117">Ändern Sie den Ablagetyp für die Mastertabelle in Details durch Klicken auf **Details** in der Dropdown-Liste für den Tabellenknoten.</span><span class="sxs-lookup"><span data-stu-id="c972c-117">Change the drop type of the master table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="c972c-118">Ziehen Sie die Mastertabelle-Knoten in den Elementvorlagenbereich des ersten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="c972c-118">Drag the master table node onto the item template region of the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
7.  <span data-ttu-id="c972c-119">Erweitern Sie den Hauptschlüssel Tabellenknoten, und wählen Sie den Detailknoten für die verknüpfte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c972c-119">Expand the master table node and select the detail node for the related table.</span></span>  
  
8.  <span data-ttu-id="c972c-120">Ändern Sie den Ablagetyp der Detailtabelle in Details durch Klicken auf **Details** in der Dropdown-Liste für den Tabellenknoten.</span><span class="sxs-lookup"><span data-stu-id="c972c-120">Change the drop type of the detail table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
9. <span data-ttu-id="c972c-121">Wählen Sie diese Tabellenknoten, und ziehen Sie es in den Elementvorlagenbereich des zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="c972c-121">Select this table node and drag it onto the item template region of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c972c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c972c-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="c972c-123">Einführung in das DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c972c-123">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="c972c-124">Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c972c-124">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="c972c-125">Gewusst wie: Anzeigen von verknüpften Daten in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="c972c-125">How to: Display Related Data in a Windows Forms Application</span></span>](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [<span data-ttu-id="c972c-126">Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="c972c-126">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="c972c-127">Problembehandlung beim DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c972c-127">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
