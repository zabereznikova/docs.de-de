---
title: "Standardfunktionalität des DataGridView-Steuerelements von Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d6b15085c301f074ef6fcf9e60a75299c4b245b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c2bca-102">Standardfunktionalität des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c2bca-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c2bca-103">Windows Forms <xref:System.Windows.Forms.DataGridView> Steuerelement bietet Benutzern eine beträchtliche Menge an Standardeinstellung Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="c2bca-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="c2bca-104">Standardfunktionen</span><span class="sxs-lookup"><span data-stu-id="c2bca-104">Default Functionality</span></span>  
 <span data-ttu-id="c2bca-105">Wird standardmäßig ein <xref:System.Windows.Forms.DataGridView> Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="c2bca-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <span data-ttu-id="c2bca-106">Zeigt automatisch Spaltenüberschriften und Zeilenüberschriften, die sichtbar bleiben, wenn die Tabelle vertikal einen Bildlauf durchführt.</span><span class="sxs-lookup"><span data-stu-id="c2bca-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
-   <span data-ttu-id="c2bca-107">Verfügt über einen Zeilenkopf, der einen Auswahlindikator für die aktuelle Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="c2bca-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
-   <span data-ttu-id="c2bca-108">Verfügt über ein Auswahlrechteck in der ersten Zelle ein.</span><span class="sxs-lookup"><span data-stu-id="c2bca-108">Has a selection rectangle in the first cell.</span></span>  
  
-   <span data-ttu-id="c2bca-109">Enthält Spalten, die automatisch angepasst werden können, wenn der Benutzer die Spaltenunterteiler doppelklickt.</span><span class="sxs-lookup"><span data-stu-id="c2bca-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
-   <span data-ttu-id="c2bca-110">Automatisch visuelle Stile unter Windows XP und Windows Server 2003-Produktfamilie unterstützt bei der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode wird aufgerufen, aus der Anwendungsverzeichnis `Main` Methode.</span><span class="sxs-lookup"><span data-stu-id="c2bca-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="c2bca-111">Darüber hinaus den Inhalt einer <xref:System.Windows.Forms.DataGridView> -Steuerelement standardmäßig bearbeitet werden kann:</span><span class="sxs-lookup"><span data-stu-id="c2bca-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
-   <span data-ttu-id="c2bca-112">Wenn der Benutzer doppelklickt oder in einer Zelle F2 drückt, wird das Steuerelement automatisch versetzt die Zelle in den Bearbeitungsmodus, und aktualisiert den Inhalt der Zelle als vom Benutzer eingegebenen.</span><span class="sxs-lookup"><span data-stu-id="c2bca-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
-   <span data-ttu-id="c2bca-113">Wenn der Benutzer einen Bildlauf bis zum Ende des Rasters durchführt, wird der Benutzer angezeigt, dass eine Zeile für neue Datensätze hinzufügen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c2bca-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="c2bca-114">Wenn der Benutzer diese Zeile klickt, wird eine neue Zeile hinzugefügt, um die <xref:System.Windows.Forms.DataGridView> Steuerelement mit Standardwerten.</span><span class="sxs-lookup"><span data-stu-id="c2bca-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="c2bca-115">Wenn der Benutzer die ESC-Taste drückt, verschwindet dieser neuen Zeile auf.</span><span class="sxs-lookup"><span data-stu-id="c2bca-115">When the user presses ESC, this new row disappears.</span></span>  
  
-   <span data-ttu-id="c2bca-116">Wenn der Benutzer auf einen Zeilenheader klickt, wird die gesamte Zeile ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="c2bca-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="c2bca-117">Beim Binden einer <xref:System.Windows.Forms.DataGridView> Steuerelement mit einer Datenquelle durch Festlegen seiner <xref:System.Windows.Forms.DataGridView.DataSource%2A> -Eigenschaft, die das Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="c2bca-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
-   <span data-ttu-id="c2bca-118">Verwendet automatisch die Namen der Spalten der Datenquelle, wie der Text der Spaltenüberschrift.</span><span class="sxs-lookup"><span data-stu-id="c2bca-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
-   <span data-ttu-id="c2bca-119">Wird mit dem Inhalt der Datenquelle aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="c2bca-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="c2bca-120"><xref:System.Windows.Forms.DataGridView>Spalten werden für jede Spalte in der Datenquelle automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="c2bca-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
-   <span data-ttu-id="c2bca-121">Erstellt eine Zeile für jede sichtbare Zeile in der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="c2bca-121">Creates a row for each visible row in the table.</span></span>  
  
-   <span data-ttu-id="c2bca-122">Automatisch sortiert die Zeilen basierend auf den zugrunde liegenden Daten, wenn der Benutzer auf einen Spaltenheader klickt.</span><span class="sxs-lookup"><span data-stu-id="c2bca-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2bca-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2bca-123">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="c2bca-124">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c2bca-124">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
