---
title: Übersicht über angefügte Ereignisse
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handling attached events [WPF]
- defining attached events as routed events [WPF]
- attached events [WPF], scenarios for
- attached events vs. routed events [WPF]
- backing attached events with routed events [WPF]
- attached events [WPF], definition
ms.assetid: 2c40eae3-80e4-4a45-ae09-df6c9ab4d91e
ms.openlocfilehash: c6a8b3b7355d315b83f859e7016018b56ade5484
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47112467"
---
# <a name="attached-events-overview"></a>Übersicht über angefügte Ereignisse
[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definiert eine Sprachkomponente und einen Ereignistyp mit der Bezeichnung *angefügtes Ereignis*. Mit dem Konzept eines angefügten Ereignisses können Sie einen Handler für ein bestimmtes Ereignis zu einem beliebigen Element und nicht zu einem Element, das tatsächlich das Ereignis definiert oder erbt, hinzufügen. In diesem Fall definiert oder „besitzt“ weder das Objekt, das potenziell das Ereignis auslöst, noch die Instanz der Richtungsbehandlung das Ereignis.  
  
 
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird davon ausgegangen, dass Sie die Artikel [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md) und [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) gelesen haben.  
  
<a name="Syntax"></a>   
## <a name="attached-event-syntax"></a>Syntax der angefügten Ereignisse  
 Angefügte Ereignisse haben eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Syntax und ein Codierungsmuster, die von zugrunde liegendem Code verwendet werden müssen, damit die Verwendung angefügter Ereignisse unterstützt wird.  
  
 In der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Syntax wird das angefügte Ereignis nicht einfach durch seinen Ereignisnamen, sondern durch seinen besitzenden Typ plus dem Ereignisnamen, getrennt durch einen Punkt (.) angegeben. Da der Name des Ereignisses mit dem Namen des besitzenden Typs qualifiziert wird, ermöglicht es die Syntax der angefügten Ereignisse jedem angefügten Ereignis an jedes Element angefügt zu werden, die instanziiert werden können.  
  
 Folgendes ist z.B. die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Syntax für das Anfügen eines Handlers für ein benutzerdefiniertes angefügtes Ereignis `NeedsCleaning`:  
  
 [!code-xaml[WPFAquariumSln#AE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 Beachten Sie das `aqua:`-Präfix. Das Präfix ist in diesem Fall erforderlich, da das angefügte Ereignis ein benutzerdefiniertes Ereignis ist, das aus einer benutzerdefinierten zugeordneten xmlns stammt.  
  
<a name="WPFImplements"></a>   
## <a name="how-wpf-implements-attached-events"></a>So implementiert WPF angefügte Ereignisse  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]werden angefügte Ereignisse verfügen über eine <xref:System.Windows.RoutedEvent> ein, und durch die Struktur weitergeleitet werden, nachdem sie ausgelöst werden. In der Regel ist die Quelle des angefügten Ereignisses (das Objekt, welches das Ereignis auslöst) eine System- oder Dienstquelle, und das Objekt, das den Ereignis auslösenden Code ausführt, ist daher nicht direkter Teil der Elementstruktur.  
  
<a name="Scenarios"></a>   
## <a name="scenarios-for-attached-events"></a>Szenarios für angefügte Ereignisse  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]werden angefügte Ereignisse in bestimmten Funktionsbereichen vorhanden sind denen eine Abstraktion auf Dienstebene, z. B. für die Ereignisse, die von der statischen aktiviert <xref:System.Windows.Input.Mouse> Klasse oder die <xref:System.Windows.Controls.Validation> Klasse. Klassen, die mit dem Dienst interagieren oder ihn verwenden, können entweder das Ereignis in der Syntax für angefügte Ereignisse verwenden, oder sie können das angefügte Ereignis als Routingereignis darstellen, das Teil davon ist, wie die Klasse die Funktionen des Diensts integriert.  
  
 Obwohl [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Reihe von angefügten Ereignissen definiert, sind die Szenarios sehr begrenzt, in denen Sie das angefügte Ereignis direkt verwenden oder behandeln werden. Im Allgemeinen dient das angefügte Ereignis einem Zweck der Architektur, aber dann wird es an ein nicht angefügtes Routingereignis weitergeleitet (gesichert mit einem [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Ereigniswrapper).  
  
 Z. B. die zugrunde liegende angefügte Ereignis <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> mehr problemlos verarbeitet werden können auf ein beliebiges <xref:System.Windows.UIElement> mit <xref:System.Windows.UIElement.MouseDown> , <xref:System.Windows.UIElement> statt Umgang mit Syntax für angefügte Ereignisse entweder in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code. Das angefügte Ereignis dient einem Zweck in der Architektur, da es die zukünftige Erweiterung der Eingabegeräte ermöglicht. Das hypothetische Gerät würde nur auslösen müssen <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> , um Mauseingaben zu simulieren, und müssen nicht für die Ableitung <xref:System.Windows.Input.Mouse> dazu. Dieses Szenario beinhaltet jedoch Code zur Verarbeitung von Ereignissen, und die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Behandlung des angefügten Ereignisses ist nicht für dieses Szenario relevant.  
  
<a name="Handling"></a>   
## <a name="handling-an-attached-event-in-wpf"></a>Behandeln eines angefügten Ereignisses in WPF  
 Der Prozess für die Behandlung eines angefügten Ereignisses und den von Ihnen geschriebenen Handlercode ist im Grunde derselbe wie für ein Routingereignis.  
  
 Im Allgemeinen unterscheidet sich ein angefügtes Ereignis von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nicht sehr von einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Routingereignis. Die Unterschiede bestehen in der Quelle des Ereignisses und wie es durch eine Klasse als Member verfügbar gemacht wird (was auch die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Handlersyntax beeinflusst).  
  
 Aber wie oben erwähnt sind die vorhandenen angefügten Ereignisse von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nicht speziell für die Behandlung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bestimmt. Der Zweck des Ereignisses ist häufiger das Aktivieren eines zusammengesetzten Elements, um den Status an ein übergeordnetes Element in Zusammensetzung zu melden. In diesem Fall wird das Ereignis in der Regel im Code ausgelöst und beruht auf Klassenbehandlung in der entsprechenden übergeordneten Klasse. Z. B. Elemente in einer <xref:System.Windows.Controls.Primitives.Selector> erwartet, dass Sie die angefügte <xref:System.Windows.Controls.Primitives.Selector.Selected> -Ereignis, das Klasse ist von behandelt die <xref:System.Windows.Controls.Primitives.Selector> Klasse, und klicken Sie dann möglicherweise konvertiert, indem die <xref:System.Windows.Controls.Primitives.Selector> Klasse in ein anderes Routingereignis <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> . Weitere Informationen über Routingereignisse und Klassenbehandlung finden Sie unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="Custom"></a>   
## <a name="defining-your-own-attached-events-as-routed-events"></a>Definieren Ihres eigenen angefügten Ereignisses als Routingereignisse  
 Wenn Sie von allgemeinen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Basisklassen ableiten, können Sie eigene angefügte Ereignisse implementieren, indem Sie bestimmte Mustermethoden in Ihrer Klasse einschließen und Hilfsmethoden verwenden, die bereits in den Basisklassen vorhanden sind.  
  
 Das Muster ist wie folgt:  
  
-   Eine Methode **hinzufügen*EventName*Handler** mit zwei Parametern. Der erste Parameter muss das Ereignis identifizieren, und das identifizierte Ereignis muss Namen entsprechen den ***EventName*** im Methodennamen. Der zweite Parameter ist der hinzuzufügende Handler. Die Methode muss `public` und `static`, ohne Rückgabewert.  
  
-   Eine Methode **entfernen*EventName*Handler** mit zwei Parametern. Der erste Parameter muss das Ereignis identifizieren, und das identifizierte Ereignis muss Namen entsprechen den ***EventName*** im Methodennamen. Der zweite Parameter ist der zu entfernende Handler. Die Methode muss `public` und `static`, ohne Rückgabewert.  
  
 Die **hinzufügen*EventName*Handler** Accessormethode vereinfacht die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Verarbeitung, wenn von angefügten Ereignishandlern Attribute für ein Element deklariert werden. Die **hinzufügen*EventName*Handler** und **entfernen*EventName*Handler** Methoden können auch den Codezugriff auf den Speicher des ereignishandlers für das angefügte Ereignis.  
  
 Dieses allgemeine Muster ist noch nicht präzise genug für die praktische Implementierung in einem Framework, da jede gegebene Implementierung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Readers möglicherweise verschiedene Schemas zum Identifizieren der zugrunde liegenden Ereignisse in der unterstützenden Sprache und Architektur aufweisen könnte. Dies ist einer der Gründe, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementiert, die angefügte Ereignisse als Routingereignisse; der Bezeichner für ein Ereignis (<xref:System.Windows.RoutedEvent>) wird bereits von definiert die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignissystem. Darüber hinaus ist das Weiterleiten eines Ereignisses eine natürliche Implementierungserweiterung auf dem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Konzept auf Sprachebene der angefügten Ereignisse.  
  
 Die **hinzufügen*EventName*Handler** Implementierung für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] angefügtes Ereignis besteht aus dem Aufruf der <xref:System.Windows.UIElement.AddHandler%2A> mit dem Routingereignis und dem Handler als Argumente.  
  
 Diese Implementierungsstrategie und das Routingereignissystem beschränken Sie im Allgemeinen Behandlung für angefügte Ereignisse entweder <xref:System.Windows.UIElement> abgeleiteten Klassen oder <xref:System.Windows.ContentElement> abgeleitete Klassen, aus, da nur die Klassen verfügen <xref:System.Windows.UIElement.AddHandler%2A> Implementierungen.  
  
 Der folgende Code definiert z.B. das angefügte Ereignis `NeedsCleaning` in der Besitzerklasse `Aquarium`, unter Verwendung der Strategie des angefügten Ereignisses von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für das Deklarieren des angefügten Ereignisses als Routingereignis.  
  
 [!code-csharp[WPFAquariumSln#AECode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 Beachten Sie, dass die Methode verwendet wird, um das angefügte Ereignis-ID-Feld herzustellen <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>, ist tatsächlich die gleiche Methode, die verwendet wird, um ein nicht angefügtes Routingereignis zu registrieren. Angefügte Ereignisse und Routingereignisse werden alle in einem zentralisierten internen Speicher registriert. Diese Implementierung des Ereignisspeichers ermöglicht die konzeptionelle Besonderheit „Ereignisse als Schnittstelle“, die im Artikel [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md) diskutiert wird.  
  
<a name="Raising"></a>   
## <a name="raising-a-wpf-attached-event"></a>Auslösen eines angefügten Ereignisses von WPF  
 Sie müssen normalerweise keine vorhandenen, definierten angefügten Ereignisse von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aus Ihrem Code auslösen. Diese Ereignisse folgen dem allgemeinen "Dienst"-Konzeptmodell, und Dienstklassen wie <xref:System.Windows.Input.InputManager> sind verantwortlich für das Auslösen der Ereignisse.  
  
 Jedoch wenn Sie ein benutzerdefiniertes angefügtes Ereignis basierend auf definieren die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Modells angefügte Ereignisse <xref:System.Windows.RoutedEvent>, können Sie <xref:System.Windows.UIElement.RaiseEvent%2A> zum Auslösen eines angefügten Ereignisses von einem <xref:System.Windows.UIElement> oder <xref:System.Windows.ContentElement>. Das Auslösen eines Routingereignisses (angefügt oder nicht) erfordert, dass Sie ein bestimmtes Element in der Elementstruktur als Ereignisquelle deklarieren. Diese Quelle wird gemeldet, als die <xref:System.Windows.UIElement.RaiseEvent%2A> Aufrufer. Das Element zu bestimmen, welches als die Quelle in der Struktur gemeldet ist, unterliegt Ihrer Verantwortung des Dienstes.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Ausführliche Erläuterung der XAML-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)  
 [XAML- und benutzerdefinierte Klassen für WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
