---
title: 'Vorgehensweise: erstellen ein komplexes Rasters'
description: Ein Beispiel für das ein Grid-Steuerelement zu verwenden, um ein Layout erstellen, der einem Monatskalender ähnelt.
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: e2356113457e8c9a6737132e9779e49c05a23d77
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199980"
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="3f1a2-103">Vorgehensweise: erstellen ein komplexes Rasters</span><span class="sxs-lookup"><span data-stu-id="3f1a2-103">How to create a complex Grid</span></span>

<span data-ttu-id="3f1a2-104">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Controls.Grid> Steuerelement ein Layout erstellen, der einem Monatskalender ähnelt.</span><span class="sxs-lookup"><span data-stu-id="3f1a2-104">This example shows how to use a <xref:System.Windows.Controls.Grid> control to create a layout that looks like a monthly calendar.</span></span>

## <a name="example"></a><span data-ttu-id="3f1a2-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f1a2-105">Example</span></span>

<span data-ttu-id="3f1a2-106">Das folgende Beispiel definiert acht Zeilen und acht Spalten mithilfe der <xref:System.Windows.Controls.RowDefinition> und <xref:System.Windows.Controls.ColumnDefinition> Klassen.</span><span class="sxs-lookup"><span data-stu-id="3f1a2-106">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="3f1a2-107">Er verwendet den <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> und <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> angefügten Eigenschaften zusammen mit <xref:System.Windows.Shapes.Rectangle> -Elemente, die den Hintergrund der einzelnen Spalten und Zeilen ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="3f1a2-107">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="3f1a2-108">Dieser Entwurf ist möglich, da mehr als ein Element vorhanden, in jeder Zelle in sein kann einer <xref:System.Windows.Controls.Grid>, ein grundlegender Unterschied zwischen <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Documents.Table>.</span><span class="sxs-lookup"><span data-stu-id="3f1a2-108">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>

<span data-ttu-id="3f1a2-109">Im Beispiel wird die vertikale Farbverläufe <xref:System.Windows.Shapes.Shape.Fill%2A> Spalten und Zeilen, die die visuelle Darstellung und Lesbarkeit des Kalenders zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="3f1a2-109">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="3f1a2-110">Formatiert <xref:System.Windows.Controls.TextBlock> Elemente darstellen, die die Datumsangaben und die Tage der Woche.</span><span class="sxs-lookup"><span data-stu-id="3f1a2-110">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="3f1a2-111"><xref:System.Windows.Controls.TextBlock> Elemente sind absolut positioniert in deren Zellen mithilfe der <xref:System.Windows.FrameworkElement.Margin%2A> -Eigenschaft und die Eigenschaften für die Ausrichtung, die innerhalb der Formatvorlage für die Anwendung definiert sind.</span><span class="sxs-lookup"><span data-stu-id="3f1a2-111"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>

[!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

<span data-ttu-id="3f1a2-112">Die folgende Abbildung zeigt das resultierende Steuerelement, einem anpassbaren dar:</span><span class="sxs-lookup"><span data-stu-id="3f1a2-112">The following image shows the resulting control, a customizable calendar:</span></span>

![Screenshot: das resultierende Steuerelement](./media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a><span data-ttu-id="3f1a2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f1a2-114">See also</span></span>

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [<span data-ttu-id="3f1a2-115">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="3f1a2-115">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="3f1a2-116">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="3f1a2-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="3f1a2-117">Übersicht über Tabellen</span><span class="sxs-lookup"><span data-stu-id="3f1a2-117">Table Overview</span></span>](../advanced/table-overview.md)