---
title: Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: e1fa2d57cfb2cd374d691fe03a0e0bdbd3ad7141
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903187"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="866cd-102">Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="866cd-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="866cd-103">Die `DataGridView` Steuerelement bietet zahlreiche Optionen für das Größenanpassungsverhalten der Spalten und Zeilen.</span><span class="sxs-lookup"><span data-stu-id="866cd-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="866cd-104">In der Regel `DataGridView` passen Sie Zellen werden nicht basierend auf deren Inhalte.</span><span class="sxs-lookup"><span data-stu-id="866cd-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="866cd-105">Stattdessen schneiden sie jede Anzeigewert, der größer als die Zelle ist.</span><span class="sxs-lookup"><span data-stu-id="866cd-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="866cd-106">Wenn der Inhalt als Zeichenfolge angezeigt werden kann, von die Zelle in einer QuickInfo angezeigt.</span><span class="sxs-lookup"><span data-stu-id="866cd-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="866cd-107">Standardmäßig können Benutzer ziehen, Zeilen-, Spalten- und Headerunterteiler mit der Maus, um weitere Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="866cd-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="866cd-108">Benutzer können auch einen Unterteiler automatisch das zugeordnete Zeilen-, Spalten- oder Header Band entsprechend seines Inhalts ändern doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="866cd-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="866cd-109">Die `DataGridView` -Steuerelement bietet Eigenschaften, Methoden und Ereignisse, mit denen Sie anpassen oder deaktivieren alle diese Verhaltensweisen Benutzer gesteuert.</span><span class="sxs-lookup"><span data-stu-id="866cd-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="866cd-110">Darüber hinaus können Sie programmgesteuert Größe Zeilen, Spalten und Header an ihren Inhalt angepasst, oder Sie können konfigurieren, um die Größe automatisch selbst wenn deren Inhalt ändern.</span><span class="sxs-lookup"><span data-stu-id="866cd-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="866cd-111">Sie können auch konfigurieren, dass Spalten, um die verfügbare Breite des Steuerelements in Proportionen automatisch zu unterteilen, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="866cd-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="866cd-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="866cd-112">In This Section</span></span>  
 [<span data-ttu-id="866cd-113">Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="866cd-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="866cd-114">Beschreibt die Optionen für die größenanpassung von Zeilen, Spalten und Header.</span><span class="sxs-lookup"><span data-stu-id="866cd-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="866cd-115">Außerdem enthält Details zu größenanpassung-bezogene Eigenschaften und Methoden und beschreibt allgemeine Verwendungsszenarien kennen.</span><span class="sxs-lookup"><span data-stu-id="866cd-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="866cd-116">Spaltenfüllmodus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="866cd-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="866cd-117">Spaltenfüllmodus im Detail beschreibt und enthält Beispielcode, mit denen Sie mit Spaltenfüllmodus und andere Modi zu experimentieren.</span><span class="sxs-lookup"><span data-stu-id="866cd-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="866cd-118">Vorgehensweise: Festlegen der Größenanpassungsmodi des DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="866cd-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="866cd-119">Beschreibt, wie der Größenanpassungsmodi für allgemeine Zwecke zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="866cd-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="866cd-120">Vorgehensweise: Programmgesteuertes Ändern der Größe Zellen an Inhalt im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="866cd-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="866cd-121">Enthält Beispielcode, mit denen Sie experimentieren Sie mit programmgesteuerten Größenänderung.</span><span class="sxs-lookup"><span data-stu-id="866cd-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="866cd-122">Vorgehensweise: Größe automatisch Zellen aus, wenn Inhalt geändert wird, in das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="866cd-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="866cd-123">Enthält Beispielcode, die Sie verwenden können, um mit automatischen Größenanpassungsmodi zu experimentieren.</span><span class="sxs-lookup"><span data-stu-id="866cd-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="866cd-124">Referenz</span><span class="sxs-lookup"><span data-stu-id="866cd-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="866cd-125">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="866cd-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="866cd-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="866cd-126">See also</span></span>

- [<span data-ttu-id="866cd-127">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="866cd-127">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
