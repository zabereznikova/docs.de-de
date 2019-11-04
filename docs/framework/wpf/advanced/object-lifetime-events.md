---
title: Objektlebensdauer-Ereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- events [WPF], ContentRendered
- events [WPF], Deactivated
- events [WPF], Unloaded
- Activated events [WPF]
- events [WPF], Loaded
- Application objects [WPF], lifetime events
- events [WPF], Activated
- ContentRendered events [WPF]
- Deactivated events [WPF]
- events [WPF], Initialized
- events [WPF], Closing
- Unloaded events [WPF]
- exit events [WPF]
- objects' lifetime events [WPF]
- Loaded events [WPF]
- Closing events [WPF]
- events [WPF], Closed
- Initialized events [WPF]
- Closed events [WPF]
- startup events [WPF]
- lifetime events of objects [WPF]
ms.assetid: face6fc7-465b-4502-bfe5-e88d2e729a78
ms.openlocfilehash: c0858a0194bc0e9efa60a42d4029bdba9f4f3fef
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458573"
---
# <a name="object-lifetime-events"></a>Objektlebensdauer-Ereignisse
In diesem Thema werden die spezifischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignisse beschrieben, die die Phasen einer Objektlebensdauer darstellen (Erstellung, Verwendung und Zerstörung).  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Voraussetzungen  
 In diesem Thema wird vorausgesetzt, dass Sie sich mit Abhängigkeitseigenschaften aus Sicht von vorhandenen Abhängigkeitseigenschaften von Consumern in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klassen auskennen und dass Sie das Thema [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) gelesen haben. Um den Beispielen in diesem Thema folgen zu können, sollten Sie [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verstehen (siehe Übersicht über [XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)) und mit dem Schreiben von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen vertraut sein.  
  
<a name="intro"></a>   
## <a name="object-lifetime-events"></a>Objektlebensdauer-Ereignisse  
 Alle Objekte in verwaltetem Code Microsoft .NET Framework durchlaufen einen ähnlichen Satz von Lebensphasen, Erstellung, Verwendung und Zerstörung. Viele Objekte weisen außerdem eine Abschlussphase auf, die Teil der Zerstörungsphase ist. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Objekte, oder genauer gesagt: die visuellen Objekte, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als Elemente identifiziert, weisen zudem eine Reihe von allgemeinen Objektlebensphasen auf. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Programmierungs- und -Anwendungsmodelle stellen diese Phasen als eine Abfolge von Ereignissen dar. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es vier Objekttypen in Bezug auf Lebensdauerereignisse: allgemeine Elemente, Fensterelemente, Navigationshosts und Anwendungsobjekte. Fenster und Navigationshosts befinden sich auch innerhalb der größeren Gruppierung visueller Objekte (Elemente). In diesem Thema werden zunächst die Lebensdauerereignisse beschrieben, die allen Elementen gemeinsam sind. Anschließend wird eine Einführung in spezifischere Elemente gegeben, die sich auf Anwendungsdefinitionen, Fenster oder Navigationshosts beziehen.  
  
<a name="common_events"></a>   
## <a name="common-lifetime-events-for-elements"></a>Allgemeine Lebensdauerereignisse für Elemente  
 Alle Elemente auf WPF-Frameworkebene (die Objekte, die von <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>abgeleitet werden) haben drei allgemeine Lebensdauer Ereignisse: <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded>und <xref:System.Windows.FrameworkElement.Unloaded>.  
  
### <a name="initialized"></a>Initialisiert  
 <xref:System.Windows.FrameworkElement.Initialized> wird zuerst ausgelöst und entspricht ungefähr der Initialisierung des Objekts durch den aufrufkonstruktor. Da das Ereignis in Reaktion auf die Initialisierung eintritt, ist sichergestellt, dass alle Eigenschaften des Objekts festgelegt werden. (Eine Ausnahme sind Ausdrucks Verwendungen, wie z. b. dynamische Ressourcen oder Bindungen. Dies sind nicht ausgewertete Ausdrücke.) Als Folge der Anforderung, dass alle Eigenschaften festgelegt werden, scheint die Sequenz der <xref:System.Windows.FrameworkElement.Initialized>, die von geschposteten Elementen ausgelöst werden, die in Markup definiert sind, in der Reihenfolge der tiefstlegenden Elemente in der Elementstruktur und dann den übergeordneten Elementen in Richtung des Stamms auftreten. Diese Reihenfolge wird eingehalten, da die Beziehungen zwischen übergeordneten und untergeordneten Elementen und die Kapselung Eigenschaften sind und daher das übergeordnete Element erst die Initialisierung berichten kann, wenn die untergeordneten Elemente, die die Eigenschaft ausfüllen, auch vollständig initialisiert werden.  
  
 Wenn Sie Handler als Reaktion auf das <xref:System.Windows.FrameworkElement.Initialized>-Ereignis schreiben, müssen Sie Bedenken, dass es keine Garantie gibt, dass alle anderen Elemente in der Elementstruktur (entweder logische Struktur oder visuelle Struktur), an die der Handler angefügt ist, erstellt wurden, besonders übergeordnet. Aspekte. Membervariablen sind möglicherweise NULL, oder Datenquellen sind unter Umständen noch nicht durch die zugrunde liegende Bindung gefüllt (auch nicht auf Ausdrucksebene).  
  
### <a name="loaded"></a>Geladen  
 <xref:System.Windows.FrameworkElement.Loaded> wird als nächstes ausgelöst. Das <xref:System.Windows.FrameworkElement.Loaded>-Ereignis wird vor dem endgültigen Rendering ausgelöst, aber nachdem das Layoutsystem alle für das Rendering erforderlichen Werte berechnet hat. <xref:System.Windows.FrameworkElement.Loaded> bedeutet, dass die logische Struktur, in der ein Element enthalten ist, abgeschlossen ist, und stellt eine Verbindung mit einer Präsentations Quelle her, die das HWND und die Renderingoberfläche bereitstellt. Die Standard Datenbindung (Bindung an lokale Quellen, z. b. andere Eigenschaften oder direkt definierte Datenquellen) ist vor <xref:System.Windows.FrameworkElement.Loaded>aufgetreten. Asynchrone Datenbindungen (externe oder dynamische Quellen) sind möglicherweise aufgetreten; dies kann jedoch aufgrund ihrer asynchronen Natur nicht garantiert werden.  
  
 Der Mechanismus, mit dem das <xref:System.Windows.FrameworkElement.Loaded>-Ereignis ausgelöst wird, unterscheidet sich von <xref:System.Windows.FrameworkElement.Initialized>. Das <xref:System.Windows.FrameworkElement.Initialized> Ereignis wird Element Weise ausgelöst, ohne dass eine abgeschlossene Elementstruktur direkt koordiniert wird. Im Gegensatz dazu wird das <xref:System.Windows.FrameworkElement.Loaded>-Ereignis als koordinierter Aufwand in der gesamten Elementstruktur ausgelöst (insbesondere die logische Struktur). Wenn sich alle Elemente in der Struktur in einem Zustand befinden, in dem Sie als geladen angesehen werden, wird das <xref:System.Windows.FrameworkElement.Loaded> Ereignis zuerst für das Stamm Element ausgelöst. Das <xref:System.Windows.FrameworkElement.Loaded>-Ereignis wird dann nacheinander für jedes untergeordnete Element ausgelöst.  
  
> [!NOTE]
> Dieses Verhalten ähnelt oberflächlich betrachtet dem Tunneln für ein Routingereignis. Allerdings werden hier keine Informationen von Ereignis zu Ereignis transportiert. Jedes Element hat immer die Möglichkeit, das <xref:System.Windows.FrameworkElement.Loaded> Ereignis zu behandeln, und das Markieren der Ereignisdaten als behandelt hat keine Auswirkung über dieses Element hinaus.  
  
### <a name="unloaded"></a>Nicht Geladen  
 <xref:System.Windows.FrameworkElement.Unloaded> wird zuletzt ausgelöst und wird entweder von der Präsentations Quelle oder vom visuellen übergeordneten Element initiiert, das entfernt wird. Wenn <xref:System.Windows.FrameworkElement.Unloaded> ausgelöst und behandelt wird, kann das Element, das das übergeordnete Ereignis Quell Element ist (wie durch <xref:System.Windows.FrameworkElement.Parent%2A>-Eigenschaft festgelegt), oder ein beliebiges Element nach oben in den logischen oder visuellen Strukturen nicht festgelegt worden sein. Dies bedeutet, dass Datenbindung, Ressourcen Verweise und Stile vorhanden sind. kann nicht auf den normalen oder den letzten bekannten Lauf Zeitwert festgelegt werden.  
  
<a name="application_model_elements"></a>   
## <a name="lifetime-events-application-model-elements"></a>Anwendungsmodellelemente für Lebensdauerereignisse  
 Das aufbauen der allgemeinen Lebensdauer Ereignisse für Elemente sind die folgenden Anwendungsmodell Elemente: <xref:System.Windows.Application>, <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>und <xref:System.Windows.Controls.Frame>. Mit ihnen können die allgemeinen Lebensdauerereignisse, um zusätzliche Ereignisse erweitert werden, die relevant für ihren speziellen Zweck sind. Sie werden im Detail in folgenden Themen erläutert:  
  
- <xref:System.Windows.Application>: [Übersicht über die Anwendungs Verwaltung](../app-development/application-management-overview.md).  
  
- <xref:System.Windows.Window>: [Übersicht über WPF-Fenster](../app-development/wpf-windows-overview.md).  
  
- <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>und <xref:System.Windows.Controls.Frame>: [Navigations Übersicht](../app-development/navigation-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md)
- [Übersicht über Routingereignisse](routed-events-overview.md)
