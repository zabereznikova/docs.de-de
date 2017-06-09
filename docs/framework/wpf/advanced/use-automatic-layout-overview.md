---
title: "&#220;bersicht &#252;ber die Verwendung eines automatischen Layouts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Automatisches Layout"
  - "Layout, Automatisch"
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# &#220;bersicht &#252;ber die Verwendung eines automatischen Layouts
Dieses Thema enthält Richtlinien für Entwickler zum Schreiben von Anwendungen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] mit lokalisierbaren [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)].  In der Vergangenheit nahm die Lokalisierung einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sehr viel Zeit in Anspruch.  Für jede Sprache, für die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Anpassung durchgeführt wurde, musste eine Pixelanpassung vorgenommen werden.  Jetzt können die [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] mit dem geeigneten Layout und den entsprechenden Codierungsstandards so aufgebaut werden, dass die Lokalisierungsspezialisten weniger Größenänderungen und Neupositionierungen durchführen müssen.  Der Ansatz, Anwendungen zu schreiben, bei denen Größenänderungen und Neupositionierungen einfacher ausgeführt werden können, wird als automatisches Layout bezeichnet und mithilfe des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungsentwurfs erzielt.  
  
 Dieses Thema enthält folgende Abschnitte.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [Vorteile der Verwendung eines automatischen Layouts](#advantages_of_autolayout)  
  
-   [Automatisches Layout und Steuerelemente](#autolayout_controls)  
  
-   [Automatisches Layout und Codierungsstandards](#autolayout_coding)  
  
-   [Automatisches Layout und Raster](#autolay_grids)  
  
-   [Automatisches Layout und Raster mit der IsSharedSizeScope\-Eigenschaft](#autolay_grids_issharedsizescope)  
  
-   [Verwandte Themen](#seeAlsoToggle)  
  
<a name="advantages_of_autolayout"></a>   
## Vorteile der Verwendung eines automatischen Layouts  
 Mit seiner Leistungsfähigkeit und Flexibilität bietet das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Präsentationssystem die Möglichkeit, die Elemente in einer Anwendung so auszulegen, dass sie entsprechend den Anforderungen der unterschiedlichen Sprachen angepasst werden können.  Die folgende Auflistung enthält einige der Vorteile von automatischen Layouts.  
  
-   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] kann in jeder beliebigen Sprache gut angezeigt werden.  
  
-   Verringert nach der Übersetzung der textlichen Inhalte die Notwendigkeit zur erneuten Anpassung der Positionen und der Größe von Steuerelementen.  
  
-   Reduziert die Notwendigkeit zur erneuten Anpassung der Fenstergröße.  
  
-   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Layout kann in jede Sprache korrekt gerendert werden.  
  
-   Die Lokalisierung kann so vereinfacht werden, dass sie nur wenig komplexer als eine Zeichenfolgenübersetzung ist.  
  
<a name="autolayout_controls"></a>   
## Automatisches Layout und Steuerelemente  
 Ein automatisches Layout ermöglicht es einer Anwendung, die Größe eines Steuerelements automatisch einzustellen.  Ein Steuerelement kann sich beispielsweise so ändern, dass es die Länge einer Zeichenfolge anzeigt.  Mithilfe dieser Funktion können die Lokalisierungsspezialisten die Zeichenfolge übersetzen und müssen das Steuerelement nicht mehr entsprechend der Länge der Zeichenfolge anpassen.  Im folgenden Beispiel wird eine Schaltfläche mit englischem Inhalt erstellt.  
  
 [!code-xml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 Wenn Sie für das Beispiel eine Schaltfläche mit spanischem Inhalt erstellen möchten, müssen Sie nur noch den Textinhalt ändern.  Beispiel:  
  
 [!code-xml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 Die folgende Grafik zeigt die Ausgabe der Codebeispiele.  
  
 ![Die gleiche Schaltfläche mit Text in unterschiedlichen Sprachen](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Automatische Anpassung der Schaltflächengröße  
  
<a name="autolayout_coding"></a>   
## Automatisches Layout und Codierungsstandards  
 Für die Verwendung des automatischen Layoutansatzes sind Codierungs\- und Entwurfsstandards sowie Regeln erforderlich, um eine völlig lokalisierbare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] zu erstellen.  Die folgenden Richtlinien unterstützen die automatische Layoutcodierung.  
  
|Codierungsstandards|Beschreibung|  
|-------------------------|------------------|  
|Verwenden Sie keine absoluten Positionen.|-   Verwenden Sie nicht das <xref:System.Windows.Controls.Canvas>\-Objekt, weil Elemente damit absolut positioniert werden.<br />-   Verwenden Sie zur Positionierung der Steuerelemente <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel> und <xref:System.Windows.Controls.Grid>.<br />-   Die verschiedenen Bereichstypen werden unter [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md) erläutert.|  
|Legen Sie keine feste Größe für ein Fenster fest.|-   Verwenden Sie die <xref:System.Windows.Window.SizeToContent%2A>\-Eigenschaft.<br />-   Beispiele:<br /><br /> [!code-xml[LocalizationGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]|  
|Fügen Sie eine <xref:System.Windows.FrameworkElement.FlowDirection%2A>\-Eigenschaft hinzu.|<ul><li>Fügen Sie dem Stammelement der Anwendung eine <xref:System.Windows.FrameworkElement.FlowDirection%2A> hinzu.</li><li>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet eine komfortable Möglichkeit zur Unterstützung von horizontalen, bidirektionalen und vertikalen Layouts.  In PresentationFramework kann die <xref:System.Windows.FrameworkElement.FlowDirection%2A>\-Eigenschaft zur Definition des Layouts verwendet werden.  Folgende Flussrichtungsmuster stehen zur Verfügung:<br /><br /> <ul><li><xref:System.Windows.FlowDirection> \(LrTb\) —horizontales Layout für Lateinisch, ostasiatische Sprachen usw.</li><li><xref:System.Windows.FlowDirection> \(RlTb\) — bidirektional für Arabisch, Hebräisch usw.</li></ul></li></ul>|  
|Verwenden Sie zusammengesetzte Schriftarten statt physischer Schriftarten.|<ul><li>Bei zusammengesetzten Schriftarten muss die <xref:System.Windows.Controls.Control.FontFamily%2A>\-Eigenschaft nicht lokalisiert werden.</li><li>Entwickler können eine der folgenden Schriftarten verwenden oder ihre eigenen erstellen.<br /><br /> <ul><li>Global User Interface</li><li>Global Sans Serif</li><li>Global Serif</li></ul></li></ul>|  
|Fügen Sie xml:lang hinzu.|-   Fügen Sie das `xml:lang`\-Attribut im [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Stammelement hinzu, z. B. `xml:lang="en-US"` für eine englische Anwendung.<br />-   Da `xml:lang` von zusammengesetzten Schriftarten für die Bestimmung der zu verwendenden Schriftarten herangezogen wird, legen Sie diese Eigenschaft so fest, dass sie mehrsprachige Szenarien unterstützt.|  
  
<a name="autolay_grids"></a>   
## Automatisches Layout und Raster  
 Das <xref:System.Windows.Controls.Grid>\-Element eignet sich für automatische Layouts, da es die Positionierung von Elementen ermöglicht.  Ein <xref:System.Windows.Controls.Grid>\-Steuerelement kann den verfügbaren Leerraum mit einer Spalten\- und Zeilenanordnung auf seine untergeordneten Elemente verteilen.  Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Elemente können sich über mehrere Zellen erstrecken und verschachtelte Raster aufweisen.  Raster sind sehr hilfreich, da Sie mit deren Hilfe eine komplexe [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] erstellen und positionieren können.  Im folgenden Beispiel wird veranschaulicht, wie mit einem Raster einige Schaltflächen und Text positioniert werden.  Beachten Sie, dass Höhe und Breite der Zellen auf <xref:System.Windows.GridUnitType> festgelegt sind. Daher wird die Größe der Zelle, die die Schaltfläche mit einem Bild enthält, an das Bild angepasst.  
  
 [!code-xml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 Die folgende Grafik zeigt das vom vorherigen Code erzeugte Raster.  
  
 ![Rasterbeispiel](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob\_grid")  
Raster  
  
<a name="autolay_grids_issharedsizescope"></a>   
## Automatisches Layout und Raster mit der IsSharedSizeScope\-Eigenschaft  
 Ein <xref:System.Windows.Controls.Grid>\-Element ist in lokalisierbaren Anwendungen sehr hilfreich, um Steuerelemente zu erstellen, die sich an den entsprechenden Inhalt anpassen.  Zuweilen ist es jedoch erforderlich, dass die Steuerelemente unabhängig vom Inhalt eine bestimmte Größe beibehalten.  So sollen beispielsweise die Schaltflächen "OK", "Abbrechen" und "Durchsuchen" wahrscheinlich nicht an den entsprechenden Inhalt angepasst werden.  In diesem Fall kann die angehängte Eigenschaft <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=fullName> verwendet werden, um dieselbe Größe in mehreren Rasterelementen zu nutzen.  Im folgenden Beispiel wird veranschaulicht, wie dieselbe Spalten\- und Zeilengröße in mehreren <xref:System.Windows.Controls.Grid>\-Elementen gemeinsam genutzt werden kann.  
  
 [!code-xml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 **Hinweis:** Das vollständige Codebeispiel finden Sie unter [Freigeben von Größeneigenschaften zwischen Grids](../../../../docs/framework/wpf/controls/how-to-share-sizing-properties-between-grids.md).  
  
## Siehe auch  
 [Globalisierung für WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)   
 [Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)   
 [Verwenden eines Rasters für automatisches Layout](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)