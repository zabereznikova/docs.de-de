---
title: Übersicht über die Verwendung eines automatischen Layouts
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: 2fe473da3eeabef3852e3003e61b3b9604332855
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291268"
---
# <a name="use-automatic-layout-overview"></a>Übersicht über die Verwendung eines automatischen Layouts

In diesem Thema werden Richtlinien für Entwickler zum Schreiben von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen mit lokalisierbaren Benutzeroberflächen (User Interface, UIs) vorgestellt. In der Vergangenheit war die Lokalisierung einer Benutzeroberfläche ein zeitaufwändiger Prozess. Jede Sprache, für die die Benutzeroberfläche angepasst wurde, erforderte ein Pixel nach Pixel Anpassung. Heute mit dem richtigen Entwurfs-und richtigen Codierungsstandards kann UIs erstellt werden, sodass lokalisierungssoren weniger Größe und Neupositionierung haben. Der Ansatz zum Schreiben von Anwendungen, die einfacher geändert und neu positioniert werden können, wird als automatisches Layout bezeichnet und kann mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungsdesign erreicht werden.

<a name="advantages_of_autolayout"></a>

## <a name="advantages-of-using-automatic-layout"></a>Vorteile der Verwendung des automatischen Layouts

Da das Präsentationssystem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] leistungsstark und flexibel ist, bietet es die Möglichkeit, Elemente in einer Anwendung zu erstellen, die an die Anforderungen unterschiedlicher Sprachen angepasst werden können. Die folgende Liste hebt einige der Vorteile des automatischen Layouts hervor.

- Die Benutzeroberfläche wird in jeder Sprache gut angezeigt.

- Reduziert nach der Übersetzung des Text die Notwendigkeit der Anpassung von Position und Größe von Steuerelementen.

- Reduziert die Notwendigkeit zur Anpassung der Fenstergröße.

- Das Layout der Benutzeroberfläche wird in jeder beliebigen Sprache ordnungsgemäß

- Die Lokalisierung kann bis zu dem Punkt reduziert werden, dass sie nur wenig komplexer als eine Zeichenfolgeübersetzung ist.

<a name="autolayout_controls"></a>

## <a name="automatic-layout-and-controls"></a>Automatisches Layout und Steuerelemente

Das automatische Layout ermöglicht einer Anwendung die automatisch Anpassung der Größe eines Steuerelements. Beispielsweise kann ein Steuerelement so geändert werden, dass es die Länge einer Zeichenfolge aufnimmt. Diese Funktion ermöglicht Lokalisierern die Übersetzung der Zeichenfolge. Es ist nicht mehr notwendig, die Größe des Steuerelements an den übersetzten Text anzupassen. Im folgende Beispiel wird eine Schaltfläche mit englischen Inhalt erstellt.

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]

Alles, was Sie in diesem Beispiel tun müssen, um eine spanische Schaltfläche zu erstellen, ist das Ändern des Texts. Ein auf ein Objekt angewendeter

[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]

Die folgende Grafik zeigt die Ausgabe der Codebeispiele:

![Die gleiche Schaltfläche mit Text in unterschiedlichen Sprachen](./media/use-automatic-layout-overview/auto-resizable-button.png)

<a name="autolayout_coding"></a>

## <a name="automatic-layout-and-coding-standards"></a>Automatisches Layout und Codierungsstandards

Die Verwendung des automatischen Layoutansatzes erfordert eine Reihe von Codierungs-und Entwurfs Standards und Regeln, um eine vollständig lokalisierbare Benutzeroberfläche zu erstellen Die folgenden Richtlinien werden Ihnen bei der automatischen Layoutcodierung helfen .

**Keine absoluten Positionen verwenden**

- Verwenden Sie <xref:System.Windows.Controls.Canvas> nicht, da Elemente absolut positioniert werden.

- Verwenden Sie <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel> und <xref:System.Windows.Controls.Grid>, um Steuerelemente zu positionieren.

Eine Erläuterung zu den verschiedenen Arten von Panels finden Sie unter [Übersicht über Panels](../controls/panels-overview.md).

**Legen Sie keine festgelegte Größe für ein Fenster fest.**

- Verwenden Sie <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>. Zum Beispiel:

  [!code-xaml[LocalizationGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

**Hinzufügen einer <xref:System.Windows.FrameworkElement.FlowDirection%2A>**

- Fügen Sie dem Stamm Element der Anwendung eine <xref:System.Windows.FrameworkElement.FlowDirection%2A> hinzu.

  WPF bietet eine bequeme Möglichkeit zur Unterstützung von horizontalen, bidirektionalen und vertikalen Layouts. In Presentation Framework kann die <xref:System.Windows.FrameworkElement.FlowDirection%2A>-Eigenschaft verwendet werden, um das Layout zu definieren. Die Muster der Flussrichtung sind:Die flussrichtung Muster sind:

  - <xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) – horizontales Layout für Lateinisch, ostasiatisch usw.

  - <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RLTB) – bidirektional für Arabisch, Hebräisch usw.

**Verwenden von zusammengesetzten Schriftarten anstelle physischer Schriftarten**

- Bei zusammengesetzten Schriftarten muss die <xref:System.Windows.Controls.Control.FontFamily%2A>-Eigenschaft nicht lokalisiert werden.

- Entwickler können eine der folgenden Schriftarten verwenden oder ihre eigenen erstellen.

  - Globale Benutzeroberfläche
  - Global San Serif
  - Global Serif

**XML hinzufügen: lang**

- Fügen Sie das `xml:lang`-Attribut im Root-Element ihrer Benutzeroberfläche hinzu, z. b. `xml:lang="en-US"` für eine englische Anwendung.

- Da zusammengesetzte Schriftarten `xml:lang` verwenden, um zu bestimmen, welche Schriftart verwendet werden soll, legen Sie diese Eigenschaft fest, um mehrsprachige Szenarien

<a name="autolay_grids"></a>

## <a name="automatic-layout-and-grids"></a>Automatisches Layout und Raster

Das <xref:System.Windows.Controls.Grid>-Element ist für das automatische Layout nützlich, da es einem Entwickler ermöglicht, Elemente zu positionieren. Ein <xref:System.Windows.Controls.Grid>-Steuerelement ist in der Lage, mithilfe einer Spalten-und Zeilen Anordnung den verfügbaren Platz unter seinen untergeordneten Elementen zu verteilen. Die Benutzeroberflächen Elemente können mehrere Zellen umfassen, und es ist möglich, Raster in Raster zu haben. Raster sind nützlich, da Sie Ihnen ermöglichen, eine komplexe Benutzeroberfläche zu erstellen und zu positionieren. Im folgende Beispiel wird veranschaulicht, wie mit einem Raster einige Schaltflächen und Text positioniert werden. Beachten Sie, dass die Höhe und Breite der Zellen auf "<xref:System.Windows.GridUnitType.Auto>" festgelegt ist. Daher wird die Zelle, die die Schaltfläche mit einem Bild enthält, an das Bild angepasst.

[!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]

Die folgende Grafik zeigt die vom vorherigen Code erzeugten Raster.

![Raster Beispiel](./media/glob-grid.png "glob_grid") Raster

<a name="autolay_grids_issharedsizescope"></a>

## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a>Automatisches Layout und Raster mit der IsSharedSizeScope-Eigenschaft

Ein <xref:System.Windows.Controls.Grid>-Element ist in lokalisierbaren Anwendungen hilfreich, um Steuerelemente zu erstellen, die an den Inhalt angepasst werden. Manchmal ist es jedoch notwendig, dass Steuerelemente unabhängig vom Inhalt eine bestimmte Größe beibehalten. Beispielsweise sollen die Schaltflächen „OK“, „Abbrechen“ und „Durchsuchen“ wahrscheinlich nicht die Größe des Inhalts angepasst werden. In diesem Fall ist die angefügte <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType>-Eigenschaft für die gemeinsame Nutzung derselben Größe in mehreren Raster Elementen nützlich. Im folgenden Beispiel wird veranschaulicht, wie Spalten-und Zeilen Größendaten zwischen mehreren <xref:System.Windows.Controls.Grid>-Elementen gemeinsam genutzt werden.

[!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]

> [!NOTE]
> Das Codebeispiel für den gesamten Code finden Sie unter [Freigeben von Größen Eigenschaften zwischen](../controls/how-to-share-sizing-properties-between-grids.md)Rastern.

## <a name="see-also"></a>Siehe auch

- [Globalisierung für WPF](globalization-for-wpf.md)
- [Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche](how-to-use-automatic-layout-to-create-a-button.md)
- [Verwenden eines Rasters für automatisches Layout](how-to-use-a-grid-for-automatic-layout.md)
