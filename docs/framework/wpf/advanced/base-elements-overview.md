---
title: Übersicht über Basiselemente
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: 73d854d601de05c2cb7dd6063e4a5f2907b09f47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578665"
---
# <a name="base-elements-overview"></a>Übersicht über Basiselemente
Ein hoher Prozentsatz der Klassen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stammen von vier Klassen ab, die häufig in der [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)]-Dokumentation als Basiselementklassen bezeichnet werden. Diese Klassen sind <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement>, und <xref:System.Windows.FrameworkContentElement>. Die <xref:System.Windows.DependencyObject> -Klasse auch bezieht, da es sich um eine allgemeine Basisklasse von beiden ist <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement>  
 
  
<a name="base_apis"></a>   
## <a name="base-element-apis-in-wpf-classes"></a>Basiselement-APIs in WPF-Klassen  
 Beide <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement> davon abgeleitet sind <xref:System.Windows.DependencyObject>, über etwas andere Pfade. Die Aufteilung auf dieser Ebene befasst sich mit einem <xref:System.Windows.UIElement> oder <xref:System.Windows.ContentElement> in einer Benutzeroberfläche und zu welchem Zweck sie dienen in einer Anwendung verwendet werden. <xref:System.Windows.UIElement> verfügt auch über <xref:System.Windows.Media.Visual> in der Klassenhierarchie, d.h. eine Klasse, die die Low-Level-grafikunterstützung macht die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. <xref:System.Windows.Media.Visual> bietet ein Rendering-Framework durch definieren unabhängiger rechteckiger Bildschirmbereiche. In der Praxis <xref:System.Windows.UIElement> ist für Elemente, die ein größeres Objektmodell unterstützen, sind vorgesehen, die zum Rendern und Regionen, die als rechteckige Bildschirmbereiche beschrieben werden können und, wo das Inhaltsmodell bewusst mehr geöffnet ist, können verschiedene, Layouts Kombinationen von Elementen. <xref:System.Windows.ContentElement> nicht von abgeleitet <xref:System.Windows.Media.Visual>; das Modell ist, die eine <xref:System.Windows.ContentElement> von etwas anderem, wie z. B. einen Reader oder Viewer, die dann die Elemente zu interpretieren und erzeugt die vollständige verwendet <xref:System.Windows.Media.Visual> für [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] nutzen. Bestimmte <xref:System.Windows.UIElement> -Klassen sollen Inhaltshosts sein: sie bieten das hosting und Rendering für eine oder mehrere <xref:System.Windows.ContentElement> Klassen (<xref:System.Windows.Controls.DocumentViewer> ist ein Beispiel einer solchen Klasse). <xref:System.Windows.ContentElement> Dient als Basisklasse für Elemente mit kleineren Objektmodellen und mehr auf den Text, die Informationen oder den Dokumentinhalt, die in gehostet werden, können ein <xref:System.Windows.UIElement>.  
  
### <a name="framework-level-and-core-level"></a>Frameworkebene und Kernebene  
 <xref:System.Windows.UIElement> Dient als Basisklasse für <xref:System.Windows.FrameworkElement>, und <xref:System.Windows.ContentElement> dient als Basisklasse für <xref:System.Windows.FrameworkContentElement>. Der Grund für diese nächste Klassenebene ist die Unterstützung einer WPF-Kernebene, die unabhängig von einer WPF-Frameworkebene ist. Diese Unterteilung ist auch relevant, in wie weit [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] zwischen den Assembys PresentationCore und PresentationFramework getrennt sind. Die WPF-Frameworkebene stellt eine vollständigere Lösung für grundlegende Anwendungsanforderungen dar, einschließlich die Implementierung des Layout-Managers für die Darstellung. Die WPF-Kernebene bietet eine Möglichkeit, mehr von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu verwenden, ohne den Mehraufwand der zusätzlichen Assembly. Der Unterschied zwischen diesen Ebenen spielt für die meisten Anwendungsentwicklungsszenarios in den seltensten Fällen eine Rolle. Allgemein sollten Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] als Ganzes betrachten und sich keine Sorgen über den Unterschied zwischen der WPF-Frameworkebene und der -Kernebene machen. Sie müssen möglicherweise über die Unterschiede der Ebenen Bescheid wissen, wenn Ihr Anwendungsentwurf eine Vielzahl von Funktionen der WPF-Frameworkebene ersetzt, z.B. wenn Ihre allgemeine Projektmappe schon über eigene Implementierungen der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Zusammenstellung und des -Layouts verfügt.  
  
<a name="subclassing_elements"></a>   
## <a name="choosing-which-element-to-derive-from"></a>Auswählen des Elements für die Ableitung  
 Der praktischste Weg, eine benutzerdefinierte Klasse zu erstellen, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erweitert, ist durch Ableiten von einer der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Klassen, wobei Sie so viel Funktionalität wie möglich durch die vorhandene Klassenhierarchie erhalten. In diesem Abschnitt sind die Funktionen aufgeführt, die mit drei der wichtigsten Elementklassen geliefert werden, um Ihnen bei der Entscheidung zu helfen, von welcher Klasse geerbt werden soll.  
  
 Wenn Sie ein Steuerelement implementieren die ist einer der häufigeren Gründe für die Ableitung von einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Klasse, möchten Sie wahrscheinlich, leiten Sie von einer Klasse, die ein praktisches Steuerelement eine Basisklasse, oder auf zumindest von der <xref:System.Windows.Controls.Control> Basisklasse. Einige Leitfäden und praktische Beispiele finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Wenn Sie kein Steuerelement erstellen und von einer Klasse ableiten müssen, die in der Hierarchie höher gestellt ist, sollen Ihnen die folgenden Abschnitte als Leitfaden für die Eigenschaften dienen, die in jeder Basiselementklasse definiert sind.  
  
 Wenn Sie eine Klasse, die Erstellen von abgeleitet <xref:System.Windows.DependencyObject>, erben die folgende Funktionen:  
  
-   <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> Unterstützung und allgemeine.  
  
-   Fähigkeit zum Verwenden von Abhängigkeitseigenschaften und angefügten Eigenschaften, die als Abhängigkeitseigenschaften implementiert sind  
  
 Wenn Sie eine Klasse, die Erstellen von abgeleitet <xref:System.Windows.UIElement>, erben die folgende Funktionalität zusätzlich zu den <xref:System.Windows.DependencyObject>:  
  
-   Grundlegende Unterstützung für animierte Eigenschaftswerte. Weitere Informationen finden Sie unter [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Grundlegende Unterstützung für Eingabeereignisse und Unterstützung für Befehle. Weitere Informationen finden Sie unter [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md) und [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
-   Virtuelle Methoden, die überschrieben werden können, um Informationen für ein Layoutsystem bereitzustellen.  
  
 Wenn Sie eine Klasse, die Erstellen von abgeleitet <xref:System.Windows.FrameworkElement>, erben die folgende Funktionalität zusätzlich zu den <xref:System.Windows.UIElement>:  
  
-   Unterstützung für Formatierung und Storyboards. Weitere Informationen finden Sie unter <xref:System.Windows.Style> und [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
-   Unterstützung für die Datenbindung. Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Unterstützung für dynamische Ressourcenverweise. Weitere Informationen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Unterstützung für die Eigenschaftswertvererbung und andere Flags in den Metadaten, die Ihnen beim Melden von Bedingungen über Eigenschaften für Frameworkdienste helfen, z.B. Datenbindung, Stile oder die Frameworkimplementierung des Layouts. Weitere Informationen finden Sie unter [Framework-Eigenschaftenmetadaten](../../../../docs/framework/wpf/advanced/framework-property-metadata.md).  
  
-   Das Konzept der logischen Struktur. Weitere Informationen finden Sie unter [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
-   Unterstützung für die praktische Implementierung der WPF-Frameworkebene des Layoutsystems, einschließlich einer <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> außer Kraft setzen, die erkennen, kann Änderungen an Eigenschaften, die das Layout beeinflussen.  
  
 Wenn Sie eine Klasse, die Erstellen von abgeleitet <xref:System.Windows.ContentElement>, erben die folgende Funktionalität zusätzlich zu den <xref:System.Windows.DependencyObject>:  
  
-   Unterstützung für Animationen. Weitere Informationen finden Sie unter [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Grundlegende Unterstützung für Eingabeereignisse und Unterstützung für Befehle. Weitere Informationen finden Sie unter [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md) und [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
 Wenn Sie eine Klasse, die Erstellen von abgeleitet <xref:System.Windows.FrameworkContentElement>, erhalten Sie die folgende Funktionalität zusätzlich zu den <xref:System.Windows.ContentElement>:  
  
-   Unterstützung für Formatierung und Storyboards. Weitere Informationen finden Sie unter <xref:System.Windows.Style> und [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Unterstützung für die Datenbindung. Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Unterstützung für dynamische Ressourcenverweise. Weitere Informationen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Unterstützung für die Eigenschaftswertvererbung und andere Flags in den Metadaten, die Ihnen beim Melden von Bedingungen über Eigenschaften für Frameworkdienste helfen, z.B. Datenbindung, Stile oder die Frameworkimplementierung des Layouts. Weitere Informationen finden Sie unter [Framework-Eigenschaftenmetadaten](../../../../docs/framework/wpf/advanced/framework-property-metadata.md).  
  
-   Sie erben nicht den Zugriff auf layoutsystemänderungen (wie z. B. <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>). Layoutsystemimplementierungen sind nur verfügbar für <xref:System.Windows.FrameworkElement>. Sie erben jedoch eine <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> außer Kraft setzen, die Änderungen an Eigenschaften erkennen kann, die Layout beeinflussen, und melden diese an Inhaltshosts.  
  
 Inhaltsmodelle sind für eine Vielzahl von Klassen dokumentiert. Das Inhaltsmodell für eine Klasse ist ein möglicher Faktor, den Sie berücksichtigen sollten, wenn Sie eine entsprechende Klasse finden möchten, von der Sie ableiten möchten. Weitere Informationen finden Sie unter [WPF-Inhaltsmodell](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>   
## <a name="other-base-classes"></a>Andere Basisklassen  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject> bietet Unterstützung für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Threadmodell und ermöglicht, die alle Objekte, für die erstellt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen verknüpft werden soll eine <xref:System.Windows.Threading.Dispatcher>. Auch wenn Sie nicht von abgeleitet sind <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject>, oder <xref:System.Windows.Media.Visual>, sollten Sie erwägen, ableiten von <xref:System.Windows.Threading.DispatcherObject> um Unterstützung für das Threadingmodell zu erhalten. Weitere Informationen finden Sie unter [Threading-Modell](../../../../docs/framework/wpf/advanced/threading-model.md).  
  
### <a name="visual"></a>Grafisches Element  
 <xref:System.Windows.Media.Visual> implementiert das Konzept eines 2D-Objekts, die im Allgemeinen visuelle Darstellung in einem etwa rechteckigen Bereich erfordert. Das eigentliche Rendern einer <xref:System.Windows.Media.Visual> geschieht in anderen Klassen (es ist nicht eigenständig), aber die <xref:System.Windows.Media.Visual> Klasse liefert einen bekannten Typ, der von Renderingprozessen auf verschiedenen Ebenen verwendet wird. <xref:System.Windows.Media.Visual> implementiert den Treffertest durchführen, aber es keine Ereignisse an, die positive Treffertests melden (diese befinden sich im <xref:System.Windows.UIElement>). Weitere Informationen finden Sie unter [Programmierung auf visueller Ebene](../../../../docs/framework/wpf/graphics-multimedia/visual-layer-programming.md).  
  
### <a name="freezable"></a>Freezable-Objekt  
 <xref:System.Windows.Freezable> simuliert Unveränderlichkeit in einem veränderbares Objekt durch die Bereitstellung der Möglichkeit zum Generieren von Kopien des Objekts, wenn ein unveränderliches Objekt erforderlich oder Leistungsgründen erwünscht ist. Die <xref:System.Windows.Freezable> Typ bietet eine allgemeine Grundlage für bestimmte Grafikelemente wie Geometrien und Pinsel sowie Animationen. Vor allem eine <xref:System.Windows.Freezable> ist keine <xref:System.Windows.Media.Visual>; sie kann Eigenschaften enthalten, die untergeordneten Eigenschaften werden beim der <xref:System.Windows.Freezable> wird angewendet, um einen Eigenschaftswert eines anderen Objekts zu füllen und diese Untereigenschaften können das Rendern beeinträchtigen. Weitere Informationen finden Sie unter der [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable> ist eine <xref:System.Windows.Freezable> abgeleitete Klasse, die speziell die Steuerelementebene für die Animation und einige nützliche Member hinzufügt, sodass derzeit animierte Eigenschaften unterschieden werden können von nicht.  
  
### <a name="control"></a>Steuerelement  
 <xref:System.Windows.Controls.Control> ist die Basisklasse für den Typ des Objekts, das unterschiedlich Steuerelement oder eine Komponente, je nach Technologie bezeichnet wird. Im allgemeinen sind [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelementklassen Klassen, die entweder direkt ein UI-Steuerelement darstellen oder in der Zusammenstellung der Steuerelemente eng beteiligt sind. Die Hauptfunktionalität, <xref:System.Windows.Controls.Control> zulässt, sind Steuerelementvorlagen.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.Control>
- [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md)
- [WPF-Architektur](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
