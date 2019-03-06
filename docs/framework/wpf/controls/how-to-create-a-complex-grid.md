---
title: 'Vorgehensweise: erstellen ein komplexes Rasters'
description: Ein Beispiel für das ein Grid-Steuerelement zu verwenden, um ein Layout erstellen, der einem Monatskalender ähnelt.
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: dd17dfeea85e2b404f7a284f93faceec63145b1f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355014"
---
# <a name="how-to-create-a-complex-grid"></a>Vorgehensweise: erstellen ein komplexes Rasters

Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Controls.Grid> Steuerelement ein Layout erstellen, der einem Monatskalender ähnelt.

## <a name="example"></a>Beispiel

Das folgende Beispiel definiert acht Zeilen und acht Spalten mithilfe der <xref:System.Windows.Controls.RowDefinition> und <xref:System.Windows.Controls.ColumnDefinition> Klassen. Er verwendet den <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> und <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> angefügten Eigenschaften zusammen mit <xref:System.Windows.Shapes.Rectangle> -Elemente, die den Hintergrund der einzelnen Spalten und Zeilen ausfüllen. Dieser Entwurf ist möglich, da mehr als ein Element vorhanden, in jeder Zelle in sein kann einer <xref:System.Windows.Controls.Grid>, ein grundlegender Unterschied zwischen <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Documents.Table>.

Im Beispiel wird die vertikale Farbverläufe <xref:System.Windows.Shapes.Shape.Fill%2A> Spalten und Zeilen, die die visuelle Darstellung und Lesbarkeit des Kalenders zu verbessern. Formatiert <xref:System.Windows.Controls.TextBlock> Elemente darstellen, die die Datumsangaben und die Tage der Woche. <xref:System.Windows.Controls.TextBlock> Elemente sind absolut positioniert in deren Zellen mithilfe der <xref:System.Windows.FrameworkElement.Margin%2A> -Eigenschaft und die Eigenschaften für die Ausrichtung, die innerhalb der Formatvorlage für die Anwendung definiert sind.

[!code-xaml[GridComplex#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

Die folgende Abbildung zeigt das resultierende Steuerelement, einem anpassbaren dar:

![Screenshot: das resultierende Steuerelement](././media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Übersicht über Panel-Elemente](panels-overview.md)
- [Übersicht über Tabellen](../advanced/table-overview.md)