---
title: "Objektlebensdauer-Ereignisse | Microsoft Docs"
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
  - "Aktivierte Ereignisse"
  - "Anwendungsobjekte, Lebensdauerereignisse"
  - "Klassen, Frame"
  - "Klassen, NavigationWindow"
  - "Geschlossene Ereignisse"
  - "Schließende Ereignisse"
  - "ContentRendered-Ereignisse"
  - "Deaktivierte Ereignisse"
  - "Ereignisse, Aktivierte"
  - "Ereignisse, Geschlossen"
  - "Ereignisse, Schließende"
  - "Ereignisse, ContentRendered"
  - "Ereignisse, Deaktivierte"
  - "Ereignisse, Initialisiert"
  - "Ereignisse, Geladen"
  - "Ereignisse, Nicht Geladen"
  - "Exit-Ereignisse"
  - "Frame-Klasse"
  - "Initialized-Ereignisse"
  - "Lebensdauerereignisse von Objekten"
  - "Geladene Ereignisse"
  - "NavigationWindow-Klasse"
  - "Lebensdauerereignisse von Objekten"
  - "Startup-Ereignisse"
  - "Entladene Ereignisse"
ms.assetid: face6fc7-465b-4502-bfe5-e88d2e729a78
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Objektlebensdauer-Ereignisse
In diesem Thema werden die spezifischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ereignisse beschrieben, die die Phasen einer Objektlebensdauer darstellen \(Erstellung, Verwendung und Zerstörung\).  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird vorausgesetzt, dass Sie sich mit [Abhängigkeitseigenschaften](GTMT) aus Sicht eines Consumers vorhandener Abhängigkeitseigenschaften in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Klassen auskennen und dass Sie das Thema [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) gelesen haben.  Um den Beispielen in diesem Thema folgen zu können, sollten Sie mit der Verwendung von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] \(siehe [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)\) und dem Schreiben von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen vertraut sein.  
  
<a name="intro"></a>   
## Objektlebensdauer\-Ereignisse  
 Alle Objekte in verwaltetem Code von [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] durchlaufen ähnliche Lebensphasen: Erstellung, Verwendung und Zerstörung.  Viele Objekte weisen außerdem eine Abschlussphase auf, die Teil der Zerstörungsphase ist.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Objekte, oder genauer gesagt: die visuellen Objekte, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als Elemente identifiziert, weisen zudem eine Reihe von allgemeinen Objektlebensphasen auf.  Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Programmierungs\- und \-Anwendungsmodelle stellen diese Phasen als eine Abfolge von Ereignissen dar.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es vier Objekttypen in Bezug auf Lebensdauerereignisse: allgemeine Elemente, Fensterelemente, Navigationshosts und Anwendungsobjekte.  Fenster und Navigationshosts befinden sich auch innerhalb der größeren Gruppierung visueller Objekte \(Elemente\).  In diesem Thema werden zunächst die Lebensdauerereignisse beschrieben, die allen Elementen gemeinsam sind. Anschließend wird eine Einführung in spezifischere Elemente gegeben, die sich auf Anwendungsdefinitionen, Fenster oder Navigationshosts beziehen.  
  
<a name="common_events"></a>   
## Allgemeine Lebensdauerereignisse für Elemente  
 Jedes [WPF\-Frameworkebene](GTMT)\-Element \(Objekte, die sich von einem <xref:System.Windows.FrameworkElement> oder einem <xref:System.Windows.FrameworkContentElement> ableiten\) hat drei allgemeine Lebensdauerereignisse: <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded> und <xref:System.Windows.FrameworkElement.Unloaded>.  
  
### Initialized  
 <xref:System.Windows.FrameworkElement.Initialized> wird zuerst ausgelöst. Dies entspricht in etwa der Initialisierung des Objekts durch den Aufruf seines Konstruktors.  Da das Ereignis in Reaktion auf die Initialisierung eintritt, ist sichergestellt, dass alle Eigenschaften des Objekts festgelegt werden.  \(Eine Ausnahme sind Ausdrucksverwendungen wie z. B. dynamische Ressourcen oder Bindungen; dies sind nicht ausgewertete Ausdrücke.\) Als Folge der Anforderung, dass alle Eigenschaften festgelegt sein müssen, scheint die Sequenz von <xref:System.Windows.FrameworkElement.Initialized>, die durch im Markup definierte geschachtelte Elemente ausgelöst wird, zunächst für die untersten Elemente in der Struktur und dann für die übergeordneten Elemente in Richtung Stammelement aufzutreten.  Diese Reihenfolge wird eingehalten, da die Beziehungen zwischen übergeordneten und untergeordneten Elementen und die Kapselung Eigenschaften sind und daher das übergeordnete Element erst die Initialisierung berichten kann, wenn die untergeordneten Elemente, die die Eigenschaft ausfüllen, auch vollständig initialisiert werden.  
  
 Wenn Sie Handler in Reaktion auf das <xref:System.Windows.FrameworkElement.Initialized>\-Ereignis schreiben, müssen Sie berücksichtigen, dass es keine Garantie dafür gibt, dass alle anderen Elemente in der Elementstruktur \(entweder [logische Struktur](GTMT) oder [visuelle Struktur](GTMT)\), die sich in der Nähe des Handlers befinden, insbesondere übergeordnete Elemente, erstellt wurden.  Membervariablen sind möglicherweise NULL, oder Datenquellen sind unter Umständen noch nicht durch die zugrunde liegende Bindung gefüllt \(auch nicht auf Ausdrucksebene\).  
  
### Loaded  
 <xref:System.Windows.FrameworkElement.Loaded> wird als Nächstes ausgeführt.  Das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis wird vor dem endgültigen Rendern, aber nach der Berechnung der nötigen Werte für das Rendern durch das Layoutsystem ausgelöst.  Das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis führt dazu, dass die logische Struktur, in der sich ein Element befindet, vollständig ist und dass eine Verbindung zu einer Präsentationsquelle hergestellt wird, die das HWND und die Renderingoberfläche bereitstellt.  Standarddatenbindungen \(Bindungen zu lokalen Quellen, wie andere Eigenschaften oder direkt definierte Datenquellen\) treten vor <xref:System.Windows.FrameworkElement.Loaded> auf.  Asynchrone Datenbindungen \(externe oder dynamische Quellen\) sind möglicherweise aufgetreten; dies kann jedoch aufgrund ihrer asynchronen Natur nicht garantiert werden.  
  
 Der Mechanismus, durch den das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis ausgelöst wird, ist anders als <xref:System.Windows.FrameworkElement.Initialized>.  Das <xref:System.Windows.FrameworkElement.Initialized>\-Ereignis wird elementweise ausgelöst, ohne eine direkte Koordination durch eine vollständige Elementstruktur.  Im Gegensatz dazu wird das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis koordiniert über die gesamte Elementstruktur hinweg \(insbesondere die [logische Struktur](GTMT)\) ausgelöst.  Wenn alle Elemente in der Struktur einen geladenen Status aufweisen, wird das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis zunächst für das Stammelement ausgelöst.  Das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis wird dann nacheinander für jedes untergeordnete Element ausgelöst.  
  
> [!NOTE]
>  Dieses Verhalten ähnelt oberflächlich betrachtet dem Tunneln für ein [Routingereignis](GTMT).  Allerdings werden keine Informationen von Ereignis zu Ereignis transportiert.  Jedes Element hat immer die Möglichkeit, sein <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis zu verarbeiten, und das Markieren von Ereignisdaten als verarbeitet wirkt sich nur auf dieses Element aus.  
  
### Unloaded  
 <xref:System.Windows.FrameworkElement.Unloaded> wird als Letztes ausgelöst und entweder von der Präsentationsquelle oder dem visuellen übergeordneten Element initiiert, die bzw. das entfernt wird.  Wenn <xref:System.Windows.FrameworkElement.Unloaded> ausgelöst und verarbeitet wird, wurde die Festlegung des übergeordneten Elements der Ereignisquelle \(wie durch die <xref:System.Windows.FrameworkElement.Parent%2A>\-Eigenschaft festgelegt\) oder anderer Elemente weiter oben in den logischen oder visuellen Strukturen unter Umständen bereits aufgehoben, was bedeutet, dass die Datenbindung, die Ressourcenverweise und Stile nicht auf die normalen oder letzten bekannten Laufzeitwerte festgelegt werden können.  
  
<a name="application_model_elements"></a>   
## Anwendungsmodellelemente für Lebensdauerereignisse  
 Aufbauend auf den allgemeinen Lebensdauerereignissen sind folgende Anwendungsmodellelemente vorhanden: <xref:System.Windows.Application>, <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow> und <xref:System.Windows.Controls.Frame>.  Diese erweitern die allgemeinen Lebensdauerereignisse um zusätzliche Ereignisse, die relevant für ihren spezifischen Zweck sind.  Sie werden im Detail in folgenden Themen erläutert:  
  
-   <xref:System.Windows.Application>: [Übersicht über die Anwendungsverwaltung](../../../../docs/framework/wpf/app-development/application-management-overview.md).  
  
-   <xref:System.Windows.Window>: [Übersicht über WPF\-Fenster](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).  
  
-   <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow> und <xref:System.Windows.Controls.Frame>: [Übersicht über die Navigation](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
## Siehe auch  
 [Priorität von Abhängigkeitseigenschaftswerten](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)   
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)