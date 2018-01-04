---
title: "Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c1c11ca487003e57a499b3ff46178350e6aad404
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="10022-102">Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="10022-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="10022-103">Die `DataGridView` Steuerelement bietet zahlreiche Optionen für das Größenanpassungsverhalten seiner Spalten und Zeilen.</span><span class="sxs-lookup"><span data-stu-id="10022-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="10022-104">In der Regel `DataGridView` Größe Zellen nicht basierend auf deren Inhalt.</span><span class="sxs-lookup"><span data-stu-id="10022-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="10022-105">Stattdessen schneiden sie ausnahmslos anzeigen, die größer als die Zelle ist.</span><span class="sxs-lookup"><span data-stu-id="10022-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="10022-106">Wenn der Inhalt als Zeichenfolge angezeigt werden kann, durch die Zelle in einer QuickInfo angezeigt.</span><span class="sxs-lookup"><span data-stu-id="10022-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="10022-107">Standardmäßig können Benutzer ziehen, Zeilen-, Spalten- und Header Trennblättern mit der Maus, um weitere Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="10022-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="10022-108">Benutzer können auch einen Unterteiler automatisch die zugehörige Zeilen-, Spalten- oder Header Band an dessen Inhalt angepasst Größe doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="10022-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="10022-109">Die `DataGridView` gesteuert, Eigenschaften, Methoden und Ereignisse, mit denen Sie alle diese benutzergesteuerten Verhaltensweisen anpassen oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="10022-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="10022-110">Darüber hinaus können Sie programmgesteuert Größe Zeilen, Spalten und Header an ihren Inhalt angepasst, oder Sie können konfigurieren, um automatisch selbst angepasst werden, sobald Sie ihren Inhalt ändern.</span><span class="sxs-lookup"><span data-stu-id="10022-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="10022-111">Sie können auch konfigurieren, dass Spalten, um die verfügbare Breite des Steuerelements in acht Proportionen automatisch zu unterteilen, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="10022-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="10022-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="10022-112">In This Section</span></span>  
 [<span data-ttu-id="10022-113">Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="10022-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="10022-114">Beschreibt die Optionen für die größenanpassung von Zeilen, Spalten und Header.</span><span class="sxs-lookup"><span data-stu-id="10022-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="10022-115">Außerdem enthält Details zum Sizing-bezogene Eigenschaften und Methoden, und beschreibt allgemeine Verwendungsszenarien.</span><span class="sxs-lookup"><span data-stu-id="10022-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="10022-116">Spaltenfüllmodus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="10022-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="10022-117">Spaltenfüllmodus im Detail beschreibt und enthält Beispielcode, die Sie zum Experimentieren mit anderen Modi "und" Spaltenfüllmodus verwenden können.</span><span class="sxs-lookup"><span data-stu-id="10022-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="10022-118">Gewusst wie: Festlegen der Größenanpassungsmodi des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="10022-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="10022-119">Beschreibt, wie der Größenanpassungsmodi für allgemeine Zwecke zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="10022-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="10022-120">Gewusst wie: Programmgesteuertes Anpassen der Zellengröße an den Inhalt im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="10022-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="10022-121">Enthält Beispielcode, die Sie zum Experimentieren mit programmgesteuerten größenanpassung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="10022-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="10022-122">Gewusst wie: Automatisches Anpassen der Zellengröße bei Änderungen des Inhalts im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="10022-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="10022-123">Enthält Beispielcode, die Sie zum Experimentieren mit Modi zur Größenänderung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="10022-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="10022-124">Verweis</span><span class="sxs-lookup"><span data-stu-id="10022-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="10022-125">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="10022-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10022-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10022-126">See Also</span></span>  
 [<span data-ttu-id="10022-127">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="10022-127">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
