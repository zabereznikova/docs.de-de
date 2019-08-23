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
ms.openlocfilehash: dd2e116c4241a44786af3a56b931b0c3c0571814
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933487"
---
# <a name="object-lifetime-events"></a>Objektlebensdauer-Ereignisse
In diesem Thema werden die spezifischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignisse beschrieben, die die Phasen einer Objektlebensdauer darstellen (Erstellung, Verwendung und Zerstörung).  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 In diesem Thema wird vorausgesetzt, dass Sie sich mit Abhängigkeitseigenschaften aus Sicht von vorhandenen Abhängigkeitseigenschaften von Consumern in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klassen auskennen und dass Sie das Thema [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) gelesen haben. Um den Beispielen in diesem Thema folgen zu können, sollten Sie [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verstehen (siehe Übersicht über [XAML (WPF)](xaml-overview-wpf.md)) und mit dem Schreiben von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen vertraut sein.  
  
<a name="intro"></a>   
## <a name="object-lifetime-events"></a>Objektlebensdauer-Ereignisse  
 Alle Objekte in verwaltetem Code Microsoft .NET Framework durchlaufen einen ähnlichen Satz von Lebensphasen, Erstellung, Verwendung und Zerstörung. Viele Objekte weisen außerdem eine Abschlussphase auf, die Teil der Zerstörungsphase ist. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Objekte, oder genauer gesagt: die visuellen Objekte, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als Elemente identifiziert, weisen zudem eine Reihe von allgemeinen Objektlebensphasen auf. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Programmierungs- und -Anwendungsmodelle stellen diese Phasen als eine Abfolge von Ereignissen dar. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es vier Objekttypen in Bezug auf Lebensdauerereignisse: allgemeine Elemente, Fensterelemente, Navigationshosts und Anwendungsobjekte. Fenster und Navigationshosts befinden sich auch innerhalb der größeren Gruppierung visueller Objekte (Elemente). In diesem Thema werden zunächst die Lebensdauerereignisse beschrieben, die allen Elementen gemeinsam sind. Anschließend wird eine Einführung in spezifischere Elemente gegeben, die sich auf Anwendungsdefinitionen, Fenster oder Navigationshosts beziehen.  
  
<a name="common_events"></a>   
## <a name="common-lifetime-events-for-elements"></a>Allgemeine Lebensdauerereignisse für Elemente  
 Alle Elemente auf WPF-Frameworkebene (die Objekte <xref:System.Windows.FrameworkElement> , <xref:System.Windows.FrameworkContentElement>die von oder abgeleitet werden) haben <xref:System.Windows.FrameworkElement.Initialized>drei allgemeine Lebens <xref:System.Windows.FrameworkElement.Unloaded>Dauer Ereignisse:, <xref:System.Windows.FrameworkElement.Loaded>und.  
  
### <a name="initialized"></a>Initialisiert  
 <xref:System.Windows.FrameworkElement.Initialized>wird zuerst ausgelöst und entspricht ungefähr der Initialisierung des-Objekts durch den-Konstruktor. Da das Ereignis in Reaktion auf die Initialisierung eintritt, ist sichergestellt, dass alle Eigenschaften des Objekts festgelegt werden. (Eine Ausnahme sind Ausdrucksverwendungen wie z.B. dynamische Ressourcen oder Bindungen; dies sind nicht ausgewertete Ausdrücke.) Als Folge der Anforderung, dass alle Eigenschaften festgelegt werden, scheint die Sequenz <xref:System.Windows.FrameworkElement.Initialized> , die von geschposteten Elementen ausgelöst wird, die in Markup definiert sind, in der Reihenfolge der tiefsten Elemente in der Elementstruktur und dann der übergeordneten Elemente in Richtung des Stamms auftreten. Diese Reihenfolge wird eingehalten, da die Beziehungen zwischen übergeordneten und untergeordneten Elementen und die Kapselung Eigenschaften sind und daher das übergeordnete Element erst die Initialisierung berichten kann, wenn die untergeordneten Elemente, die die Eigenschaft ausfüllen, auch vollständig initialisiert werden.  
  
 Wenn Sie Handler als Reaktion auf das <xref:System.Windows.FrameworkElement.Initialized> -Ereignis schreiben, müssen Sie Bedenken, dass es keine Garantie gibt, dass alle anderen Elemente in der Elementstruktur (entweder logische Struktur oder visuelle Struktur), an die der Handler angefügt ist, erstellt wurden, insbesondere übergeordnete Elemente. Membervariablen sind möglicherweise NULL, oder Datenquellen sind unter Umständen noch nicht durch die zugrunde liegende Bindung gefüllt (auch nicht auf Ausdrucksebene).  
  
### <a name="loaded"></a>Geladen  
 <xref:System.Windows.FrameworkElement.Loaded>wird als nächstes ausgelöst. Das <xref:System.Windows.FrameworkElement.Loaded> -Ereignis wird vor dem endgültigen Rendering ausgelöst, aber nachdem das Layoutsystem alle für das Rendering erforderlichen Werte berechnet hat. <xref:System.Windows.FrameworkElement.Loaded>umfasst, dass die logische Struktur, in der ein Element enthalten ist, abgeschlossen ist, und stellt eine Verbindung mit einer Präsentations Quelle her, die das HWND und die Renderingoberfläche bereitstellt. Die Standard Datenbindung (Bindung an lokale Quellen, z <xref:System.Windows.FrameworkElement.Loaded>. b. andere Eigenschaften oder direkt definierte Datenquellen) ist vor aufgetreten. Asynchrone Datenbindungen (externe oder dynamische Quellen) sind möglicherweise aufgetreten; dies kann jedoch aufgrund ihrer asynchronen Natur nicht garantiert werden.  
  
 Der Mechanismus, mit dem <xref:System.Windows.FrameworkElement.Loaded> das-Ereignis ausgelöst wird, <xref:System.Windows.FrameworkElement.Initialized>unterscheidet sich von. Das <xref:System.Windows.FrameworkElement.Initialized> Ereignis wird durch ein Element nach Element ausgelöst, ohne dass eine direkte Koordination durch eine abgeschlossene Elementstruktur besteht. Im Gegensatz dazu wird <xref:System.Windows.FrameworkElement.Loaded> das-Ereignis in der gesamten Elementstruktur als koordinierter Aufwand ausgelöst (insbesondere die logische Struktur). Wenn sich alle Elemente in der Struktur in einem Zustand befinden, in dem Sie als geladen <xref:System.Windows.FrameworkElement.Loaded> angesehen werden, wird das-Ereignis zuerst für das root-Element ausgelöst. Das <xref:System.Windows.FrameworkElement.Loaded> -Ereignis wird dann nacheinander für jedes untergeordnete Element ausgelöst.  
  
> [!NOTE]
> Dieses Verhalten ähnelt oberflächlich betrachtet dem Tunneln für ein Routingereignis. Allerdings werden hier keine Informationen von Ereignis zu Ereignis transportiert. Jedes Element hat immer die Möglichkeit, sein <xref:System.Windows.FrameworkElement.Loaded> Ereignis zu behandeln, und das Markieren der Ereignisdaten als behandelt hat keine Auswirkung über dieses Element hinaus.  
  
### <a name="unloaded"></a>Nicht Geladen  
 <xref:System.Windows.FrameworkElement.Unloaded>wird zuletzt ausgelöst und wird entweder von der Präsentations Quelle oder vom visuellen übergeordneten Element initiiert, das entfernt wird. Wenn <xref:System.Windows.FrameworkElement.Unloaded> ausgelöst und behandelt wird, kann das Element, das das übergeordnete Ereignis Quell Element ist <xref:System.Windows.FrameworkElement.Parent%2A> (wie von der Eigenschaft festgelegt), oder ein beliebiges Element nach oben in den logischen oder visuellen Strukturen nicht mehr festgelegt worden sein. Dies bedeutet, dass die Datenbindung, Ressourcen Verweise -und-Stile dürfen nicht auf Ihren normalen oder letzten bekannten Lauf Zeitwert festgelegt werden.  
  
<a name="application_model_elements"></a>   
## <a name="lifetime-events-application-model-elements"></a>Anwendungsmodellelemente für Lebensdauerereignisse  
 Das aufbauen der allgemeinen Lebensdauer Ereignisse für Elemente sind die folgenden Anwendungsmodell Elemente <xref:System.Windows.Application>: <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, und <xref:System.Windows.Controls.Frame>. Mit ihnen können die allgemeinen Lebensdauerereignisse, um zusätzliche Ereignisse erweitert werden, die relevant für ihren speziellen Zweck sind. Sie werden im Detail in folgenden Themen erläutert:  
  
- <xref:System.Windows.Application>: [Übersicht über die Anwendungs Verwaltung](../app-development/application-management-overview.md).  
  
- <xref:System.Windows.Window>: [Übersicht über WPF-Fenster](../app-development/wpf-windows-overview.md).  
  
- <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>und :<xref:System.Windows.Controls.Frame> [Navigations Übersicht](../app-development/navigation-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md)
- [Übersicht über Routingereignisse](routed-events-overview.md)
