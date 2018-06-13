---
title: 'Gewusst wie: Suchen von Daten in einem DataRepeater-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, implementing search
- DataRepeater, searching data
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
ms.openlocfilehash: 689990ee125c85c3151a4e965b619fde068d220e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588053"
---
# <a name="how-to-search-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="1a08d-102">Gewusst wie: Suchen von Daten in einem DataRepeater-Steuerelement (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="1a08d-102">How to: Search Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="1a08d-103">Beim Verwenden einer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement, das viele Datensätze enthält, können Sie Benutzern die Suche nach einem bestimmten Datensatz empfiehlt.</span><span class="sxs-lookup"><span data-stu-id="1a08d-103">When you are using a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control that contains many records, you may want to let users search for a specific record.</span></span> <span data-ttu-id="1a08d-104">Sie können eine Suche durch Abfragen der zugrunde liegende implementieren, anstatt das Durchsuchen der Daten in das Steuerelement, <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="1a08d-104">Rather than searching the data in the control itself, you can implement a search by querying the underlying <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="1a08d-105">Wenn das Element gefunden wird, können Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> Eigenschaft wählen Sie das Element, und es per Bildlauf anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1a08d-105">If the item is found, you can then use the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> property to select the item and scroll it into view.</span></span>  
  
### <a name="to-implement-search"></a><span data-ttu-id="1a08d-106">Suche implementiert.</span><span class="sxs-lookup"><span data-stu-id="1a08d-106">To implement search</span></span>  
  
1.  <span data-ttu-id="1a08d-107">Ziehen Sie ein <xref:System.Windows.Forms.TextBox> -Steuerelement aus der **Toolbox** auf das Formular, das das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="1a08d-107">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="1a08d-108">Ändern Sie im Eigenschaftenfenster die Eigenschaft **Name** in **SearchTextBox**.</span><span class="sxs-lookup"><span data-stu-id="1a08d-108">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="1a08d-109">Ziehen Sie ein <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular, das das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="1a08d-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="1a08d-110">Ändern Sie im Eigenschaftenfenster die Eigenschaft **Name** in **SearchButton**.</span><span class="sxs-lookup"><span data-stu-id="1a08d-110">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="1a08d-111">Ändern Sie die **Text** -Eigenschaft in **Search**.</span><span class="sxs-lookup"><span data-stu-id="1a08d-111">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="1a08d-112">Doppelklicken Sie auf das <xref:System.Windows.Forms.Button> -Steuerelement, um den Code-Editor zu öffnen, und fügen Sie dem `SearchButton_Click` -Ereignishandler den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="1a08d-112">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     <span data-ttu-id="1a08d-113">Ersetzen Sie *ProductsBindingSource* durch den Namen des der <xref:System.Windows.Forms.BindingSource> für Ihre <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, und Ersetzen Sie *"ProductID"* mit dem Namen des Felds, das Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="1a08d-113">Replace *ProductsBindingSource* with the name of the <xref:System.Windows.Forms.BindingSource> for your <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and replace *ProductID* with the name of the field that you want to search.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a08d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a08d-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="1a08d-115">Einführung in das DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1a08d-115">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="1a08d-116">Problembehandlung beim DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1a08d-116">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="1a08d-117">Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="1a08d-117">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
