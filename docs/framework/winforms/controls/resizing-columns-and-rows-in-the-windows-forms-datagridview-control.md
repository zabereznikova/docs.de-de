---
title: Ändern der Größe von Spalten und Zeilen im DataGridView-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: 8f8394a837ccc11c469f9ad4feeb60464d0014fe
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742416"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="4f682-102">Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f682-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4f682-103">Das `DataGridView`-Steuerelement bietet zahlreiche Optionen zum Anpassen des Größen Anpassungs Verhaltens der Spalten und Zeilen.</span><span class="sxs-lookup"><span data-stu-id="4f682-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="4f682-104">In der Regel werden `DataGridView` Zellen nicht auf Grundlage ihres Inhalts angepasst.</span><span class="sxs-lookup"><span data-stu-id="4f682-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="4f682-105">Stattdessen wird jeder Anzeige Wert, der größer ist als die Zelle, zugeschnitten.</span><span class="sxs-lookup"><span data-stu-id="4f682-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="4f682-106">Wenn der Inhalt als Zeichenfolge angezeigt werden kann, zeigt die Zelle ihn in einer QuickInfo an.</span><span class="sxs-lookup"><span data-stu-id="4f682-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="4f682-107">Standardmäßig können Benutzer Zeilen-, Spalten-und Header Teiler mit der Maus ziehen, um weitere Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4f682-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="4f682-108">Benutzer können auch auf einen unter Teiler doppelklicken, um die zugehörige Zeile, Spalte oder das Header Band basierend auf dem Inhalt automatisch zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4f682-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="4f682-109">Das `DataGridView`-Steuerelement stellt Eigenschaften, Methoden und Ereignisse bereit, mit denen Sie alle diese vom Benutzer gerichteten Verhalten anpassen oder deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="4f682-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="4f682-110">Darüber hinaus können Sie die Größe von Zeilen, Spalten und Headern Programm gesteuert ändern, damit Sie an ihren Inhalt angepasst werden, oder Sie können Sie so konfigurieren, dass Sie sich automatisch ändern, wenn sich Ihre Inhalte ändern.</span><span class="sxs-lookup"><span data-stu-id="4f682-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="4f682-111">Sie können auch Spalten konfigurieren, um die verfügbare Breite des Steuer Elements in von Ihnen angegebenen Proportionen automatisch aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="4f682-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f682-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4f682-112">In This Section</span></span>  
 [<span data-ttu-id="4f682-113">Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f682-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4f682-114">Beschreibt die Optionen zum Anpassen der Größe von Zeilen, Spalten und Headern.</span><span class="sxs-lookup"><span data-stu-id="4f682-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="4f682-115">Bietet auch Details zu Größen bezogenen Eigenschaften und Methoden und beschreibt häufige Verwendungs Szenarien.</span><span class="sxs-lookup"><span data-stu-id="4f682-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="4f682-116">Spaltenfüllmodus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f682-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4f682-117">Beschreibt den Spalten Füll Modus ausführlich und bietet Demonstrations Code, den Sie verwenden können, um mit dem Spalten Füll Modus und anderen Modi zu experimentieren.</span><span class="sxs-lookup"><span data-stu-id="4f682-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="4f682-118">Gewusst wie: Festlegen der Größenanpassungsmodi des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f682-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4f682-119">Beschreibt, wie die Größen Anpassungs Modi für allgemeine Zwecke konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4f682-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="4f682-120">Gewusst wie: Programmgesteuertes Anpassen der Zellengröße an den Inhalt im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f682-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="4f682-121">Bietet Demonstrations Code, den Sie verwenden können, um mit der programmatischen Größe zu experimentieren.</span><span class="sxs-lookup"><span data-stu-id="4f682-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="4f682-122">Gewusst wie: Automatisches Anpassen der Zellengröße bei Änderungen des Inhalts im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f682-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="4f682-123">Bietet Demonstrations Code, den Sie verwenden können, um mit automatischen Größen Anpassungs Modi zu experimentieren.</span><span class="sxs-lookup"><span data-stu-id="4f682-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4f682-124">Verweis</span><span class="sxs-lookup"><span data-stu-id="4f682-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="4f682-125">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4f682-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f682-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f682-126">See also</span></span>

- [<span data-ttu-id="4f682-127">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4f682-127">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
