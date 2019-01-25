---
title: Standardfunktionalität des DataGridView-Steuerelements von Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: 1b67fa4da987778b08bad59d2e2829d0a974512a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710559"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="fd2be-102">Standardfunktionalität des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd2be-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fd2be-103">Die Windows-Formulare <xref:System.Windows.Forms.DataGridView> Steuerelement bietet Benutzern eine beträchtliche Menge an Standardfunktionen.</span><span class="sxs-lookup"><span data-stu-id="fd2be-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="fd2be-104">Standardfunktionen</span><span class="sxs-lookup"><span data-stu-id="fd2be-104">Default Functionality</span></span>  
 <span data-ttu-id="fd2be-105">Standardmäßig eine <xref:System.Windows.Forms.DataGridView> Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="fd2be-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <span data-ttu-id="fd2be-106">Zeigt automatisch Spaltenüberschriften und Zeilenüberschriften, die sichtbar bleiben, wie vertikalem der Tabelle Bildlauf an.</span><span class="sxs-lookup"><span data-stu-id="fd2be-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
-   <span data-ttu-id="fd2be-107">Verfügt über einen Zeilenkopf, der einen Auswahlindikator für die aktuelle Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="fd2be-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
-   <span data-ttu-id="fd2be-108">Verfügt über ein Auswahlrechteck in der ersten Zelle ein.</span><span class="sxs-lookup"><span data-stu-id="fd2be-108">Has a selection rectangle in the first cell.</span></span>  
  
-   <span data-ttu-id="fd2be-109">Enthält Spalten, die automatisch geändert werden können, wenn der Benutzer die Spaltenunterteiler doppelklickt.</span><span class="sxs-lookup"><span data-stu-id="fd2be-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
-   <span data-ttu-id="fd2be-110">Visuelle Stile automatisch auf Windows XP und Windows Server 2003-Produktfamilie unterstützt bei der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode wird aufgerufen, von der Anwendung `Main` Methode.</span><span class="sxs-lookup"><span data-stu-id="fd2be-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="fd2be-111">Darüber hinaus den Inhalt einer <xref:System.Windows.Forms.DataGridView> -Steuerelement standardmäßig bearbeitet werden kann:</span><span class="sxs-lookup"><span data-stu-id="fd2be-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
-   <span data-ttu-id="fd2be-112">Wenn der Benutzer doppelklickt, oder drücken F2 in einer Zelle, die Zelle in den Bearbeitungsmodus versetzt das Steuerelement automatisch und aktualisiert den Inhalt der Zelle, wenn der Benutzer eingibt.</span><span class="sxs-lookup"><span data-stu-id="fd2be-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
-   <span data-ttu-id="fd2be-113">Wenn der Benutzer einen Bildlauf bis zum Ende des Rasters durchführt, wird der Benutzer finden Sie, dass eine Zeile für neue Datensätze hinzufügen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fd2be-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="fd2be-114">Wenn der Benutzer diese Zeile klickt, wird eine neue Zeile hinzugefügt, um die <xref:System.Windows.Forms.DataGridView> Steuerelement, mit Standardwerten.</span><span class="sxs-lookup"><span data-stu-id="fd2be-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="fd2be-115">Wenn der Benutzer die ESC-Taste drückt, wird nicht mehr dieser neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="fd2be-115">When the user presses ESC, this new row disappears.</span></span>  
  
-   <span data-ttu-id="fd2be-116">Wenn der Benutzer einen Zeilenkopf klickt, wird die gesamte Zeile ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="fd2be-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="fd2be-117">Beim Binden einer <xref:System.Windows.Forms.DataGridView> Steuerelement mit einer Datenquelle durch Festlegen seiner <xref:System.Windows.Forms.DataGridView.DataSource%2A> -Eigenschaft, die das Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="fd2be-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
-   <span data-ttu-id="fd2be-118">Verwendet automatisch die Namen der Spalten für die Datenquelle, als den Spaltenkopftext.</span><span class="sxs-lookup"><span data-stu-id="fd2be-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
-   <span data-ttu-id="fd2be-119">Wird mit dem Inhalt der Datenquelle aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="fd2be-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="fd2be-120"><xref:System.Windows.Forms.DataGridView> Spalten werden für jede Spalte in der Datenquelle automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="fd2be-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
-   <span data-ttu-id="fd2be-121">Erstellt eine Zeile für jede sichtbare Zeile in der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="fd2be-121">Creates a row for each visible row in the table.</span></span>  
  
-   <span data-ttu-id="fd2be-122">Automatisch sortiert die Zeilen basierend auf den zugrunde liegenden Daten, wenn der Benutzer einen Spaltenheader klickt.</span><span class="sxs-lookup"><span data-stu-id="fd2be-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd2be-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd2be-123">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="fd2be-124">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fd2be-124">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
