---
title: Objektlebensdauer-Ereignisse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81bd06811e428645a9a3103be457d30266a353c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="object-lifetime-events"></a>Objektlebensdauer-Ereignisse
In diesem Thema werden die spezifischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignisse beschrieben, die die Phasen einer Objektlebensdauer darstellen (Erstellung, Verwendung und Zerstörung).  
  

  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird vorausgesetzt, dass Sie sich mit Abhängigkeitseigenschaften aus Sicht von vorhandenen Abhängigkeitseigenschaften von Consumern in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klassen auskennen und dass Sie das Thema [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) gelesen haben. Um den Beispielen in diesem Thema folgen zu können, sollten Sie [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verstehen (siehe Übersicht über [XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)) und mit dem Schreiben von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen vertraut sein.  
  
<a name="intro"></a>   
## <a name="object-lifetime-events"></a>Objektlebensdauer-Ereignisse  
 Alle Objekte in verwaltetem Code von [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] durchlaufen ähnliche Lebensphasen: Erstellung, Verwendung und Zerstörung. Viele Objekte weisen außerdem eine Abschlussphase auf, die Teil der Zerstörungsphase ist. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Objekte, oder genauer gesagt: die visuellen Objekte, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als Elemente identifiziert, weisen zudem eine Reihe von allgemeinen Objektlebensphasen auf. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Programmierungs- und -Anwendungsmodelle stellen diese Phasen als eine Abfolge von Ereignissen dar. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es vier Objekttypen in Bezug auf Lebensdauerereignisse: allgemeine Elemente, Fensterelemente, Navigationshosts und Anwendungsobjekte. Fenster und Navigationshosts befinden sich auch innerhalb der größeren Gruppierung visueller Objekte (Elemente). In diesem Thema werden zunächst die Lebensdauerereignisse beschrieben, die allen Elementen gemeinsam sind. Anschließend wird eine Einführung in spezifischere Elemente gegeben, die sich auf Anwendungsdefinitionen, Fenster oder Navigationshosts beziehen.  
  
<a name="common_events"></a>   
## <a name="common-lifetime-events-for-elements"></a>Allgemeine Lebensdauerereignisse für Elemente  
 Jedes Element der WPF-Frameworkebene (diese Objekte Ableiten von entweder <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>) verfügt über drei allgemeine Lebensdauerereignisse: <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded>, und <xref:System.Windows.FrameworkElement.Unloaded>.  
  
### <a name="initialized"></a>Initialisiert  
 <xref:System.Windows.FrameworkElement.Initialized>wird zuerst ausgelöst, und ungefähr durch den Aufruf an den Konstruktor der Initialisierung des Objekts entspricht. Da das Ereignis in Reaktion auf die Initialisierung eintritt, ist sichergestellt, dass alle Eigenschaften des Objekts festgelegt werden. (Eine Ausnahme sind Ausdrucksverwendungen wie z.B. dynamische Ressourcen oder Bindungen; dies sind nicht ausgewertete Ausdrücke.) Als Folge der Anforderung, die alle Eigenschaften festgelegt werden, die Abfolge der <xref:System.Windows.FrameworkElement.Initialized> von geschachtelten Elementen, die im Markup definierte ausgelöst wird zunächst in der Reihenfolge der tiefsten Elementen in der Elementstruktur auftreten wird dann an die übergeordnete Elemente auf den Stamm. Diese Reihenfolge wird eingehalten, da die Beziehungen zwischen übergeordneten und untergeordneten Elementen und die Kapselung Eigenschaften sind und daher das übergeordnete Element erst die Initialisierung berichten kann, wenn die untergeordneten Elemente, die die Eigenschaft ausfüllen, auch vollständig initialisiert werden.  
  
 Wenn Sie Ereignishandler als Antwort auf Schreiben der <xref:System.Windows.FrameworkElement.Initialized> Ereignis müssen Sie berücksichtigen, keine Garantie besteht, dass alle anderen Elemente in der Elementstruktur (logische Struktur oder visuellen Struktur) umgehen, in dem der Handler angefügt ist, vor allem erstellt wurden übergeordnete Elemente. Membervariablen sind möglicherweise NULL, oder Datenquellen sind unter Umständen noch nicht durch die zugrunde liegende Bindung gefüllt (auch nicht auf Ausdrucksebene).  
  
### <a name="loaded"></a>Geladen  
 <xref:System.Windows.FrameworkElement.Loaded>als Nächstes ausgelöst wird. Die <xref:System.Windows.FrameworkElement.Loaded> Ereignis wird ausgelöst, vor dem endgültigen Rendern, aber nachdem das Layoutsystem alle erforderlichen Werte für das Rendering berechnet wurde. <xref:System.Windows.FrameworkElement.Loaded>erfordert, dass die logische Struktur, der in ein Element enthalten ist, abgeschlossen ist und eine Verbindung mit einer Präsentationsquelle, die das HWND und die Darstellungsoberfläche bereitstellt. Standarddaten Bindung (die Bindung an lokale Datenquellen, z. B. andere Eigenschaften oder direkt definierten Datenquellen), wird vor aufgetreten <xref:System.Windows.FrameworkElement.Loaded>. Asynchrone Datenbindungen (externe oder dynamische Quellen) sind möglicherweise aufgetreten; dies kann jedoch aufgrund ihrer asynchronen Natur nicht garantiert werden.  
  
 Der Mechanismus, mit dem die <xref:System.Windows.FrameworkElement.Loaded> Ereignis wird ausgelöst, unterscheidet sich von <xref:System.Windows.FrameworkElement.Initialized>. Die <xref:System.Windows.FrameworkElement.Initialized> Ereignis ist elementweise ausgelöst, ohne eine direkte Koordination durch eine vollständige Elementstruktur. Im Gegensatz dazu, die <xref:System.Windows.FrameworkElement.Loaded> Ereignis wird ausgelöst, während der gesamten Elementstruktur (insbesondere der logischen Struktur) koordiniert. Wenn alle Elemente in der Struktur in einem Zustand, in denen sie berücksichtigt werden, die geladen wird, sind die <xref:System.Windows.FrameworkElement.Loaded> Ereignis wird zuerst für das Stammelement. Die <xref:System.Windows.FrameworkElement.Loaded> -Ereignis wird für jedes untergeordnete Element klicken Sie dann nacheinander ausgelöst.  
  
> [!NOTE]
>  Dieses Verhalten ähnelt oberflächlich betrachtet dem Tunneln für ein Routingereignis. Allerdings werden hier keine Informationen von Ereignis zu Ereignis transportiert. Jedes Element hat immer die Möglichkeit, verarbeiten die <xref:System.Windows.FrameworkElement.Loaded> Ereignisses, und markieren die Ereignisdaten als behandelt wirkt sich nicht hinter diesem Element.  
  
### <a name="unloaded"></a>Nicht Geladen  
 <xref:System.Windows.FrameworkElement.Unloaded>zuletzt ausgelöst wird, und initiiert wird, indem Sie entweder die Präsentationsquelle oder visuellen übergeordneten Element entfernt wird. Wenn <xref:System.Windows.FrameworkElement.Unloaded> ausgelöst und behandelt, das Element, das das Ereignis Quelle übergeordnete Element ist (gemäß <xref:System.Windows.FrameworkElement.Parent%2A> Eigenschaft) oder ein bestimmtes Element nach oben in der Strukturen logischen oder visual wurde möglicherweise bereits nicht festgelegt, d. h., die Datenbindung, Ressourcenverweise , und die Stile können nicht auf ihre normal oder letzten bekannten Run-Time-Wert festgelegt werden.  
  
<a name="application_model_elements"></a>   
## <a name="lifetime-events-application-model-elements"></a>Anwendungsmodellelemente für Lebensdauerereignisse  
 Aufbauend auf die allgemeine Lebensdauerereignisse sind folgende Modell: <xref:System.Windows.Application>, <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, und <xref:System.Windows.Controls.Frame>. Mit ihnen können die allgemeinen Lebensdauerereignisse, um zusätzliche Ereignisse erweitert werden, die relevant für ihren speziellen Zweck sind. Sie werden im Detail in folgenden Themen erläutert:  
  
-   <xref:System.Windows.Application>: [Application Management Overview](../../../../docs/framework/wpf/app-development/application-management-overview.md).  
  
-   <xref:System.Windows.Window>: [Übersicht über WPF-Windows](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).  
  
-   <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, und <xref:System.Windows.Controls.Frame>: [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Priorität von Abhängigkeitseigenschaftswerten](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
