---
title: Übersicht über die Verwendung eines automatischen Layouts
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: a43b3c0e008025171e3b1fdeba3bc514d01e28c8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43542623"
---
# <a name="use-automatic-layout-overview"></a>Übersicht über die Verwendung eines automatischen Layouts
In diesem Thema werden Richtlinien für Entwickler zum Schreiben von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] -Anwendungen mit lokalisierbarem [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]. In der Vergangenheit nahm die Lokalisierung von einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] wurde viel Zeit in Anspruch. Jede Sprache, die die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] wurde für eine pixelweise Anpassung erforderlich. Sofort mit dem richtigen Entwurfs- und Codierungsstandards können [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] konstruiert werden kann, sodass Lokalisierer Ändern der Größe und die neupositionierung vorhanden sind. Der Ansatz zum Schreiben von Anwendungen, die einfacher geändert und neu positioniert werden können ist als automatisches Layout bezeichnet und kann erreicht werden, indem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungsentwurf.  
  
<a name="advantages_of_autolayout"></a>   
## <a name="advantages-of-using-automatic-layout"></a>Vorteile der Verwendung des automatischen Layouts  
 Da die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Präsentationssystem ist leistungsfähiger und flexibler, es bietet die Möglichkeit, Elemente in einer Anwendung, die die Anforderungen für verschiedene Sprachen angepasst werden kann. Die folgende Liste hebt einige der Vorteile des automatischen Layouts hervor.  
  
-   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] kann in jeder Sprache gut angezeigt werden.  
  
-   Reduziert nach der Übersetzung des Text die Notwendigkeit der Anpassung von Position und Größe von Steuerelementen.  
  
-   Reduziert die Notwendigkeit zur Anpassung der Fenstergröße.  
  
-   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Layout kann in jede beliebige Sprache korrekt gerendert werden.  
  
-   Die Lokalisierung kann bis zu dem Punkt reduziert werden, dass sie nur wenig komplexer als eine Zeichenfolgeübersetzung ist.  
  
<a name="autolayout_controls"></a>   
## <a name="automatic-layout-and-controls"></a>Automatisches Layout und Steuerelemente  
 Das automatische Layout ermöglicht einer Anwendung die automatisch Anpassung der Größe eines Steuerelements. Beispielsweise kann ein Steuerelement so geändert werden, dass es die Länge einer Zeichenfolge aufnimmt. Diese Funktion ermöglicht Lokalisierern die Übersetzung der Zeichenfolge. Es ist nicht mehr notwendig, die Größe des Steuerelements an den übersetzten Text anzupassen. Im folgende Beispiel wird eine Schaltfläche mit englischen Inhalt erstellt.  
  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 Alles, was Sie in diesem Beispiel tun müssen, um eine spanische Schaltfläche zu erstellen, ist das Ändern des Texts. Ein auf ein Objekt angewendeter  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 Die folgende Grafik zeigt die Ausgabe der Codebeispiele.  
  
 ![Die gleiche Schaltfläche mit Text in unterschiedlichen Sprachen](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Schaltfläche zur automatischen Größenanpassung  
  
<a name="autolayout_coding"></a>   
## <a name="automatic-layout-and-coding-standards"></a>Automatisches Layout und Codierungsstandards  
 Verwenden des automatischen layoutansatzes erfordert einen Satz von Codierungs- und Entwurfsstandards und Regeln, um eine vollständig lokalisierbare erzeugen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Die folgenden Richtlinien werden Ihnen bei der automatischen Layoutcodierung helfen .  
  
| Codierungsstandards | Beschreibung |
| ---------------------- | ----------------- |
| Verwenden Sie keine absoluten Positionen. | <ul><li>Verwenden Sie keine <xref:System.Windows.Controls.Canvas> , weil dieses Elemente absolut positioniert.</li><li>Verwendung <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, und <xref:System.Windows.Controls.Grid> um Steuerelemente zu positionieren.</li><li>Weitere Informationen zu verschiedenen Bereichen, finden Sie unter [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</li></ul> |
| Legen Sie keine feste Größe für ein Fenster fest. | – Verwenden Sie <xref:System.Windows.Window.SizeToContent%2A>.<br />Zum Beispiel:<br /><br /> [!code-xaml[LocalizationGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)] |
| Fügen Sie ein <xref:System.Windows.FrameworkElement.FlowDirection%2A> hinzu. | <ul><li>Hinzufügen einer <xref:System.Windows.FrameworkElement.FlowDirection%2A> auf das Stammelement der Anwendung.</li><li>WPF bietet eine praktische Möglichkeit zur Unterstützung von horizontalen, bidirektionalen und vertikalen Layouts. In Präsentationsframework das <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft kann verwendet werden, um das Layout zu definieren. Die Muster der Flussrichtung sind:Die flussrichtung Muster sind:<br /><br /> <ul><li><xref:System.Windows.FlowDirection.LeftToRight> (LrTb) — horizontales Layout für Latein, Ostasiatisch usw.</li><li><xref:System.Windows.FlowDirection.RightToLeft> (RlTb) — bidirektional für Arabisch, Hebräisch und So weiter.</li></ul></li></ul> |
| Verwenden Sie zusammengesetzte Schriftarten anstelle von physischen Schriftarten. | <ul><li>Bei zusammengesetzten Schriftarten der <xref:System.Windows.Controls.Control.FontFamily%2A> Eigenschaft muss nicht lokalisiert werden soll.</li><li>Entwickler können eine der folgenden Schriftarten verwenden oder ihre eigenen erstellen.<br /><br /> <ul><li>Globale Benutzeroberfläche</li><li>Global San Serif</li><li>Global Serif</li></ul></li></ul> |
| Fügen Sie xml:lang hinzu. | <ul><li>Hinzufügen der `xml:lang` -Attribut in das Stammelement Ihrer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], z. B. `xml:lang="en-US"` für eine englische Anwendung.</li><li>Da zusammengesetzte Schriftarten `xml:lang` um zu bestimmen, welche Schriftart verwendet, legen Sie diese Eigenschaft zur Unterstützung von mehrsprachigen Szenarios.</li></ul> |
  
<a name="autolay_grids"></a>   
## <a name="automatic-layout-and-grids"></a>Automatisches Layout und Raster  
 Die <xref:System.Windows.Controls.Grid> -Element eignet sich für automatisches Layout, da es die Positionierung von Elementen ermöglicht. Ein <xref:System.Windows.Controls.Grid> Steuerelement ist in der Lage, den verfügbaren Platz auf seine untergeordneten Elemente, die mit einer Spalten- und zeilenanordnung zu verteilen. Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente können mehrere Zellen umfassen, und es ist möglich, verschachtelte Raster aufweisen. Raster sind sehr hilfreich, da sie Ihnen ermöglichen das Erstellen und positionieren Sie komplexe [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Im folgende Beispiel wird veranschaulicht, wie mit einem Raster einige Schaltflächen und Text positioniert werden. Beachten Sie, die die Höhe und Breite der Zellen, um festgelegt werden <xref:System.Windows.GridUnitType.Auto>daher die Zelle mit der Schaltfläche mit einem Bild passt, das Bild angepasst.  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 Die folgende Grafik zeigt die vom vorherigen Code erzeugten Raster.  
  
 ![Rasterbeispiel](../../../../docs/framework/wpf/advanced/media/glob-grid.png "Glob_grid")  
Raster  
  
<a name="autolay_grids_issharedsizescope"></a>   
## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a>Automatisches Layout und Raster mit der IsSharedSizeScope-Eigenschaft  
 Ein <xref:System.Windows.Controls.Grid> Element ist nützlich in lokalisierbaren Anwendungen um Steuerelemente zu erstellen, die an Inhalt anpassen. Manchmal ist es jedoch notwendig, dass Steuerelemente unabhängig vom Inhalt eine bestimmte Größe beibehalten. Beispielsweise sollen die Schaltflächen „OK“, „Abbrechen“ und „Durchsuchen“ wahrscheinlich nicht die Größe des Inhalts angepasst werden. In diesem Fall die <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> angefügte Eigenschaft ist nützlich für dieselbe Größe in mehreren Rasterelementen. Im folgende Beispiel wird veranschaulicht, wie Spalten- und Zeilengröße zwischen mehreren Teilen <xref:System.Windows.Controls.Grid> Elemente.  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 **Beachten Sie** das vollständige Codebeispiel finden Sie unter [Freigabe Sizing Eigenschaften zwischen Grids](../../../../docs/framework/wpf/controls/how-to-share-sizing-properties-between-grids.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Globalisierung für WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)  
 [Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)  
 [Verwenden eines Rasters für automatisches Layout](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
