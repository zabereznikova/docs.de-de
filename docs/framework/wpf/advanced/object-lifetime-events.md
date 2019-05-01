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
ms.openlocfilehash: 8ecc3f716061dfd08ac95652d1a9d8e06e26d949
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053222"
---
# <a name="object-lifetime-events"></a>Objektlebensdauer-Ereignisse
In diesem Thema werden die spezifischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignisse beschrieben, die die Phasen einer Objektlebensdauer darstellen (Erstellung, Verwendung und Zerstörung).  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 In diesem Thema wird vorausgesetzt, dass Sie sich mit Abhängigkeitseigenschaften aus Sicht von vorhandenen Abhängigkeitseigenschaften von Consumern in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klassen auskennen und dass Sie das Thema [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) gelesen haben. Um den Beispielen in diesem Thema folgen zu können, sollten Sie [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verstehen (siehe Übersicht über [XAML (WPF)](xaml-overview-wpf.md)) und mit dem Schreiben von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen vertraut sein.  
  
<a name="intro"></a>   
## <a name="object-lifetime-events"></a>Objektlebensdauer-Ereignisse  
 Alle Objekte im verwalteten Microsoft .NET Framework-Code wechseln Sie über eine ähnliche Reihe von Phasen des Lebenszyklus, Erstellung, Verwendung und Zerstörung. Viele Objekte weisen außerdem eine Abschlussphase auf, die Teil der Zerstörungsphase ist. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Objekte, oder genauer gesagt: die visuellen Objekte, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als Elemente identifiziert, weisen zudem eine Reihe von allgemeinen Objektlebensphasen auf. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Programmierungs- und -Anwendungsmodelle stellen diese Phasen als eine Abfolge von Ereignissen dar. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es vier Objekttypen in Bezug auf Lebensdauerereignisse: allgemeine Elemente, Fensterelemente, Navigationshosts und Anwendungsobjekte. Fenster und Navigationshosts befinden sich auch innerhalb der größeren Gruppierung visueller Objekte (Elemente). In diesem Thema werden zunächst die Lebensdauerereignisse beschrieben, die allen Elementen gemeinsam sind. Anschließend wird eine Einführung in spezifischere Elemente gegeben, die sich auf Anwendungsdefinitionen, Fenster oder Navigationshosts beziehen.  
  
<a name="common_events"></a>   
## <a name="common-lifetime-events-for-elements"></a>Allgemeine Lebensdauerereignisse für Elemente  
 Alle WPF-Frameworkebene-Element (diese Objekte Ableiten von entweder <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>) verfügt über drei allgemeine Lebensdauerereignisse: <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded>, und <xref:System.Windows.FrameworkElement.Unloaded>.  
  
### <a name="initialized"></a>Initialisiert  
 <xref:System.Windows.FrameworkElement.Initialized> wird zuerst ausgelöst, und dies durch den Aufruf an den Konstruktor für die Initialisierung des Objekts entspricht. Da das Ereignis in Reaktion auf die Initialisierung eintritt, ist sichergestellt, dass alle Eigenschaften des Objekts festgelegt werden. (Eine Ausnahme sind Ausdrucksverwendungen wie z.B. dynamische Ressourcen oder Bindungen; dies sind nicht ausgewertete Ausdrücke.) Als Folge der Anforderung, die alle Eigenschaften festgelegt werden, die Reihenfolge der <xref:System.Windows.FrameworkElement.Initialized> von geschachtelten Elementen, die im Markup definierte ausgelöst werden zunächst in der untersten Elemente in der Elementstruktur auftreten wird dann an die übergeordnete Elemente in Richtung Stammelement. Diese Reihenfolge wird eingehalten, da die Beziehungen zwischen übergeordneten und untergeordneten Elementen und die Kapselung Eigenschaften sind und daher das übergeordnete Element erst die Initialisierung berichten kann, wenn die untergeordneten Elemente, die die Eigenschaft ausfüllen, auch vollständig initialisiert werden.  
  
 Wenn Sie Handler als Reaktion auf schreiben die <xref:System.Windows.FrameworkElement.Initialized> Ereignis müssen Sie berücksichtigen, dass es keine Garantie gibt, dass alle anderen Elemente in der Elementstruktur auf, in dem der Handler angefügt ist (entweder logische Struktur oder visuelle Struktur), vor allem erstellt wurden übergeordnete Elemente. Membervariablen sind möglicherweise NULL, oder Datenquellen sind unter Umständen noch nicht durch die zugrunde liegende Bindung gefüllt (auch nicht auf Ausdrucksebene).  
  
### <a name="loaded"></a>Geladen  
 <xref:System.Windows.FrameworkElement.Loaded> als Nächstes ausgeführt wird. Die <xref:System.Windows.FrameworkElement.Loaded> Ereignis wird vor dem endgültigen Rendern, aber nach der Berechnung der nötigen Werte für das Rendering durch das Layoutsystem ausgelöst. <xref:System.Windows.FrameworkElement.Loaded> zur Folge, dass die logische Struktur, der in ein Element enthalten ist abgeschlossen ist, und eine Verbindung mit einer Präsentationsquelle, die das HWND und die Renderingoberfläche bereitstellt. Standard-Datenbindung (Bindungen zu lokalen Quellen, wie andere Eigenschaften oder direkt definierte Datenquellen) werden aufgetreten vor <xref:System.Windows.FrameworkElement.Loaded>. Asynchrone Datenbindungen (externe oder dynamische Quellen) sind möglicherweise aufgetreten; dies kann jedoch aufgrund ihrer asynchronen Natur nicht garantiert werden.  
  
 Der Mechanismus, mit dem die <xref:System.Windows.FrameworkElement.Loaded> Ereignis wird ausgelöst, unterscheidet sich von <xref:System.Windows.FrameworkElement.Initialized>. Die <xref:System.Windows.FrameworkElement.Initialized> -Ereignis wird elementweise ausgelöst, ohne eine direkte Koordination durch eine vollständige Elementstruktur. Im Gegensatz dazu die <xref:System.Windows.FrameworkElement.Loaded> Ereignis wird ausgelöst, während die gesamte Elementstruktur (insbesondere der logischen Struktur) koordiniert. Wenn alle Elemente in der Struktur in einem Zustand, in denen sie berücksichtigt werden, geladen, die <xref:System.Windows.FrameworkElement.Loaded> -Ereignis zunächst für das Stammelement ausgelöst wird. Die <xref:System.Windows.FrameworkElement.Loaded> -Ereignis wird dann nacheinander für jedes untergeordnete Element ausgelöst.  
  
> [!NOTE]
>  Dieses Verhalten ähnelt oberflächlich betrachtet dem Tunneln für ein Routingereignis. Allerdings werden hier keine Informationen von Ereignis zu Ereignis transportiert. Jedes Element hat immer die Möglichkeit, verarbeiten die <xref:System.Windows.FrameworkElement.Loaded> -Ereignis, und markieren die Ereignisdaten als behandelt wirkt sich nicht nur auf dieses Element.  
  
### <a name="unloaded"></a>Nicht Geladen  
 <xref:System.Windows.FrameworkElement.Unloaded> wird als Letztes ausgelöst und wird durch die Präsentationsquelle oder das übergeordnete visuelle Element entfernt wird. Wenn <xref:System.Windows.FrameworkElement.Unloaded> ausgelöst und behandelt, das Element, das das übergeordnete Element Event-Quelle ist (gemäß <xref:System.Windows.FrameworkElement.Parent%2A> Eigenschaft) oder ein bestimmtes Element oben in der logischen oder visuellen Strukturen wurde möglicherweise bereits Plattformmetadaten aufgehoben wird, was bedeutet, dass die Datenbindung, Ressourcenverweise , und Stile können nicht auf ihre normalen oder zuletzt bekannten Laufzeitwerte festgelegt werden.  
  
<a name="application_model_elements"></a>   
## <a name="lifetime-events-application-model-elements"></a>Anwendungsmodellelemente für Lebensdauerereignisse  
 Aufbauend auf den allgemeinen Lebensdauerereignissen sind folgende Anwendungsmodellelemente: <xref:System.Windows.Application>, <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, und <xref:System.Windows.Controls.Frame>. Mit ihnen können die allgemeinen Lebensdauerereignisse, um zusätzliche Ereignisse erweitert werden, die relevant für ihren speziellen Zweck sind. Sie werden im Detail in folgenden Themen erläutert:  
  
- <xref:System.Windows.Application>: [Übersicht über die Anwendungsverwaltung](../app-development/application-management-overview.md).  
  
- <xref:System.Windows.Window>: [Übersicht über WPF-Windows](../app-development/wpf-windows-overview.md).  
  
- <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, und <xref:System.Windows.Controls.Frame>: [Übersicht über die Navigation](../app-development/navigation-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md)
- [Übersicht über Routingereignisse](routed-events-overview.md)
