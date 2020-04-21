---
title: Übersicht über Basiselemente
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: f6519675ebf3624152e1077e7582f04e38b1dce9
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644036"
---
# <a name="base-elements-overview"></a>Übersicht über Basiselemente
Ein hoher Prozentsatz [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] der Klassen in wird von vier Klassen abgeleitet, die in der SDK-Dokumentation häufig als Basiselementklassen bezeichnet werden. Diese Klassen <xref:System.Windows.UIElement> <xref:System.Windows.FrameworkElement>sind <xref:System.Windows.ContentElement>, <xref:System.Windows.FrameworkContentElement>, und . Die <xref:System.Windows.DependencyObject> Klasse ist auch verwandt, da sie <xref:System.Windows.UIElement> eine gemeinsame Basisklasse von<xref:System.Windows.ContentElement>  

<a name="base_apis"></a>
## <a name="base-element-apis-in-wpf-classes"></a>Basiselement-APIs in WPF-Klassen  
 Beide <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement> und werden <xref:System.Windows.DependencyObject>von abgeleitet , durch etwas unterschiedliche Wege. Die Aufteilung auf dieser Ebene <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement> befasst sich mit der Verwendung einer oder in einer Benutzeroberfläche und mit welchem Zweck sie in einer Anwendung dienen. <xref:System.Windows.UIElement>hat <xref:System.Windows.Media.Visual> auch in seiner Klassenhierarchie, die eine Klasse ist, die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]die grafikuntere Unterstützung auf niedrigerer Ebene verfügbar macht, die der zugrunde liegt. <xref:System.Windows.Media.Visual>bietet ein Rendering-Framework, indem unabhängige rechteckige Bildschirmbereiche definiert werden. In der <xref:System.Windows.UIElement> Praxis ist für Elemente, die ein größeres Objektmodell unterstützen, sollen rendern und Layout in Bereiche, die als rechteckige Bildschirmbereiche beschrieben werden können, und wo das Inhaltsmodell ist absichtlich offener, um verschiedene Kombinationen von Elementen zu ermöglichen. <xref:System.Windows.ContentElement>leitet sich nicht <xref:System.Windows.Media.Visual>von ab ; Sein Modell ist, dass ein <xref:System.Windows.ContentElement> von etwas anderem verbraucht wird, z. B. <xref:System.Windows.Media.Visual> von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] einem Leser oder Betrachter, der dann die Elemente interpretiert und das vollständige für den Verbrauch erzeugt. Bestimmte <xref:System.Windows.UIElement> Klassen sind als Inhaltshosts gedacht: Sie stellen das <xref:System.Windows.ContentElement> Hosting<xref:System.Windows.Controls.DocumentViewer> und Rendering für eine oder mehrere Klassen bereit (ist ein Beispiel für eine solche Klasse). <xref:System.Windows.ContentElement>wird als Basisklasse für Elemente mit etwas kleineren Objektmodellen verwendet, die sich mehr mit <xref:System.Windows.UIElement>Text, Informationen oder Dokumentinhalten befassen, die möglicherweise in einem gehostet werden.  
  
### <a name="framework-level-and-core-level"></a>Frameworkebene und Kernebene  
 <xref:System.Windows.UIElement>dient als Basisklasse <xref:System.Windows.FrameworkElement>für <xref:System.Windows.ContentElement> und dient als <xref:System.Windows.FrameworkContentElement>Basisklasse für . Der Grund für diese nächste Klassenebene ist die Unterstützung einer WPF-Kernebene, die von einer WPF-Frameworkebene getrennt ist, wobei diese Division auch in der Aufteilung der APIs zwischen den Assemblys PresentationCore und PresentationFramework vorhanden ist. Die WPF-Frameworkebene stellt eine vollständigere Lösung für grundlegende Anwendungsanforderungen dar, einschließlich die Implementierung des Layout-Managers für die Darstellung. Die WPF-Kernebene bietet eine Möglichkeit, mehr von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu verwenden, ohne den Mehraufwand der zusätzlichen Assembly. Die Unterscheidung zwischen diesen Ebenen spielt für die meisten typischen Anwendungsentwicklungsszenarien sehr selten eine Rolle, und im Allgemeinen sollten Sie sich die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] APIs als Ganzes überlegen und sich nicht mit dem Unterschied zwischen WPF-Frameworkebene und WPF-Kernebene befassen. Sie müssen möglicherweise über die Unterschiede der Ebenen Bescheid wissen, wenn Ihr Anwendungsentwurf eine Vielzahl von Funktionen der WPF-Frameworkebene ersetzt, z.B. wenn Ihre allgemeine Projektmappe schon über eigene Implementierungen der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Zusammenstellung und des -Layouts verfügt.  
  
<a name="subclassing_elements"></a>
## <a name="choosing-which-element-to-derive-from"></a>Auswählen des Elements für die Ableitung  
 Der praktischste Weg, eine benutzerdefinierte Klasse zu erstellen, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erweitert, ist durch Ableiten von einer der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Klassen, wobei Sie so viel Funktionalität wie möglich durch die vorhandene Klassenhierarchie erhalten. In diesem Abschnitt sind die Funktionen aufgeführt, die mit drei der wichtigsten Elementklassen geliefert werden, um Ihnen bei der Entscheidung zu helfen, von welcher Klasse geerbt werden soll.  
  
 Wenn Sie ein Steuerelement implementieren, was wirklich einer der häufigsten Gründe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für die Ableitung von einer Klasse ist, möchten Sie wahrscheinlich von einer Klasse <xref:System.Windows.Controls.Control> ableiten, die ein praktisches Steuerelement, eine Basisklasse für die Steuerelementfamilie oder zumindest von der Basisklasse ist. Einige Leitfäden und praktische Beispiele finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).  
  
 Wenn Sie kein Steuerelement erstellen und von einer Klasse ableiten müssen, die in der Hierarchie höher gestellt ist, sollen Ihnen die folgenden Abschnitte als Leitfaden für die Eigenschaften dienen, die in jeder Basiselementklasse definiert sind.  
  
 Wenn Sie eine Klasse erstellen, <xref:System.Windows.DependencyObject>die von ableitet, erben Sie die folgende Funktion:  
  
- <xref:System.Windows.DependencyObject.GetValue%2A>Unterstützung <xref:System.Windows.DependencyObject.SetValue%2A> und Unterstützung des allgemeinen Eigentumssystems.  
  
- Fähigkeit zum Verwenden von Abhängigkeitseigenschaften und angefügten Eigenschaften, die als Abhängigkeitseigenschaften implementiert sind  
  
 Wenn Sie eine Klasse erstellen, <xref:System.Windows.UIElement>die von ableitet, erben Sie zusätzlich <xref:System.Windows.DependencyObject>zu den Funktionen von :  
  
- Grundlegende Unterstützung für animierte Eigenschaftswerte. Weitere Informationen finden Sie unter [Übersicht über Animation](../graphics-multimedia/animation-overview.md).  
  
- Grundlegende Unterstützung für Eingabeereignisse und Unterstützung für Befehle. Weitere Informationen finden Sie unter [Übersicht über die Eingabe](input-overview.md) und [Befehlsübersicht](commanding-overview.md).  
  
- Virtuelle Methoden, die überschrieben werden können, um Informationen für ein Layoutsystem bereitzustellen.  
  
 Wenn Sie eine Klasse erstellen, <xref:System.Windows.FrameworkElement>die von ableitet, erben Sie zusätzlich <xref:System.Windows.UIElement>zu den Funktionen von :  
  
- Unterstützung für Formatierung und Storyboards. Weitere Informationen finden <xref:System.Windows.Style> Sie unter und [Storyboards Übersicht](../graphics-multimedia/storyboards-overview.md).  
  
- Unterstützung für die Datenbindung. Weitere Informationen finden Sie unter [Datenbindungsübersicht](../../../desktop-wpf/data/data-binding-overview.md).  
  
- Unterstützung für dynamische Ressourcenverweise. Weitere Informationen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Unterstützung für die Eigenschaftswertvererbung und andere Flags in den Metadaten, die Ihnen beim Melden von Bedingungen über Eigenschaften für Frameworkdienste helfen, z.B. Datenbindung, Stile oder die Frameworkimplementierung des Layouts. Weitere Informationen finden Sie unter [Framework-Eigenschaftenmetadaten](framework-property-metadata.md).  
  
- Das Konzept der logischen Struktur. Weitere Informationen finden Sie unter [Strukturen in WPF](trees-in-wpf.md).  
  
- Unterstützung für die praktische Implementierung des Layoutsystems auf <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> WPF-Frameworkebene, einschließlich einer Außerkraftsetzung, die Änderungen an Eigenschaften erkennen kann, die das Layout beeinflussen.  
  
 Wenn Sie eine Klasse erstellen, <xref:System.Windows.ContentElement>die von ableitet, erben Sie zusätzlich <xref:System.Windows.DependencyObject>zu den Funktionen von :  
  
- Unterstützung für Animationen. Weitere Informationen finden Sie unter [Übersicht über Animation](../graphics-multimedia/animation-overview.md).  
  
- Grundlegende Unterstützung für Eingabeereignisse und Unterstützung für Befehle. Weitere Informationen finden Sie unter [Übersicht über die Eingabe](input-overview.md) und [Befehlsübersicht](commanding-overview.md).  
  
 Wenn Sie eine Klasse erstellen, <xref:System.Windows.FrameworkContentElement>die von ableitet, erhalten Sie <xref:System.Windows.ContentElement>zusätzlich zu den Funktionen von :  
  
- Unterstützung für Formatierung und Storyboards. Weitere Informationen finden <xref:System.Windows.Style> Sie unter [Und Animationsübersicht](../graphics-multimedia/animation-overview.md).  
  
- Unterstützung für die Datenbindung. Weitere Informationen finden Sie unter [Datenbindungsübersicht](../../../desktop-wpf/data/data-binding-overview.md).  
  
- Unterstützung für dynamische Ressourcenverweise. Weitere Informationen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Unterstützung für die Eigenschaftswertvererbung und andere Flags in den Metadaten, die Ihnen beim Melden von Bedingungen über Eigenschaften für Frameworkdienste helfen, z.B. Datenbindung, Stile oder die Frameworkimplementierung des Layouts. Weitere Informationen finden Sie unter [Framework-Eigenschaftenmetadaten](framework-property-metadata.md).  
  
- Sie erben keinen Zugriff auf Layoutsystemänderungen <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>(z. B. ). Layoutsystemimplementierungen sind nur <xref:System.Windows.FrameworkElement>auf verfügbar. Sie erben jedoch eine <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> Außerkraftsetzung, die Änderungen an Eigenschaften erkennen kann, die das Layout beeinflussen, und diese an alle Inhaltshosts melden.  
  
 Inhaltsmodelle sind für eine Vielzahl von Klassen dokumentiert. Das Inhaltsmodell für eine Klasse ist ein möglicher Faktor, den Sie berücksichtigen sollten, wenn Sie eine entsprechende Klasse finden möchten, von der Sie ableiten möchten. Weitere Informationen finden Sie unter [WPF-Inhaltsmodell](../controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>
## <a name="other-base-classes"></a>Andere Basisklassen  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject>unterstützt das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Threadingmodell und ermöglicht es, alle Objekte, die für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen erstellt wurden, einer <xref:System.Windows.Threading.Dispatcher>zu zugeordnet werden. Auch wenn Sie nicht <xref:System.Windows.UIElement>von <xref:System.Windows.DependencyObject>ableiten , oder <xref:System.Windows.Media.Visual>, <xref:System.Windows.Threading.DispatcherObject> sollten Sie ableiten, um diese Threadingmodellunterstützung zu erhalten. Weitere Informationen finden Sie unter [Threading-Modell](threading-model.md).  
  
### <a name="visual"></a>Grafisches Element  
 <xref:System.Windows.Media.Visual>implementiert das Konzept eines 2D-Objekts, das in der Regel eine visuelle Darstellung in einem grob rechteckigen Bereich erfordert. Das tatsächliche Rendern einer <xref:System.Windows.Media.Visual> erfolgt in anderen Klassen (es <xref:System.Windows.Media.Visual> ist nicht in sich geschlossen), aber die Klasse stellt einen bekannten Typ bereit, der durch Rendern von Prozessen auf verschiedenen Ebenen verwendet wird. <xref:System.Windows.Media.Visual>implementiert Treffertests, macht jedoch keine Ereignisse verfügbar, die Positive <xref:System.Windows.UIElement>von Treffertests melden (diese sind in ). Weitere Informationen finden Sie unter [Programmierung auf visueller Ebene](../graphics-multimedia/visual-layer-programming.md).  
  
### <a name="freezable"></a>Freezable-Objekt  
 <xref:System.Windows.Freezable>simuliert Unveränderlichkeit in einem veränderlichen Objekt, indem die Möglichkeit zur Verfügung gestellt wird, Kopien des Objekts zu generieren, wenn ein unveränderliches Objekt aus Leistungsgründen erforderlich oder gewünscht wird. Der <xref:System.Windows.Freezable> Typ bietet eine gemeinsame Grundlage für bestimmte Grafikelemente wie Geometrien und Pinsel sowie Animationen. Bemerkenswert ist, <xref:System.Windows.Freezable> a <xref:System.Windows.Media.Visual>ist nicht a ; Sie kann Eigenschaften enthalten, die <xref:System.Windows.Freezable> zu Untereigenschaften werden, wenn der angewendet wird, um einen Eigenschaftswert eines anderen Objekts zu füllen, und diese Untereigenschaften können sich auf das Rendern auswirken. Weitere Informationen finden Sie unter der [Übersicht über Freezable-Objekte](freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable>ist <xref:System.Windows.Freezable> eine abgeleitete Klasse, die speziell die Animationssteuerungsebene und einige Dienstprogrammmember hinzufügt, sodass aktuell animierte Eigenschaften von nicht animierten Eigenschaften unterschieden werden können.  
  
### <a name="control"></a>Control  
 <xref:System.Windows.Controls.Control>ist die beabsichtigte Basisklasse für den Objekttyp, der je nach Technologie als Steuerelement oder Komponente bezeichnet wird. Im allgemeinen sind [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelementklassen Klassen, die entweder direkt ein UI-Steuerelement darstellen oder in der Zusammenstellung der Steuerelemente eng beteiligt sind. Die primäre <xref:System.Windows.Controls.Control> Funktionalität, die aktiviert wird, ist die Steuerung der Templatierung.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Control>
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md)
- [WPF-Architektur](wpf-architecture.md)
