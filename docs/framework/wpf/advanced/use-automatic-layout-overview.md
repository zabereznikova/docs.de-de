---
title: "Übersicht über die Verwendung eines automatischen Layouts"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 75066b59d0f3a686c66fdbdd187ba4c18e786e6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="use-automatic-layout-overview"></a>Übersicht über die Verwendung eines automatischen Layouts
Dieses Thema enthält Richtlinien für Entwickler zum Schreiben [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungen in lokalisierbare [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]. In der Vergangenheit Lokalisierung von einem [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] wurde eine Zeit in Anspruch. Jede Sprache, die die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] angepasst wurde, für eine Anpassung x Pixel erforderlich. Heute mit der rechten Entwurf und rechts Codierungsstandards, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] konstruiert werden kann, sodass Lokalisierungsexperten kleiner hierzu neu positionieren und ihre Größe haben. Der Ansatz zum Schreiben von Anwendungen, die leichter dessen Größe geändert wurde und neu positioniert werden können Automatisches Layout aufgerufen wird, und kann erreicht werden, indem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungsentwurf.  
  
<a name="advantages_of_autolayout"></a>   
## <a name="advantages-of-using-automatic-layout"></a>Vorteile der Verwendung des automatischen Layouts  
 Da die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Präsentation leistungsstark und flexibel, werden diese bietet die Möglichkeit, Layoutelemente in einer Anwendung, die entsprechend die Anforderungen der verschiedenen Sprachen angepasst werden kann. Die folgende Liste hebt einige der Vorteile des automatischen Layouts hervor.  
  
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
 Mit dem Automatisches Layoutansatz erfordert einen Satz von Schreiben von Code und Entwurf Standards und Regeln eine vollständig lokalisiert erzeugt [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Die folgenden Richtlinien werden Ihnen bei der automatischen Layoutcodierung helfen .  
  
|Codierungsstandards|Beschreibung|  
|----------------------|-----------------|  
|Verwenden Sie keine absoluten Positionen.|-Verwenden Sie keine <xref:System.Windows.Controls.Canvas> weil Elemente absolut positioniert.<br />– Verwenden Sie <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, und <xref:System.Windows.Controls.Grid> um Steuerelemente zu positionieren.<br />-Weitere Informationen zu den verschiedenen Typen von Bereichen, finden Sie unter [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).|  
|Legen Sie keine feste Größe für ein Fenster fest.|– Verwenden Sie <xref:System.Windows.Window.SizeToContent%2A>.<br />-Zum Beispiel:<br /><br /> [!code-xaml[LocalizationGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]|  
|Fügen Sie ein <xref:System.Windows.FrameworkElement.FlowDirection%2A> hinzu.|<ul><li>Hinzufügen einer <xref:System.Windows.FrameworkElement.FlowDirection%2A> dem Stammelement der Anwendung.</li><li>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet eine bequeme Möglichkeit zur Unterstützung von horizontalen, bidirektionalen und vertikalen Layouts. In zu testendes Präsentationsframework das <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft kann verwendet werden, um das Layout zu definieren. Die Muster der Flussrichtung sind:Die flussrichtung Muster sind:<br /><br /> <ul><li><xref:System.Windows.FlowDirection.LeftToRight>(LrTb) – horizontales Layout für Lateinisch, ostasiatische Sprachen und So weiter.</li><li><xref:System.Windows.FlowDirection.RightToLeft>(RlTb) – bidirektional für Arabisch, Hebräisch und So weiter.</li></ul></li></ul>|  
|Verwenden Sie zusammengesetzte Schriftarten anstelle von physischen Schriftarten.|<ul><li>Bei zusammengesetzten Schriftarten der <xref:System.Windows.Controls.Control.FontFamily%2A> Eigenschaft muss nicht lokalisiert werden soll.</li><li>Entwickler können eine der folgenden Schriftarten verwenden oder ihre eigenen erstellen.<br /><br /> <ul><li>Globale Benutzeroberfläche</li><li>Global San Serif</li><li>Global Serif</li></ul></li></ul>|  
|Fügen Sie xml:lang hinzu.|-Hinzufügen der `xml:lang` Attribut im Stammelement des Ihrer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], wie z. B. `xml:lang="en-US"` für eine englische Anwendung.<br />– Da es sich um eine zusammengesetzte Schriftarten verwenden `xml:lang` um zu bestimmen, welche Schriftart verwendet, legen Sie diese Eigenschaft zur Unterstützung mehrsprachiger Szenarien.|  
  
<a name="autolay_grids"></a>   
## <a name="automatic-layout-and-grids"></a>Automatisches Layout und Raster  
 Die <xref:System.Windows.Controls.Grid> -Element, eignet sich für automatisches Layout, da es die Positionierung von Elementen ermöglicht. Ein <xref:System.Windows.Controls.Grid> Steuerelement ist in der Lage, den verfügbaren Platz auf seine untergeordneten Elemente mit einer Spalte und Zeile Anordnung verteilt. Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente können mehrere Zellen umfassen, und es ist möglich, eine verschachtelte Raster aufweisen. Raster sind nützlich, da sie Ihnen ermöglichen das Erstellen und positionieren Sie komplexe [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Im folgende Beispiel wird veranschaulicht, wie mit einem Raster einige Schaltflächen und Text positioniert werden. Beachten Sie, dass die Höhe und Breite der Zellen werden zu <xref:System.Windows.GridUnitType.Auto>; daher wird die Zelle mit der Schaltfläche mit einem Bild, das Abbild angepasst.  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 Die folgende Grafik zeigt die vom vorherigen Code erzeugten Raster.  
  
 ![Rasterbeispiel](../../../../docs/framework/wpf/advanced/media/glob-grid.png "Glob_grid")  
Raster  
  
<a name="autolay_grids_issharedsizescope"></a>   
## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a>Automatisches Layout und Raster mit der IsSharedSizeScope-Eigenschaft  
 Ein <xref:System.Windows.Controls.Grid> Element ist nützlich in lokalisierbare Anwendungen um Steuerelemente zu erstellen, die an Inhalt anpassen. Manchmal ist es jedoch notwendig, dass Steuerelemente unabhängig vom Inhalt eine bestimmte Größe beibehalten. Beispielsweise sollen die Schaltflächen „OK“, „Abbrechen“ und „Durchsuchen“ wahrscheinlich nicht die Größe des Inhalts angepasst werden. In diesem Fall die <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> angefügte Eigenschaft ist nützlich für die gemeinsame Nutzung der gleichen Größe zwischen mehreren Datenblattelementen. Im folgenden Beispiel wird veranschaulicht, wie Spalten- und Größe der Daten zwischen mehreren Teilen <xref:System.Windows.Controls.Grid> Elemente.  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 **Hinweis** das vollständige Codebeispiel finden Sie unter [Freigabe Sizing Eigenschaften zwischen Datenblättern](../../../../docs/framework/wpf/controls/how-to-share-sizing-properties-between-grids.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Globalisierung für WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)  
 [Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)  
 [Verwenden eines Rasters für automatisches Layout](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
