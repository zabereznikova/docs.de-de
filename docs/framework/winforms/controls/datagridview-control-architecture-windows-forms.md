---
title: Architektur des DataGridView-Steuerelements (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 15d10ed2ec0bc78acfe887fe583d4850425eeab9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648106"
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="64dd6-102">Architektur des DataGridView-Steuerelements (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="64dd6-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="64dd6-103">Die <xref:System.Windows.Forms.DataGridView> Steuerelement und seinen verwandten Klassen dienen als ein flexibles, erweiterbares System zum Anzeigen und Bearbeiten von Tabellendaten.</span><span class="sxs-lookup"><span data-stu-id="64dd6-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="64dd6-104">Diese Klassen sind in enthalten die <xref:System.Windows.Forms?displayProperty=nameWithType> -Namespace, und sie sind alle mit dem Namen mit dem Präfix "DataGridView".</span><span class="sxs-lookup"><span data-stu-id="64dd6-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="64dd6-105">Architekturelemente</span><span class="sxs-lookup"><span data-stu-id="64dd6-105">Architecture Elements</span></span>  
 <span data-ttu-id="64dd6-106">Die primäre <xref:System.Windows.Forms.DataGridView> Assistentenklassen abgeleitet <xref:System.Windows.Forms.DataGridViewElement>.</span><span class="sxs-lookup"><span data-stu-id="64dd6-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="64dd6-107">Das folgende Objektmodell veranschaulicht die <xref:System.Windows.Forms.DataGridViewElement> Vererbungshierarchie.</span><span class="sxs-lookup"><span data-stu-id="64dd6-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 ![Diagramm, das die Hierarchie DataGridViewElement-Objektmodell veranschaulicht.](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 <span data-ttu-id="64dd6-109">Die <xref:System.Windows.Forms.DataGridViewElement> Klasse stellt einen Verweis auf das übergeordnete Element <xref:System.Windows.Forms.DataGridView> steuern und verfügt über eine <xref:System.Windows.Forms.DataGridViewElement.State%2A> -Eigenschaft, die einen Wert enthält, die eine Kombination von Werten aus darstellt. die <xref:System.Windows.Forms.DataGridViewElementStates> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="64dd6-109">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="64dd6-110">Die folgenden Abschnitte beschreiben die <xref:System.Windows.Forms.DataGridView> Assistentenklassen im Detail.</span><span class="sxs-lookup"><span data-stu-id="64dd6-110">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="64dd6-111">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="64dd6-111">DataGridViewElementStates</span></span>  
 <span data-ttu-id="64dd6-112">Die <xref:System.Windows.Forms.DataGridViewElementStates> Enumeration enthält die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="64dd6-112">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="64dd6-113">Die Werte dieser Enumeration können mit der bitweisen logischen Operatoren kombiniert werden also die <xref:System.Windows.Forms.DataGridViewElement.State%2A> Eigenschaft kann mehreren Zuständen gleichzeitig Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="64dd6-113">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="64dd6-114">Z. B. eine <xref:System.Windows.Forms.DataGridViewElement> gleichzeitig möglich <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, und <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span><span class="sxs-lookup"><span data-stu-id="64dd6-114">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="64dd6-115">Zellen und Bänder</span><span class="sxs-lookup"><span data-stu-id="64dd6-115">Cells and Bands</span></span>  
 <span data-ttu-id="64dd6-116">Die <xref:System.Windows.Forms.DataGridView> Steuerelement besteht aus zwei grundlegende Arten von Objekten: Zellen und Bänder.</span><span class="sxs-lookup"><span data-stu-id="64dd6-116">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="64dd6-117">Leiten Sie alle Zellen von der <xref:System.Windows.Forms.DataGridViewCell> Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="64dd6-117">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="64dd6-118">Die beiden Arten von Bändern, <xref:System.Windows.Forms.DataGridViewColumn> und <xref:System.Windows.Forms.DataGridViewRow>, beide leiten Sie von der <xref:System.Windows.Forms.DataGridViewBand> Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="64dd6-118">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="64dd6-119">Die <xref:System.Windows.Forms.DataGridView> -Steuerelement wirkt mit mehreren Klassen, jedoch die am häufigsten auftretenden <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, und <xref:System.Windows.Forms.DataGridViewRow>.</span><span class="sxs-lookup"><span data-stu-id="64dd6-119">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="64dd6-120">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="64dd6-120">DataGridViewCell</span></span>  
 <span data-ttu-id="64dd6-121">Die Zelle ist die grundlegende Einheit für die Interaktion der <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="64dd6-121">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="64dd6-122">Anzeige beruht auf Zellen, und die Dateneingabe wird häufig Zellen.</span><span class="sxs-lookup"><span data-stu-id="64dd6-122">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="64dd6-123">Sie Zugriff auf Zellen mithilfe der <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> Auflistung von der <xref:System.Windows.Forms.DataGridViewRow> -Klasse, und Sie können die ausgewählten Zellen zugreifen, indem Sie mit der <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> Auflistung von der <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="64dd6-123">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="64dd6-124">Das folgende Objektmodell veranschaulicht diese Verwendung sowie die <xref:System.Windows.Forms.DataGridViewCell> Vererbungshierarchie.</span><span class="sxs-lookup"><span data-stu-id="64dd6-124">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 ![Diagramm, das die Hierarchie der DataGridViewCell-Objektmodell veranschaulicht.](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 <span data-ttu-id="64dd6-126">Die <xref:System.Windows.Forms.DataGridViewCell> Typ ist eine abstrakte Basisklasse, von der alle Arten der Zelle abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="64dd6-126">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="64dd6-127"><xref:System.Windows.Forms.DataGridViewCell> und seinen abgeleiteten Typen sind nicht an Windows Forms-Steuerelemente, aber einige Windows Forms-Hoststeuerelemente.</span><span class="sxs-lookup"><span data-stu-id="64dd6-127"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="64dd6-128">Weiteren Bearbeitungsfunktionen unterstützt, die eine Zelle wird in der Regel von eines gehosteten Steuerelements behandelt.</span><span class="sxs-lookup"><span data-stu-id="64dd6-128">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="64dd6-129"><xref:System.Windows.Forms.DataGridViewCell> Objekte können nicht ihre eigenen Darstellung und das Zeichnen-Funktionen auf dieselbe Weise steuern wie Windows Forms-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="64dd6-129"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="64dd6-130">Stattdessen die <xref:System.Windows.Forms.DataGridView> ist verantwortlich für die Darstellung der <xref:System.Windows.Forms.DataGridViewCell> Objekte.</span><span class="sxs-lookup"><span data-stu-id="64dd6-130">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="64dd6-131">Sie können das Aussehen und Verhalten von Zellen erheblich beeinflussen, indem die Interaktion mit der <xref:System.Windows.Forms.DataGridView> Eigenschaften und Ereignisse des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="64dd6-131">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="64dd6-132">Wenn Sie über besondere Anforderungen für Anpassungen, die über die Funktionen der verfügen die <xref:System.Windows.Forms.DataGridView> -Steuerelement, können Sie eigene abgeleitete Klasse implementieren <xref:System.Windows.Forms.DataGridViewCell> oder eine ihrer untergeordneten Klassen.</span><span class="sxs-lookup"><span data-stu-id="64dd6-132">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="64dd6-133">Die folgende Liste enthält die von abgeleiteten Klassen <xref:System.Windows.Forms.DataGridViewCell>:</span><span class="sxs-lookup"><span data-stu-id="64dd6-133">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- <span data-ttu-id="64dd6-134">Die benutzerdefinierte Zellentypen</span><span class="sxs-lookup"><span data-stu-id="64dd6-134">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="64dd6-135">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="64dd6-135">DataGridViewColumn</span></span>  
 <span data-ttu-id="64dd6-136">Das Schema der <xref:System.Windows.Forms.DataGridView> angefügten Datenspeicher des Steuerelements, ausgedrückt in der <xref:System.Windows.Forms.DataGridView> des Steuerelements Spalten.</span><span class="sxs-lookup"><span data-stu-id="64dd6-136">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="64dd6-137">Sie erreichen die <xref:System.Windows.Forms.DataGridView> des Steuerelements Spalten mithilfe der <xref:System.Windows.Forms.DataGridView.Columns%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="64dd6-137">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="64dd6-138">Sie können die ausgewählten Spalten zugreifen, indem Sie mit der <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="64dd6-138">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="64dd6-139">Das folgende Objektmodell veranschaulicht diese Verwendung sowie die <xref:System.Windows.Forms.DataGridViewColumn> Vererbungshierarchie.</span><span class="sxs-lookup"><span data-stu-id="64dd6-139">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 ![Diagramm, das die Hierarchie DataGridViewColumn-Objektmodell veranschaulicht.](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 <span data-ttu-id="64dd6-141">Einige der wichtigsten Zellentypen verfügen über entsprechende Spaltentypen.</span><span class="sxs-lookup"><span data-stu-id="64dd6-141">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="64dd6-142">Diese stammen von der <xref:System.Windows.Forms.DataGridViewColumn> Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="64dd6-142">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="64dd6-143">Die folgende Liste enthält die von abgeleiteten Klassen <xref:System.Windows.Forms.DataGridViewColumn>:</span><span class="sxs-lookup"><span data-stu-id="64dd6-143">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- <span data-ttu-id="64dd6-144">Benutzerdefinierte Spaltentypen</span><span class="sxs-lookup"><span data-stu-id="64dd6-144">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="64dd6-145">Bearbeiten von DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="64dd6-145">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="64dd6-146">Zellen, die erweiterte Bearbeitungsfunktionen, in der Regel unterstützen, verwenden Sie ein gehostetes Steuerelement, das von einer Windows Forms-Steuerelement abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="64dd6-146">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="64dd6-147">Diese Steuerelemente implementieren, auch die <xref:System.Windows.Forms.IDataGridViewEditingControl> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="64dd6-147">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="64dd6-148">Das folgende Objektmodell veranschaulicht die Verwendung dieser Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="64dd6-148">The following object model illustrates the usage of these controls.</span></span>  
  
 ![Das Diagramm zeigt die Hierarchie DataGridView bearbeiten-Steuerelement-Objektmodell.](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 <span data-ttu-id="64dd6-150">Die folgenden Bearbeitungssteuerelemente sind im Lieferumfang der <xref:System.Windows.Forms.DataGridView> Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="64dd6-150">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="64dd6-151">Weitere Informationen zum Erstellen eigener Bearbeitungssteuerelemente, finden Sie unter [Vorgehensweise: Hosten von Steuerelementen in Windows Forms DataGridView-Zellen](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span><span class="sxs-lookup"><span data-stu-id="64dd6-151">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="64dd6-152">Die folgende Tabelle zeigt die Beziehung zwischen Zellentypen, Spaltentypen und Bearbeitung von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="64dd6-152">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="64dd6-153">Zellentyp</span><span class="sxs-lookup"><span data-stu-id="64dd6-153">Cell type</span></span>|<span data-ttu-id="64dd6-154">Gehostete Steuerelement</span><span class="sxs-lookup"><span data-stu-id="64dd6-154">Hosted control</span></span>|<span data-ttu-id="64dd6-155">Spaltentyp</span><span class="sxs-lookup"><span data-stu-id="64dd6-155">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="64dd6-156">n/v</span><span class="sxs-lookup"><span data-stu-id="64dd6-156">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="64dd6-157">n/v</span><span class="sxs-lookup"><span data-stu-id="64dd6-157">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="64dd6-158">n/v</span><span class="sxs-lookup"><span data-stu-id="64dd6-158">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="64dd6-159">n/v</span><span class="sxs-lookup"><span data-stu-id="64dd6-159">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="64dd6-160">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="64dd6-160">DataGridViewRow</span></span>  
 <span data-ttu-id="64dd6-161">Die <xref:System.Windows.Forms.DataGridViewRow> Klasse angezeigt, die Daten des Datensatzes aus den Daten Felder zu speichern, zu dem die <xref:System.Windows.Forms.DataGridView> Steuerelement angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="64dd6-161">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="64dd6-162">Sie können den Zugriff auf die <xref:System.Windows.Forms.DataGridView> des Steuerelements Zeilen mithilfe der <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="64dd6-162">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="64dd6-163">Sie können die ausgewählten Zeilen zugreifen, indem Sie mit der <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="64dd6-163">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="64dd6-164">Das folgende Objektmodell veranschaulicht diese Verwendung sowie die <xref:System.Windows.Forms.DataGridViewRow> Vererbungshierarchie.</span><span class="sxs-lookup"><span data-stu-id="64dd6-164">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 ![Diagramm, das die Hierarchie DataGridViewRow-Objektmodell veranschaulicht.](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 <span data-ttu-id="64dd6-166">Sie können Ihre eigenen Typen von Ableiten der <xref:System.Windows.Forms.DataGridViewRow> Klasse, obwohl dies in der Regel nicht notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="64dd6-166">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="64dd6-167">Die <xref:System.Windows.Forms.DataGridView> Steuerelement verfügt über mehrere zeilenbezogenen Ereignisse und Eigenschaften zum Anpassen des Verhaltens des seine <xref:System.Windows.Forms.DataGridViewRow> Objekte.</span><span class="sxs-lookup"><span data-stu-id="64dd6-167">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="64dd6-168">Wenn Sie aktivieren die <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> -Eigenschaft, eine spezielle Zeile für neue Zeilen hinzugefügt, die als letzte Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="64dd6-168">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="64dd6-169">Diese Zeile ist Teil der <xref:System.Windows.Forms.DataGridView.Rows%2A> -Auflistung, aber es verfügt über spezielle Funktionen, die möglicherweise Ihre Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="64dd6-169">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="64dd6-170">Weitere Informationen finden Sie unter [verwenden die Zeile für neue Datensätze im DataGridView-Steuerelement in Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="64dd6-170">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64dd6-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64dd6-171">See also</span></span>

- [<span data-ttu-id="64dd6-172">Übersicht über das DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="64dd6-172">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="64dd6-173">Anpassen des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64dd6-173">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="64dd6-174">Verwenden der Zeile für neue Datensätze im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64dd6-174">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
