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
ms.openlocfilehash: a3a2f711840ad7f6e28443dac3c18501cd4400e0
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401400"
---
# <a name="attached-events-overview"></a>Übersicht über angefügte Ereignisse
[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definiert eine Sprachkomponente und einen Ereignistyp mit der Bezeichnung *angefügtes Ereignis*. Mit dem Konzept eines angefügten Ereignisses können Sie einen Handler für ein bestimmtes Ereignis zu einem beliebigen Element und nicht zu einem Element, das tatsächlich das Ereignis definiert oder erbt, hinzufügen. In diesem Fall definiert oder „besitzt“ weder das Objekt, das potenziell das Ereignis auslöst, noch die Instanz der Richtungsbehandlung das Ereignis.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird davon ausgegangen, dass Sie die Artikel [Übersicht über Routingereignisse](routed-events-overview.md) und [Übersicht über XAML (WPF)](xaml-overview-wpf.md) gelesen haben.  
  
<a name="Syntax"></a>   
## <a name="attached-event-syntax"></a>Syntax der angefügten Ereignisse  
 Angefügte Ereignisse haben eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Syntax und ein Codierungsmuster, die von zugrunde liegendem Code verwendet werden müssen, damit die Verwendung angefügter Ereignisse unterstützt wird.  
  
 In der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Syntax wird das angefügte Ereignis nicht einfach durch seinen Ereignisnamen, sondern durch seinen besitzenden Typ plus dem Ereignisnamen, getrennt durch einen Punkt (.) angegeben. Da der Name des Ereignisses mit dem Namen des besitzenden Typs qualifiziert wird, ermöglicht es die Syntax der angefügten Ereignisse jedem angefügten Ereignis an jedes Element angefügt zu werden, die instanziiert werden können.  
  
 Folgendes ist z.B. die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Syntax für das Anfügen eines Handlers für ein benutzerdefiniertes angefügtes Ereignis `NeedsCleaning`:  
  
 [!code-xaml[WPFAquariumSln#AE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 Beachten Sie das `aqua:`-Präfix. Das Präfix ist in diesem Fall erforderlich, da das angefügte Ereignis ein benutzerdefiniertes Ereignis ist, das aus einer benutzerdefinierten zugeordneten xmlns stammt.  
  
<a name="WPFImplements"></a>   
## <a name="how-wpf-implements-attached-events"></a>So implementiert WPF angefügte Ereignisse  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]werden angefügte Ereignisse von einem <xref:System.Windows.RoutedEvent> -Feld gestützt und durch die Struktur weitergeleitet, nachdem Sie ausgelöst wurden. In der Regel ist die Quelle des angefügten Ereignisses (das Objekt, welches das Ereignis auslöst) eine System- oder Dienstquelle, und das Objekt, das den Ereignis auslösenden Code ausführt, ist daher nicht direkter Teil der Elementstruktur.  
  
<a name="Scenarios"></a>   
## <a name="scenarios-for-attached-events"></a>Szenarios für angefügte Ereignisse  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]sind angefügte Ereignisse in bestimmten Funktionsbereichen vorhanden, in denen eine Abstraktion auf Dienst Ebene vorhanden ist, z. b. für die <xref:System.Windows.Input.Mouse> Ereignisse, die <xref:System.Windows.Controls.Validation> von der statischen-Klasse oder der-Klasse aktiviert werden. Klassen, die mit dem Dienst interagieren oder ihn verwenden, können entweder das Ereignis in der Syntax für angefügte Ereignisse verwenden, oder sie können das angefügte Ereignis als Routingereignis darstellen, das Teil davon ist, wie die Klasse die Funktionen des Diensts integriert.  
  
 Obwohl [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Reihe von angefügten Ereignissen definiert, sind die Szenarios sehr begrenzt, in denen Sie das angefügte Ereignis direkt verwenden oder behandeln werden. Im Allgemeinen dient das angefügte-Ereignis einem Architektur Zweck, wird aber dann an ein nicht angefügtes (mit einem CLR-Ereignis "Wrapper") geroutetes Ereignis weitergeleitet.  
  
 Beispielsweise kann <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> das zugrunde liegende angefügte Ereignis leichter für jede angegebene <xref:System.Windows.UIElement> behandelt werden, indem <xref:System.Windows.UIElement.MouseDown> Sie auf <xref:System.Windows.UIElement> diesen anwenden, anstatt mit der angefügten Ereignis [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Syntax entweder in oder Code umzugehen. Das angefügte Ereignis dient einem Zweck in der Architektur, da es die zukünftige Erweiterung der Eingabegeräte ermöglicht. Das hypothetische Gerät müsste nur eine Erhöhung <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> bewirken, um Maus Eingaben zu simulieren, und es muss nicht von <xref:System.Windows.Input.Mouse> abgeleitet werden. Dieses Szenario beinhaltet jedoch Code zur Verarbeitung von Ereignissen, und die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Behandlung des angefügten Ereignisses ist nicht für dieses Szenario relevant.  
  
<a name="Handling"></a>   
## <a name="handling-an-attached-event-in-wpf"></a>Behandeln eines angefügten Ereignisses in WPF  
 Der Prozess für die Behandlung eines angefügten Ereignisses und den von Ihnen geschriebenen Handlercode ist im Grunde derselbe wie für ein Routingereignis.  
  
 Im Allgemeinen unterscheidet sich ein angefügtes Ereignis von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nicht sehr von einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Routingereignis. Die Unterschiede bestehen in der Quelle des Ereignisses und wie es durch eine Klasse als Member verfügbar gemacht wird (was auch die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Handlersyntax beeinflusst).  
  
 Aber wie oben erwähnt sind die vorhandenen angefügten Ereignisse von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nicht speziell für die Behandlung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bestimmt. Der Zweck des Ereignisses ist häufiger das Aktivieren eines zusammengesetzten Elements, um den Status an ein übergeordnetes Element in Zusammensetzung zu melden. In diesem Fall wird das Ereignis in der Regel im Code ausgelöst und beruht auf Klassenbehandlung in der entsprechenden übergeordneten Klasse. Beispielsweise wird erwartet, dass <xref:System.Windows.Controls.Primitives.Selector> Elemente innerhalb eines das angefügte <xref:System.Windows.Controls.Primitives.Selector.Selected> -Ereignis, das dann von der <xref:System.Windows.Controls.Primitives.Selector> -Klasse behandelte Klasse und anschließend potenziell von <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> der <xref:System.Windows.Controls.Primitives.Selector> -Klasse in ein anderes Routing Ereignis konvertiert wird. . Weitere Informationen über Routingereignisse und Klassenbehandlung finden Sie unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="Custom"></a>   
## <a name="defining-your-own-attached-events-as-routed-events"></a>Definieren Ihres eigenen angefügten Ereignisses als Routingereignisse  
 Wenn Sie von allgemeinen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Basisklassen ableiten, können Sie eigene angefügte Ereignisse implementieren, indem Sie bestimmte Mustermethoden in Ihrer Klasse einschließen und Hilfsmethoden verwenden, die bereits in den Basisklassen vorhanden sind.  
  
 Das Muster ist wie folgt:  
  
- Eine Methode, die einen ***EventName*-Handler** mit zwei Parametern hinzufügt. Der erste Parameter ist die-Instanz, der der Ereignishandler hinzugefügt wird. Der zweite Parameter ist der hinzu zufügende Ereignishandler. Die Methode muss und `public` sein `static`und darf keinen Rückgabewert aufweisen.  
  
- Eine Methode zum **Entfernen des*EventName*-Handlers** mit zwei Parametern. Der erste Parameter ist die Instanz, aus der der Ereignishandler entfernt wird. Der zweite Parameter ist der Ereignishandler, der entfernt werden soll. Die Methode muss und `public` sein `static`und darf keinen Rückgabewert aufweisen.  
  
 Die Methode **Add*Event Name*Handler** Accessor vereinfacht die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Verarbeitung, wenn Attribute angefügter Ereignishandler für ein Element deklariert werden. Die Handler zum **Hinzufügen eines*EventName*** -Handlers und zum **Entfernen von*EventName*** -Handlern aktivieren auch den Code Zugriff auf den Ereignishandlerspeicher für das  
  
 Dieses allgemeine Muster ist noch nicht präzise genug für die praktische Implementierung in einem Framework, da jede gegebene Implementierung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Readers möglicherweise verschiedene Schemas zum Identifizieren der zugrunde liegenden Ereignisse in der unterstützenden Sprache und Architektur aufweisen könnte. Dies ist einer der Gründe, aus [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] denen angefügte Ereignisse als Routing Ereignisse implementiert werden. der Bezeichner, der<xref:System.Windows.RoutedEvent>für ein Ereignis () verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird, wird bereits vom Ereignis System definiert. Darüber hinaus ist das Weiterleiten eines Ereignisses eine natürliche Implementierungserweiterung auf dem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Konzept auf Sprachebene der angefügten Ereignisse.  
  
 Die Implementierung des **Add*EventName*-Handlers** für ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.AddHandler%2A> angefügtes Ereignis besteht aus dem Aufrufen von mit dem Routing Ereignis und dem Handler als Argumente.  
  
 Diese Implementierungsstrategie und das Routing Ereignis System in der Regel schränken die Verarbeitung angefügter <xref:System.Windows.UIElement> Ereignisse auf abgeleitete Klassen oder <xref:System.Windows.ContentElement> abgeleitete Klassen ein, <xref:System.Windows.UIElement.AddHandler%2A> da nur diese Klassen über Implementierungen verfügen.  
  
 Der folgende Code definiert z.B. das angefügte Ereignis `NeedsCleaning` in der Besitzerklasse `Aquarium`, unter Verwendung der Strategie des angefügten Ereignisses von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für das Deklarieren des angefügten Ereignisses als Routingereignis.  
  
 [!code-csharp[WPFAquariumSln#AECode](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 Beachten Sie, dass es sich bei der Methode, die zum Einrichten <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>des Bezeichners für angefügte Ereignis Bezeichner verwendet wird, um dieselbe Methode handelt, mit der ein nicht angefügtes Routing Ereignis registriert wird Angefügte Ereignisse und Routingereignisse werden alle in einem zentralisierten internen Speicher registriert. Diese Implementierung des Ereignisspeichers ermöglicht die konzeptionelle Besonderheit „Ereignisse als Schnittstelle“, die im Artikel [Übersicht über Routingereignisse](routed-events-overview.md) diskutiert wird.  
  
<a name="Raising"></a>   
## <a name="raising-a-wpf-attached-event"></a>Auslösen eines angefügten Ereignisses von WPF  
 Sie müssen normalerweise keine vorhandenen, definierten angefügten Ereignisse von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aus Ihrem Code auslösen. Diese Ereignisse folgen dem allgemeinen "Service"-Konzeptmodell, und Dienst Klassen wie <xref:System.Windows.Input.InputManager> sind dafür verantwortlich, die Ereignisse zu erhöhen.  
  
 Wenn Sie jedoch ein benutzerdefiniertes angefügtes Ereignis basierend auf [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dem Modell der Grundlage von angefügten angehängten <xref:System.Windows.UIElement.RaiseEvent%2A> <xref:System.Windows.RoutedEvent>Ereignissen definieren, können Sie verwenden, <xref:System.Windows.UIElement> um <xref:System.Windows.ContentElement>ein angefügtes-Ereignis aus beliebigen oder zu erhöhen. Um ein Routing Ereignis (angefügt oder nicht) zu erhöhen, müssen Sie ein bestimmtes Element in der Elementstruktur als Ereignis Quelle deklarieren. Diese Quelle wird als <xref:System.Windows.UIElement.RaiseEvent%2A> Aufrufer gemeldet. Das Element zu bestimmen, welches als die Quelle in der Struktur gemeldet ist, unterliegt Ihrer Verantwortung des Dienstes.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md)
- [XAML- und benutzerdefinierte Klassen für WPF](xaml-and-custom-classes-for-wpf.md)
