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
ms.openlocfilehash: 3b761674bd2464ee87e07d9299c805431f8fdeb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141106"
---
# <a name="object-lifetime-events"></a>Objektlebensdauer-Ereignisse
In diesem Thema werden die spezifischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignisse beschrieben, die die Phasen einer Objektlebensdauer darstellen (Erstellung, Verwendung und Zerstörung).  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 In diesem Thema wird vorausgesetzt, dass Sie sich mit Abhängigkeitseigenschaften aus Sicht von vorhandenen Abhängigkeitseigenschaften von Consumern in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klassen auskennen, und dass Sie das Thema [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) gelesen haben. Um den Beispielen in diesem Thema folgen zu können, sollten Sie [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verstehen (siehe Übersicht über [XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)) und mit dem Schreiben von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen vertraut sein.  
  
<a name="intro"></a>
## <a name="object-lifetime-events"></a>Objektlebensdauer-Ereignisse  
 Alle Objekte in verwaltetem Microsoft .NET Framework-Code durchlaufen ähnliche Lebens-, Erstellungs-, Verwendungs- und Zerstörungsphasen. Viele Objekte weisen außerdem eine Abschlussphase auf, die Teil der Zerstörungsphase ist. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Objekte, oder genauer gesagt: die visuellen Objekte, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als Elemente identifiziert, weisen zudem eine Reihe von allgemeinen Objektlebensphasen auf. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Programmierungs- und -Anwendungsmodelle stellen diese Phasen als eine Abfolge von Ereignissen dar. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es vier Objekttypen in Bezug auf Lebensdauerereignisse: allgemeine Elemente, Fensterelemente, Navigationshosts und Anwendungsobjekte. Fenster und Navigationshosts befinden sich auch innerhalb der größeren Gruppierung visueller Objekte (Elemente). In diesem Thema werden zunächst die Lebensdauerereignisse beschrieben, die allen Elementen gemeinsam sind. Anschließend wird eine Einführung in spezifischere Elemente gegeben, die sich auf Anwendungsdefinitionen, Fenster oder Navigationshosts beziehen.  
  
<a name="common_events"></a>
## <a name="common-lifetime-events-for-elements"></a>Allgemeine Lebensdauerereignisse für Elemente  
 Jedes WPF-Framework-Level-Element <xref:System.Windows.FrameworkElement> (die Objekte, <xref:System.Windows.FrameworkContentElement>die von einem <xref:System.Windows.FrameworkElement.Initialized>oder <xref:System.Windows.FrameworkElement.Loaded>) <xref:System.Windows.FrameworkElement.Unloaded>abgeleitet werden, weist drei allgemeine Lebensdauerereignisse auf: , , und .  
  
### <a name="initialized"></a>Initialisiert  
 <xref:System.Windows.FrameworkElement.Initialized>wird zuerst ausgelöst und entspricht in etwa der Initialisierung des Objekts durch den Aufruf seines Konstruktors. Da das Ereignis in Reaktion auf die Initialisierung eintritt, ist sichergestellt, dass alle Eigenschaften des Objekts festgelegt werden. (Eine Ausnahme sind Ausdrucksverwendungen wie dynamische Ressourcen oder Bindung; diese werden nicht ausgewertete Ausdrücke sein.) Als Folge der Anforderung, dass alle Eigenschaften <xref:System.Windows.FrameworkElement.Initialized> festgelegt sind, scheint die Reihenfolge, die von geschachtelten Elementen ausgelöst wird, die in Markup definiert sind, zuerst in der Reihenfolge der tiefsten Elemente in der Elementstruktur und dann in übergeordneteN Elementen in Richtung des Stamms zu erfolgen. Diese Reihenfolge wird eingehalten, da die Beziehungen zwischen übergeordneten und untergeordneten Elementen und die Kapselung Eigenschaften sind und daher das übergeordnete Element erst die Initialisierung berichten kann, wenn die untergeordneten Elemente, die die Eigenschaft ausfüllen, auch vollständig initialisiert werden.  
  
 Wenn Sie Handler als Reaktion <xref:System.Windows.FrameworkElement.Initialized> auf das Ereignis schreiben, müssen Sie berücksichtigen, dass keine Garantie dafür besteht, dass alle anderen Elemente in der Elementstruktur (entweder logische Struktur oder visuelle Struktur) um den Zugeordneter zugeordnet wurden, insbesondere übergeordnete Elemente. Membervariablen sind möglicherweise NULL, oder Datenquellen sind unter Umständen noch nicht durch die zugrunde liegende Bindung gefüllt (auch nicht auf Ausdrucksebene).  
  
### <a name="loaded"></a>Geladen  
 <xref:System.Windows.FrameworkElement.Loaded>wird als nächstes angehoben. Das <xref:System.Windows.FrameworkElement.Loaded> Ereignis wird vor dem endgültigen Rendering ausgelöst, aber nachdem das Layoutsystem alle für das Rendern erforderlichen Werte berechnet hat. <xref:System.Windows.FrameworkElement.Loaded>bedeutet, dass die logische Struktur, in der sich ein Element befindet, vollständig ist und eine Verbindung mit einer Präsentationsquelle herstellt, die die HWND- und die Renderoberfläche bereitstellt. Die Standarddatenbindung (Bindung an lokale Quellen, z. B. andere <xref:System.Windows.FrameworkElement.Loaded>Eigenschaften oder direkt definierte Datenquellen) ist vor erfolgt. Asynchrone Datenbindungen (externe oder dynamische Quellen) sind möglicherweise aufgetreten; dies kann jedoch aufgrund ihrer asynchronen Natur nicht garantiert werden.  
  
 Der Mechanismus, <xref:System.Windows.FrameworkElement.Loaded> mit dem das <xref:System.Windows.FrameworkElement.Initialized>Ereignis ausgelöst wird, unterscheidet sich von . Das <xref:System.Windows.FrameworkElement.Initialized> Ereignis wird Element für Element ausgelöst, ohne direkte Koordination durch eine abgeschlossene Elementstruktur. Im Gegensatz <xref:System.Windows.FrameworkElement.Loaded> dazu wird das Ereignis als koordinierter Aufwand im gesamten Elementbaum (insbesondere dem logischen Baum) ausgelöst. Wenn sich alle Elemente in der Struktur in einem <xref:System.Windows.FrameworkElement.Loaded> Zustand befinden, in dem sie als geladen betrachtet werden, wird das Ereignis zuerst für das Stammelement ausgelöst. Das <xref:System.Windows.FrameworkElement.Loaded> Ereignis wird dann sukzessive für jedes untergeordnete Element ausgelöst.  
  
> [!NOTE]
> Dieses Verhalten ähnelt oberflächlich betrachtet dem Tunneln für ein Routingereignis. Allerdings werden hier keine Informationen von Ereignis zu Ereignis transportiert. Jedes Element hat immer die <xref:System.Windows.FrameworkElement.Loaded> Möglichkeit, sein Ereignis zu behandeln, und das Markieren der Ereignisdaten als behandelt hat keine Auswirkungen über dieses Element hinaus.  
  
### <a name="unloaded"></a>Nicht Geladen  
 <xref:System.Windows.FrameworkElement.Unloaded>wird zuletzt ausgelöst und entweder von der Präsentationsquelle oder dem entfernten visuellen übergeordneten Element initiiert. Wenn <xref:System.Windows.FrameworkElement.Unloaded> das Element, das das übergeordnete Element der Ereignisquelle <xref:System.Windows.FrameworkElement.Parent%2A> ist (wie durch Eigenschaft bestimmt), oder ein beliebiges bestimmtes Element nach oben in den logischen oder visuellen Strukturen bereits nicht gesetzt wurde, wurde das Element, das das übergeordnete Element der Ereignisquelle ist (wie durch Eigenschaft bestimmt), möglicherweise bereits nicht festgelegt, was bedeutet, dass Datenbindung, Ressourcenverweise und Stile möglicherweise nicht auf ihren normalen oder letzten bekannten Laufzeitwert festgelegt werden.  
  
<a name="application_model_elements"></a>
## <a name="lifetime-events-application-model-elements"></a>Anwendungsmodellelemente für Lebensdauerereignisse  
 Aufbauend auf den allgemeinen Lebensdauerereignissen für Elemente <xref:System.Windows.Application> <xref:System.Windows.Window>sind <xref:System.Windows.Controls.Page> <xref:System.Windows.Navigation.NavigationWindow>die <xref:System.Windows.Controls.Frame>folgenden Anwendungsmodellelemente: , , , und . Mit ihnen können die allgemeinen Lebensdauerereignisse, um zusätzliche Ereignisse erweitert werden, die relevant für ihren speziellen Zweck sind. Sie werden im Detail in folgenden Themen erläutert:  
  
- <xref:System.Windows.Application>: [Application Management Übersicht](../app-development/application-management-overview.md).  
  
- <xref:System.Windows.Window>: [WPF Windows Übersicht](../app-development/wpf-windows-overview.md).  
  
- <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>und <xref:System.Windows.Controls.Frame>: [Navigationsübersicht](../app-development/navigation-overview.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Dependency-Eigenschaftswert-Priorität](dependency-property-value-precedence.md)
- [Übersicht über Routingereignisse](routed-events-overview.md)
