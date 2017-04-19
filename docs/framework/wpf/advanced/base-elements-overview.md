---
title: "&#220;bersicht &#252;ber Basiselemente | Microsoft Docs"
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
  - "Basiselemente"
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# &#220;bersicht &#252;ber Basiselemente
Ein sehr großer Teil der Klassen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ist von vier Klassen abgeleitet, die im Allgemeinen in der [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)]\-Dokumentation als Basiselementklassen bezeichnet werden.  Diese Klassen sind <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement> und <xref:System.Windows.FrameworkContentElement>.  Die <xref:System.Windows.DependencyObject>\-Klasse ist ebenfalls in diesem Zusammenhang zu sehen, da es sich dabei um eine allgemeine Basisklasse von <xref:System.Windows.UIElement> und von <xref:System.Windows.ContentElement> handelt.  
  
   
  
<a name="base_apis"></a>   
## Basiselement\-APIs in WPF\-Klassen  
 Sowohl <xref:System.Windows.UIElement> als auch <xref:System.Windows.ContentElement> werden von dem <xref:System.Windows.DependencyObject> abgeleitet, auf leicht unterschiedlichen Wegen.  Die Aufteilung auf dieser Ebene bezieht sich darauf, wie ein <xref:System.Windows.UIElement>\- oder <xref:System.Windows.ContentElement>\-Element in einer Benutzeroberfläche verwendet wird und zu welchem Zweck diese in einer Anwendung dienen.  Das <xref:System.Windows.UIElement>\-Element hat außerdem das <xref:System.Windows.Media.Visual>\-Element in seiner Klassenhierarchie. Dabei handelt es sich um eine Klasse, die die dem [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] zugrunde liegende Unterstützung für Grafiken auf niedrigerer Ebene verfügbar macht.  Das <xref:System.Windows.Media.Visual>\-Element stellt ein Renderingframework durch die Definition unabhängiger rechteckiger Bildschirmbereiche bereit.  In der Praxis wird das <xref:System.Windows.UIElement>\-Objekt für Elemente verwendet, die ein größeres Objektmodell unterstützen, für das Rendering und Layout in als rechteckige Bildschirmbereiche beschreibbaren Bereichen vorgesehen sind und ein absichtlich offeneres Inhaltsmodell verwenden, um verschiedene Kombinationen von Elementen zu ermöglichen.  Ein <xref:System.Windows.ContentElement>\-Element wird nicht von <xref:System.Windows.Media.Visual> abgeleitet. Es folgt einem Modell, bei dem ein <xref:System.Windows.ContentElement>\-Element durch etwas anderes, z. B. einen Reader oder Viewer, verarbeitet wird, der dann die Elemente interpretieren und das gesamte <xref:System.Windows.Media.Visual>\-Objekt für die Verarbeitung durch [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] erzeugt.  Bestimmte <xref:System.Windows.UIElement>\-Klassen sind als Inhaltshosts gedacht: Sie stellen das Hosting und Rendering für eine oder mehrere <xref:System.Windows.ContentElement> \-Klassen bereit \(<xref:System.Windows.Controls.DocumentViewer> ist ein Beispiel für eine solche Klasse\).  <xref:System.Windows.ContentElement> wird als Basisklasse für Elemente mit eher kleineren Objektmodellen verwendet, die sich mehr auf den Text, die Informationen oder den Dokumentinhalt beziehen, die innerhalb eines <xref:System.Windows.UIElement>\-Elements gehostet werden könnten.  
  
### Frameworkebene und Kernebene  
 <xref:System.Windows.UIElement> dient als Basisklasse für <xref:System.Windows.FrameworkElement>, und <xref:System.Windows.ContentElement> dient als Basisklasse für <xref:System.Windows.FrameworkContentElement>.  Diese nächste Ebene von Klassen dient dazu, eine [WPF\-Kernebene](GTMT) zu unterstützen, die von einer [WPF\-Frameworkebene](GTMT) getrennt ist. Diese Trennung besteht auch bei der Aufteilung der [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] zwischen den PresentationCore\- und den PresentationFramework\-Assemblys.  Die [WPF\-Frameworkebene](GTMT) stellt eine umfassendere Lösung für die grundlegenden Anforderungen von Anwendungen dar, einschließlich der Implementierung eines Layoutmanagers für die Präsentation.  Die [WPF\-Kernebene](GTMT) bietet eine Möglichkeit, einen großen Teil von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu nutzen, ohne den Aufwand der zusätzlichen Assembly übernehmen zu müssen.  Die Unterscheidung zwischen diesen beiden Ebenen spielt in den meisten üblichen Anwendungsentwicklungsszenarien kaum eine Rolle. Im Allgemeinen reicht es, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] als Gesamtheit zu sehen und dem Unterschied zwischen [WPF\-Frameworkebene](GTMT) und [WPF\-Kernebene](GTMT) keine große Bedeutung beizumessen.  Sie müssen die Unterscheidung zwischen diesen Ebenen möglicherweise kennen, wenn in Ihrem Anwendungsentwurf die Funktionen der [WPF\-Frameworkebene](GTMT) in größerem Umfang ersetzt werden, beispielsweise, wenn Ihre Gesamtlösung eigene Implementierungen von [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]\-Zusammensetzung und \-Layout hat.  
  
<a name="subclassing_elements"></a>   
## Auswählen der Elemente für die Ableitung  
 In der Praxis lässt sich eine benutzerdefinierte Klasse, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erweitert, am einfachsten erstellen, indem sie von einer der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Klassen abgeleitet wird, bei der Sie möglichst viele der gewünschten Funktionen über die vorhandene Klassenhierarchie erhalten.  In diesem Abschnitt werden die Funktionen aufgeführt, die drei der wichtigsten Elementklassen liefern, um Ihnen die Entscheidung für die Klasse zu erleichtern, von der geerbt werden soll.  
  
 Wenn Sie ein Steuerelement implementieren \(ein recht häufiger Grund für die Ableitung von einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Klasse\), sollten Sie das Steuerelement von einer Klasse ableiten, die ein geeignetes Steuerelement, eine Steuerelementfamilien\-Basisklasse oder zumindest eine <xref:System.Windows.Controls.Control>\-Basisklasse ist.  Anweisungen und praktische Beispiele finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Wenn Sie kein Steuerelement erstellen und von einer Klasse ableiten möchten, die in der Hierarchie höher steht, finden Sie in den folgenden Abschnitten einen Leitfaden, welche Eigenschaften in den einzelnen Basiselementklassen definiert sind.  
  
 Wenn Sie eine Klasse erstellen, die von <xref:System.Windows.DependencyObject> abgeleitet wird, erben Sie die folgenden Funktionen:  
  
-   Unterstützung von <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> sowie allgemeine Unterstützung des Eigenschaftensystems.  
  
-   Fähigkeit zur Verwendung von [Abhängigkeitseigenschaften](GTMT) und [angefügten Eigenschaften](GTMT), die als [Abhängigkeitseigenschaften](GTMT) implementiert sind.  
  
 Wenn Sie eine Klasse erstellen, die von <xref:System.Windows.UIElement> abgeleitet wird, erben Sie zusätzlich zu den Funktionen, die <xref:System.Windows.DependencyObject> bereitstellt, die folgenden Funktionen:  
  
-   Grundlegende Unterstützung von animierten Eigenschaftswerten.  Weitere Informationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Grundlegende Unterstützung von Eingabeereignissen und Unterstützung von Befehlen.  Weitere Informationen finden Sie unter [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md) und [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
-   Virtuelle Methoden, die überschrieben werden können, um Informationen für ein Layoutsystem bereitzustellen.  
  
 Wenn Sie eine Klasse erstellen, die von <xref:System.Windows.FrameworkElement> abgeleitet wird, erben Sie zusätzlich zu den Funktionen, die <xref:System.Windows.UIElement> bereitstellt, die folgenden Funktionen:  
  
-   Unterstützung von Formatierung und Storyboards.  Weitere Informationen finden Sie unter <xref:System.Windows.Style> und [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
-   Unterstützung von Datenbindung.  Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Unterstützung von dynamischen Ressourcenverweisen.  Weitere Informationen finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Unterstützung der Vererbung von Eigenschaftswerten und weitere Flags in den Metadaten, die die Meldung von Bedingungen für Eigenschaften an Frameworkdienste unterstützen, z. B. Datenbindung, Stile oder die Frameworkimplementierung von Layout.  Weitere Informationen hierzu finden Sie unter [Framework\-Eigenschaftenmetadaten](../../../../docs/framework/wpf/advanced/framework-property-metadata.md).  
  
-   Das Konzept der [logischen Struktur](GTMT).  Weitere Informationen hierzu finden Sie unter [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
-   Unterstützung der praktischen [WPF\-Frameworkebenen](GTMT)\-Implementierung des Layoutsystems, einschließlich einer <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A>\-Überschreibung, die Änderungen an Eigenschaften mit Auswirkungen auf das Layout erkennen kann.  
  
 Wenn Sie eine Klasse erstellen, die von <xref:System.Windows.ContentElement> abgeleitet wird, erben Sie zusätzlich zu den Funktionen, die <xref:System.Windows.DependencyObject> bereitstellt, die folgenden Funktionen:  
  
-   Unterstützung von Animationen.  Weitere Informationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Grundlegende Unterstützung von Eingabeereignissen und Unterstützung von Befehlen.  Weitere Informationen finden Sie unter [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md) und [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
 Wenn Sie eine Klasse erstellen, die von <xref:System.Windows.FrameworkContentElement> abgeleitet wird, erhalten Sie zusätzlich zu den Funktionen, die <xref:System.Windows.ContentElement> bereitstellt, die folgenden Funktionen:  
  
-   Unterstützung von Formatierung und Storyboards.  Weitere Informationen finden Sie unter <xref:System.Windows.Style> und [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Unterstützung von Datenbindung.  Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Unterstützung von dynamischen Ressourcenverweisen.  Weitere Informationen finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Unterstützung der Vererbung von Eigenschaftswerten und weitere Flags in den Metadaten, die die Meldung von Bedingungen für Eigenschaften an Frameworkdienste unterstützen, z. B. Datenbindung, Stile oder die Frameworkimplementierung von Layout.  Weitere Informationen hierzu finden Sie unter [Framework\-Eigenschaftenmetadaten](../../../../docs/framework/wpf/advanced/framework-property-metadata.md).  
  
-   Sie erben keinen Zugriff auf Layoutsystemänderungen \(wie <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>\).  Layoutsystemimplementierungen sind nur für <xref:System.Windows.FrameworkElement> verfügbar.  Sie erben jedoch eine <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A>\-Überschreibung, die Änderungen an Eigenschaften mit Auswirkungen auf das Layout erkennen und diese Änderungen an Inhaltshosts melden kann.  
  
 Inhaltsmodelle sind für eine Vielzahl von Klassen dokumentiert.  Das Inhaltsmodell für eine Klasse ist ein möglicher Faktor, den Sie betrachten sollten, wenn Sie eine geeignete Klasse als Basis für die Ableitung suchen.  Weitere Informationen finden Sie unter [WPF\-Inhaltsmodell](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>   
## Andere Basisklassen  
  
### DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject> bietet Unterstützung für das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Threadingmodell und ermöglicht allen Objekten, die für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen erstellt werden, die Zuordnung zu einem <xref:System.Windows.Threading.Dispatcher>.  Auch wenn Sie nicht von den Objekten <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject> oder <xref:System.Windows.Media.Visual> ableiten, sollten Sie eine Ableitung von dem <xref:System.Windows.Threading.DispatcherObject>\-Objekt in Betracht ziehen, um diese Unterstützung für das Threadingmodell zu erhalten.  Weitere Informationen hierzu finden Sie unter [Threading\-Modell](../../../../docs/framework/wpf/advanced/threading-model.md).  
  
### Visual  
 <xref:System.Windows.Media.Visual> implementiert das Konzept eines 2D\-Objekts, für das im Allgemeinen die visuelle Präsentation in einem etwa rechteckigen Bereich erforderlich ist.  Das tatsächliche Rendern eines <xref:System.Windows.Media.Visual>\-Elements geschieht in anderen Klassen \(d. h., es erfolgt nicht unabhängig\), aber die <xref:System.Windows.Media.Visual>\-Klasse liefert einen bekannten Typ, der von Renderingprozessen auf verschiedenen Ebenen verwendet wird.  Das <xref:System.Windows.Media.Visual>\-Element implementiert Treffertests, macht jedoch keine Ereignisse verfügbar, die positive Treffertestergebnisse melden \(diese sind im <xref:System.Windows.UIElement>\-Element enthalten\).  Weitere Informationen hierzu finden Sie unter [Programmierung auf visueller Ebene](../../../../docs/framework/wpf/graphics-multimedia/visual-layer-programming.md).  
  
### Freezable  
 <xref:System.Windows.Freezable> simuliert Unveränderlichkeit in einem änderbaren Objekt durch Bereitstellung der Möglichkeit zum Generieren von Kopien des Objekts, wenn ein unveränderliches Objekt erforderlich oder aus Leistungsgründen erwünscht ist.  Der <xref:System.Windows.Freezable>\-Typ liefert eine gemeinsame Basis für bestimmte Grafikelemente wie Geometrien und Pinsel sowie Animationen.  Insbesondere ist ein <xref:System.Windows.Freezable>\-Objekt kein <xref:System.Windows.Media.Visual>\-Objekt. Es kann Eigenschaften speichern, die zu untergeordneten Eigenschaften werden, wenn <xref:System.Windows.Freezable> verwendet wird, um einen Eigenschaftswert für ein anderes Objekt zu liefern, und diese untergeordneten Eigenschaften können das Rendern beeinträchtigen.  Weitere Informationen finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable> ist eine von <xref:System.Windows.Freezable> abgeleitete Klasse, die insbesondere die Animationssteuerungsebene sowie einige Dienstprogramm\-Member hinzufügt, sodass gegenwärtig animierte Eigenschaften von nicht animierten Eigenschaften unterschieden werden können.  
  
### Steuerelement  
 <xref:System.Windows.Controls.Control> ist die intendierte Basisklasse für den Objekttyp, der je nach Technologie als Steuerelement oder Komponente bezeichnet wird.  Im Allgemeinen sind [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelementklassen Klassen, die entweder direkt ein Steuerelement der Benutzeroberfläche darstellen oder eng an der Steuerelementzusammensetzung beteiligt sind.  Durch das <xref:System.Windows.Controls.Control>\-Element wird in erster Linie die Funktion der Steuerelementvorlagen aktiviert.  
  
## Siehe auch  
 <xref:System.Windows.Controls.Control>   
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md)   
 [WPF\-Architektur](../../../../docs/framework/wpf/advanced/wpf-architecture.md)