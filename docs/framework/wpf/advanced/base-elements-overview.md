---
title: Übersicht über Basiselemente
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: 6f8542be5a84a4b8b4cabf594c32d6fdfd3757d2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453762"
---
# <a name="base-elements-overview"></a>Übersicht über Basiselemente
Ein hoher Prozentsatz der Klassen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stammen von vier Klassen ab, die häufig in der [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)]-Dokumentation als Basiselementklassen bezeichnet werden. Diese Klassen sind <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement>und <xref:System.Windows.FrameworkContentElement>. Die <xref:System.Windows.DependencyObject> Klasse ist auch verknüpft, da es sich um eine allgemeine Basisklasse von <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement>  

<a name="base_apis"></a>   
## <a name="base-element-apis-in-wpf-classes"></a>Basiselement-APIs in WPF-Klassen  
 Sowohl <xref:System.Windows.UIElement> als auch <xref:System.Windows.ContentElement> werden durch etwas andere Wege von <xref:System.Windows.DependencyObject>abgeleitet. Die Aufteilung auf dieser Ebene befasst sich damit, wie ein <xref:System.Windows.UIElement> oder <xref:System.Windows.ContentElement> auf einer Benutzeroberfläche verwendet wird und welchen Zweck Sie in einer Anwendung haben. <xref:System.Windows.UIElement> verfügt auch über <xref:System.Windows.Media.Visual> in der-Klassenhierarchie, bei der es sich um eine Klasse handelt, die die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Unterstützung auf niedrigerer Ebene verfügbar macht <xref:System.Windows.Media.Visual> bietet ein Renderingframework, indem unabhängige rechteckige Bildschirmbereiche definiert werden. In der Praxis ist <xref:System.Windows.UIElement> für Elemente, die ein größeres Objektmodell unterstützen, für das Rendering und Layout in Regionen vorgesehen, die als rechteckige Bildschirmbereiche beschrieben werden können, und wo das Inhalts Modell absichtlich offener ist, um unterschiedliche Kombinationen zuzulassen. von-Elementen. <xref:System.Windows.ContentElement> wird nicht von <xref:System.Windows.Media.Visual>abgeleitet; das zugehörige Modell ist, dass ein <xref:System.Windows.ContentElement> von einem anderen verbraucht wird, z. b. einem Reader oder Viewer, der dann die Elemente interpretiert und die gesamte <xref:System.Windows.Media.Visual> erzeugt, die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verarbeiten soll. Bestimmte <xref:System.Windows.UIElement> Klassen sind als Inhalts Hosts gedacht: Sie stellen das Hosting und Rendering für eine oder mehrere <xref:System.Windows.ContentElement> Klassen bereit (<xref:System.Windows.Controls.DocumentViewer> ist ein Beispiel für eine solche Klasse). <xref:System.Windows.ContentElement> wird als Basisklasse für Elemente mit etwas kleineren Objekt Modellen verwendet und adressiert die Text-, Informations-oder Dokumentinhalte, die in einem <xref:System.Windows.UIElement>gehostet werden können.  
  
### <a name="framework-level-and-core-level"></a>Frameworkebene und Kernebene  
 <xref:System.Windows.UIElement> fungiert als Basisklasse für <xref:System.Windows.FrameworkElement>, und <xref:System.Windows.ContentElement> fungiert als Basisklasse für <xref:System.Windows.FrameworkContentElement>. Der Grund für diese nächste Ebene von Klassen besteht darin, eine WPF-Kern Ebene zu unterstützen, die von der WPF-Frameworkebene getrennt ist. diese Division besteht auch darin, wie die APIs zwischen den Assemblys PresentationCore und presentationframework aufgeteilt werden. Die WPF-Frameworkebene stellt eine vollständigere Lösung für grundlegende Anwendungsanforderungen dar, einschließlich die Implementierung des Layout-Managers für die Darstellung. Die WPF-Kernebene bietet eine Möglichkeit, mehr von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu verwenden, ohne den Mehraufwand der zusätzlichen Assembly. Der Unterschied zwischen diesen Ebenen ist für die meisten typischen Anwendungs Entwicklungsszenarien sehr selten wichtig. im Allgemeinen sollten Sie sich die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-APIs als Ganzes vorstellen und sich nicht mit dem Unterschied zwischen der WPF-Frameworkebene und der WPF-kernstufe befassen. Sie müssen möglicherweise über die Unterschiede der Ebenen Bescheid wissen, wenn Ihr Anwendungsentwurf eine Vielzahl von Funktionen der WPF-Frameworkebene ersetzt, z.B. wenn Ihre allgemeine Projektmappe schon über eigene Implementierungen der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Zusammenstellung und des -Layouts verfügt.  
  
<a name="subclassing_elements"></a>   
## <a name="choosing-which-element-to-derive-from"></a>Auswählen des Elements für die Ableitung  
 Der praktischste Weg, eine benutzerdefinierte Klasse zu erstellen, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erweitert, ist durch Ableiten von einer der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Klassen, wobei Sie so viel Funktionalität wie möglich durch die vorhandene Klassenhierarchie erhalten. In diesem Abschnitt sind die Funktionen aufgeführt, die mit drei der wichtigsten Elementklassen geliefert werden, um Ihnen bei der Entscheidung zu helfen, von welcher Klasse geerbt werden soll.  
  
 Wenn Sie ein Steuerelement implementieren, bei dem es sich um einen der gängigsten Gründe für das Ableiten von einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Klasse handelt, sollten Sie wahrscheinlich von einer Klasse ableiten, die ein praktisches Steuerelement, eine Basisklasse der Steuerelement Familie oder zumindest aus der <xref:System.Windows.Controls.Control> Basisklasse ist. Einige Leitfäden und praktische Beispiele finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).  
  
 Wenn Sie kein Steuerelement erstellen und von einer Klasse ableiten müssen, die in der Hierarchie höher gestellt ist, sollen Ihnen die folgenden Abschnitte als Leitfaden für die Eigenschaften dienen, die in jeder Basiselementklasse definiert sind.  
  
 Wenn Sie eine Klasse erstellen, die von <xref:System.Windows.DependencyObject>abgeleitet ist, erben Sie die folgende Funktionalität:  
  
- Unterstützung für <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> sowie allgemeine Eigenschaften Systemunterstützung.  
  
- Fähigkeit zum Verwenden von Abhängigkeitseigenschaften und angefügten Eigenschaften, die als Abhängigkeitseigenschaften implementiert sind  
  
 Wenn Sie eine Klasse erstellen, die von <xref:System.Windows.UIElement>abgeleitet ist, erben Sie zusätzlich zu den von <xref:System.Windows.DependencyObject>bereitgestellten Funktionen die folgenden Funktionen:  
  
- Grundlegende Unterstützung für animierte Eigenschaftswerte. Weitere Informationen finden Sie unter [Übersicht über Animation](../graphics-multimedia/animation-overview.md).  
  
- Grundlegende Unterstützung für Eingabeereignisse und Unterstützung für Befehle. Weitere Informationen finden Sie unter [Übersicht über die Eingabe](input-overview.md) und [Befehlsübersicht](commanding-overview.md).  
  
- Virtuelle Methoden, die überschrieben werden können, um Informationen für ein Layoutsystem bereitzustellen.  
  
 Wenn Sie eine Klasse erstellen, die von <xref:System.Windows.FrameworkElement>abgeleitet ist, erben Sie zusätzlich zu den von <xref:System.Windows.UIElement>bereitgestellten Funktionen die folgenden Funktionen:  
  
- Unterstützung für Formatierung und Storyboards. Weitere Informationen finden Sie unter [Übersicht über <xref:System.Windows.Style> und Storyboards](../graphics-multimedia/storyboards-overview.md).  
  
- Unterstützung für die Datenbindung. Weitere Informationen finden Sie in der [Übersicht über die Datenbindung](../data/data-binding-overview.md).  
  
- Unterstützung für dynamische Ressourcenverweise. Weitere Informationen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Unterstützung für die Eigenschaftswertvererbung und andere Flags in den Metadaten, die Ihnen beim Melden von Bedingungen über Eigenschaften für Frameworkdienste helfen, z.B. Datenbindung, Stile oder die Frameworkimplementierung des Layouts. Weitere Informationen finden Sie unter [Framework-Eigenschaftenmetadaten](framework-property-metadata.md).  
  
- Das Konzept der logischen Struktur. Weitere Informationen finden Sie unter [Strukturen in WPF](trees-in-wpf.md).  
  
- Unterstützung für die praktische Implementierung der WPF-Frameworkebene des Layoutsystems, einschließlich einer <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> außer Kraft setzung, die Änderungen an Eigenschaften erkennen kann, die das Layout beeinflussen.  
  
 Wenn Sie eine Klasse erstellen, die von <xref:System.Windows.ContentElement>abgeleitet ist, erben Sie zusätzlich zu den von <xref:System.Windows.DependencyObject>bereitgestellten Funktionen die folgenden Funktionen:  
  
- Unterstützung für Animationen. Weitere Informationen finden Sie unter [Übersicht über Animation](../graphics-multimedia/animation-overview.md).  
  
- Grundlegende Unterstützung für Eingabeereignisse und Unterstützung für Befehle. Weitere Informationen finden Sie unter [Übersicht über die Eingabe](input-overview.md) und [Befehlsübersicht](commanding-overview.md).  
  
 Wenn Sie eine Klasse erstellen, die von <xref:System.Windows.FrameworkContentElement>abgeleitet ist, erhalten Sie zusätzlich zu den Funktionen, die von <xref:System.Windows.ContentElement>bereitgestellt werden, die folgenden Funktionen:  
  
- Unterstützung für Formatierung und Storyboards. Weitere Informationen finden Sie unter [Übersicht über](../graphics-multimedia/animation-overview.md)<xref:System.Windows.Style> und Animationen.  
  
- Unterstützung für die Datenbindung. Weitere Informationen finden Sie in der [Übersicht über die Datenbindung](../data/data-binding-overview.md).  
  
- Unterstützung für dynamische Ressourcenverweise. Weitere Informationen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Unterstützung für die Eigenschaftswertvererbung und andere Flags in den Metadaten, die Ihnen beim Melden von Bedingungen über Eigenschaften für Frameworkdienste helfen, z.B. Datenbindung, Stile oder die Frameworkimplementierung des Layouts. Weitere Informationen finden Sie unter [Framework-Eigenschaftenmetadaten](framework-property-metadata.md).  
  
- Sie erben nicht den Zugriff auf Layoutsystemänderungen (z. b. <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>). Layoutsystemimplementierungen sind nur auf <xref:System.Windows.FrameworkElement>verfügbar. Allerdings erben Sie eine <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> außer Kraft setzung, die Änderungen an Eigenschaften erkennen kann, die das Layout beeinflussen, und diese an beliebige Inhalts Hosts melden.  
  
 Inhaltsmodelle sind für eine Vielzahl von Klassen dokumentiert. Das Inhaltsmodell für eine Klasse ist ein möglicher Faktor, den Sie berücksichtigen sollten, wenn Sie eine entsprechende Klasse finden möchten, von der Sie ableiten möchten. Weitere Informationen finden Sie unter [WPF-Inhaltsmodell](../controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>   
## <a name="other-base-classes"></a>Andere Basisklassen  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject> bietet Unterstützung für das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Threading Modell und ermöglicht, dass alle Objekte, die für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen erstellt wurden, einem <xref:System.Windows.Threading.Dispatcher>zugeordnet werden. Auch wenn Sie nicht von <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject>oder <xref:System.Windows.Media.Visual>ableiten, sollten Sie die Ableitung von <xref:System.Windows.Threading.DispatcherObject> in Erwägung ziehen, um dieses Threading Modell zu unterstützen. Weitere Informationen finden Sie unter [Threading-Modell](threading-model.md).  
  
### <a name="visual"></a>Grafisches Element  
 <xref:System.Windows.Media.Visual> implementiert das Konzept eines 2D-Objekts, das in der Regel visuelle Darstellung in einem ungefähr rechteckigen Bereich erfordert. Das tatsächliche Rendering einer <xref:System.Windows.Media.Visual> erfolgt in anderen Klassen (es ist nicht eigenständig), aber die <xref:System.Windows.Media.Visual> Klasse stellt einen bekannten Typ bereit, der von Renderingprozessen auf unterschiedlichen Ebenen verwendet wird. <xref:System.Windows.Media.Visual> implementiert Treffer Tests, macht jedoch keine Ereignisse verfügbar, die positive Treffer Tests melden (diese sind in <xref:System.Windows.UIElement>). Weitere Informationen finden Sie unter [Programmierung auf visueller Ebene](../graphics-multimedia/visual-layer-programming.md).  
  
### <a name="freezable"></a>Freezable-Objekt  
 <xref:System.Windows.Freezable> simuliert die Unveränderlichkeit in einem änderbaren Objekt, indem die Mittel zum Generieren von Kopien des Objekts bereitgestellt werden, wenn ein unveränderliches Objekt erforderlich oder aus Leistungsgründen gewünscht ist. Der <xref:System.Windows.Freezable> Typ bietet eine allgemeine Grundlage für bestimmte Grafikelemente, wie z. b. Geometrien und Pinsel, sowie Animationen. Eine <xref:System.Windows.Freezable> ist insbesondere kein <xref:System.Windows.Media.Visual>. Es kann Eigenschaften enthalten, die unter Eigenschaften werden, wenn die <xref:System.Windows.Freezable> angewendet wird, um einen Eigenschafts Wert eines anderen Objekts auszufüllen, und diese unter Eigenschaften können sich auf das Rendering auswirken. Weitere Informationen finden Sie unter der [Übersicht über Freezable-Objekte](freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable> ist eine <xref:System.Windows.Freezable> abgeleitete Klasse, die speziell die Animations Steuerungsebene und einige hilfsprogrammmember hinzufügt, sodass derzeit animierte Eigenschaften von nicht animierten Eigenschaften unterschieden werden können.  
  
### <a name="control"></a>Steuerelement  
 <xref:System.Windows.Controls.Control> ist die beabsichtigte Basisklasse für den Objekttyp, der abhängig von der Technologie variron als Steuerelement oder Komponente bezeichnet wird. Im allgemeinen sind [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelementklassen Klassen, die entweder direkt ein UI-Steuerelement darstellen oder in der Zusammenstellung der Steuerelemente eng beteiligt sind. Die Hauptfunktion, die <xref:System.Windows.Controls.Control> ermöglicht, ist die Steuerung von Vorlagen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Control>
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md)
- [WPF-Architektur](wpf-architecture.md)
