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
ms.openlocfilehash: e125c9a57090049f4319da96c7004f06606d0147
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141561"
---
# <a name="attached-events-overview"></a>Übersicht über angefügte Ereignisse

Extensible Application Markup Language (XAML) definiert eine Sprachkomponente und den Ereignistyp, der als *angefügtes Ereignis*bezeichnet wird. Mit dem Konzept eines angefügten Ereignisses können Sie einen Handler für ein bestimmtes Ereignis zu einem beliebigen Element und nicht zu einem Element, das tatsächlich das Ereignis definiert oder erbt, hinzufügen. In diesem Fall definiert oder „besitzt“ weder das Objekt, das potenziell das Ereignis auslöst, noch die Instanz der Richtungsbehandlung das Ereignis.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 In diesem Thema wird davon ausgegangen, dass Sie die Artikel [Übersicht über Routingereignisse](routed-events-overview.md) und [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) gelesen haben.  
  
<a name="Syntax"></a>
## <a name="attached-event-syntax"></a>Syntax der angefügten Ereignisse  
 Angefügte Ereignisse verfügen über eine XAML-Syntax und ein Codierungsmuster, das vom Sicherungscode verwendet werden muss, um die angehängte Ereignisverwendung zu unterstützen.  
  
 In der XAML-Syntax wird das angefügte Ereignis nicht nur durch seinen Ereignisnamen, sondern auch durch seinen besitzenden Typ plus den Ereignisnamen, getrennt durch einen Punkt (.), angegeben. Da der Name des Ereignisses mit dem Namen des besitzenden Typs qualifiziert wird, ermöglicht es die Syntax der angefügten Ereignisse jedem angefügten Ereignis an jedes Element angefügt zu werden, die instanziiert werden können.  
  
 Im Folgenden finden Sie beispielsweise die XAML-Syntax zum `NeedsCleaning` Anfügen eines Handlers für ein benutzerdefiniertes angefügtes Ereignis:  
  
 [!code-xaml[WPFAquariumSln#AE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 Beachten Sie das `aqua:`-Präfix. Das Präfix ist in diesem Fall erforderlich, da das angefügte Ereignis ein benutzerdefiniertes Ereignis ist, das aus einer benutzerdefinierten zugeordneten xmlns stammt.  
  
<a name="WPFImplements"></a>
## <a name="how-wpf-implements-attached-events"></a>So implementiert WPF angefügte Ereignisse

In WPF werden angefügte <xref:System.Windows.RoutedEvent> Ereignisse durch ein Feld unterstützt und durch die Struktur geleitet, nachdem sie erhöht wurden. In der Regel ist die Quelle des angefügten Ereignisses (das Objekt, welches das Ereignis auslöst) eine System- oder Dienstquelle, und das Objekt, das den Ereignis auslösenden Code ausführt, ist daher nicht direkter Teil der Elementstruktur.  
  
<a name="Scenarios"></a>
## <a name="scenarios-for-attached-events"></a>Szenarios für angefügte Ereignisse  
 In WPF sind angefügte Ereignisse in bestimmten Feature-Bereichen vorhanden, in denen eine Abstraktion auf Serviceebene vorhanden ist, z. B. für die Ereignisse, die von der statischen <xref:System.Windows.Input.Mouse> Klasse oder der <xref:System.Windows.Controls.Validation> Klasse aktiviert werden. Klassen, die mit dem Dienst interagieren oder ihn verwenden, können entweder das Ereignis in der Syntax für angefügte Ereignisse verwenden, oder sie können das angefügte Ereignis als Routingereignis darstellen, das Teil davon ist, wie die Klasse die Funktionen des Diensts integriert.  
  
 Obwohl WPF eine Reihe von angefügten Ereignissen definiert, sind die Szenarien, in denen Sie das angefügte Ereignis entweder verwenden oder direkt behandeln, sehr begrenzt. Im Allgemeinen dient das angefügte Ereignis einem Architekturzweck, wird dann aber an ein nicht angefügtes (unterstützt mit einem CLR-Ereignis "wrapper") routing-Ereignis weitergeleitet.  
  
 Beispielsweise kann das zugrunde <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> liegende angefügte Ereignis einfacher <xref:System.Windows.UIElement> für <xref:System.Windows.UIElement.MouseDown> jede <xref:System.Windows.UIElement> gegebene behandelt werden, indem sie darauf verwendet wird, anstatt sich mit angefügter Ereignissyntax entweder in XAML oder Code zu befassen. Das angefügte Ereignis dient einem Zweck in der Architektur, da es die zukünftige Erweiterung der Eingabegeräte ermöglicht. Das hypothetische Gerät müsste nur <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> angehoben werden, um die Mauseingabe zu <xref:System.Windows.Input.Mouse> simulieren, und müsste nicht daraus ableiten. Dieses Szenario beinhaltet jedoch die Codebehandlung der Ereignisse, und die XAML-Behandlung des angefügten Ereignisses ist für dieses Szenario nicht relevant.  
  
<a name="Handling"></a>
## <a name="handling-an-attached-event-in-wpf"></a>Behandeln eines angefügten Ereignisses in WPF  
 Der Prozess für die Behandlung eines angefügten Ereignisses und den von Ihnen geschriebenen Handlercode ist im Grunde derselbe wie für ein Routingereignis.  
  
 Im Allgemeinen unterscheidet sich ein mit WPF angefügtes Ereignis nicht sehr von einem gerouteten WPF-Ereignis. Die Unterschiede bestehen darin, wie das Ereignis bezogen wird und wie es von einer Klasse als Member verfügbar gemacht wird (was sich auch auf die XAML-Handlersyntax auswirkt).  
  
 Wie bereits erwähnt, sind die vorhandenen WPF-Ereignisse in WPF jedoch nicht speziell für die Handhabung bestimmt. Der Zweck des Ereignisses ist häufiger das Aktivieren eines zusammengesetzten Elements, um den Status an ein übergeordnetes Element in Zusammensetzung zu melden. In diesem Fall wird das Ereignis in der Regel im Code ausgelöst und beruht auf Klassenbehandlung in der entsprechenden übergeordneten Klasse. Es wird beispielsweise <xref:System.Windows.Controls.Primitives.Selector> erwartet, dass Elemente <xref:System.Windows.Controls.Primitives.Selector.Selected> innerhalb eines das angefügte <xref:System.Windows.Controls.Primitives.Selector> Ereignis aushebe, <xref:System.Windows.Controls.Primitives.Selector> das dann von der <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>Klasse behandelt und dann möglicherweise von der Klasse in ein anderes routingiertes Ereignis konvertiert wird. Weitere Informationen über Routingereignisse und Klassenbehandlung finden Sie unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="Custom"></a>
## <a name="defining-your-own-attached-events-as-routed-events"></a>Definieren Ihres eigenen angefügten Ereignisses als Routingereignisse  
 Wenn Sie von allgemeinen WPF-Basisklassen ableiten, können Sie eigene angefügte Ereignisse implementieren, indem Sie bestimmte Mustermethoden in Ihre Klasse einschließen und Dienstprogrammmethoden verwenden, die bereits in den Basisklassen vorhanden sind.  
  
 Das Muster ist wie folgt:  
  
- Eine Methode __Add*EventName*Handler__ mit zwei Parametern. Der erste Parameter ist die Instanz, der der Ereignishandler hinzugefügt wird. Der zweite Parameter ist der hinzuzufügende Ereignishandler. Die Methode `public` muss `static`und , ohne Rückgabewert sein.  
  
- Eine Methode __Remove*EventName*Handler__ mit zwei Parametern. Der erste Parameter ist die Instanz, aus der der Ereignishandler entfernt wird. Der zweite Parameter ist der zu entfernende Ereignishandler. Die Methode `public` muss `static`und , ohne Rückgabewert sein.  
  
 Die Accessormethode __*"EventName*Handler hinzufügen"__ erleichtert die XAML-Verarbeitung, wenn angefügte Ereignishandlerattribute für ein Element deklariert werden. Die Methoden __*"Add EventName*Handler"__ und __*"EventName*Handler entfernen"__ ermöglichen auch den Codezugriff auf den Ereignishandlerspeicher für das angefügte Ereignis.  
  
 Dieses allgemeine Muster ist noch nicht präzise genug für die praktische Implementierung in einem Framework, da jede bestimmte XAML-Readerimplementierung möglicherweise über unterschiedliche Schemata zum Identifizieren zugrunde liegender Ereignisse in der unterstützenden Sprache und Architektur verfügt. Dies ist einer der Gründe dafür, dass WPF angefügte Ereignisse als routingierte Ereignisse implementiert. Der für ein Ereignis<xref:System.Windows.RoutedEvent>( ) zu verwendende Bezeichner ist bereits vom WPF-Ereignissystem definiert. Außerdem ist das Routing eines Ereignisses eine natürliche Implementierungserweiterung für das XAML-Sprachkonzept eines angefügten Ereignisses.  
  
 Die __Add*EventName*Handler-Implementierung__ für ein WPF-Anfügenereignis besteht darin, die <xref:System.Windows.UIElement.AddHandler%2A> mit dem routingd-Ereignis und dem Handler als Argumente aufzurufen.  
  
 Diese Implementierungsstrategie und das routingierte Ereignissystem beschränken <xref:System.Windows.UIElement> im Allgemeinen <xref:System.Windows.ContentElement> die Verarbeitung von angefügten Ereignissen auf abgeleitete Klassen oder abgeleitete Klassen, da nur diese Klassen Implementierungen haben. <xref:System.Windows.UIElement.AddHandler%2A>  
  
 Der folgende Code definiert z. B. `NeedsCleaning` das `Aquarium`angefügte Ereignis für die Besitzerklasse mithilfe der von WPF angefügten Ereignisstrategie, um das angefügte Ereignis als routingiertes Ereignis zu deklarieren.  
  
 [!code-csharp[WPFAquariumSln#AECode](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 Beachten Sie, dass die Methode, die <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>zum Einrichten des angefügten Ereignisbezeichnerfelds verwendet wird, tatsächlich dieselbe Methode ist, die zum Registrieren eines nicht angefügten Routingereignisses verwendet wird. Angefügte Ereignisse und Routingereignisse werden alle in einem zentralisierten internen Speicher registriert. Diese Implementierung des Ereignisspeichers ermöglicht die konzeptionelle Besonderheit „Ereignisse als Schnittstelle“, die im Artikel [Übersicht über Routingereignisse](routed-events-overview.md) diskutiert wird.  
  
<a name="Raising"></a>
## <a name="raising-a-wpf-attached-event"></a>Auslösen eines angefügten Ereignisses von WPF  
 In der Regel müssen Sie keine vorhandenen WPF-definierten angefügten Ereignisse aus dem Code anheben. Diese Ereignisse folgen dem allgemeinen konzeptionellen "Dienst"-Konzept, und Dienstklassen, z. <xref:System.Windows.Input.InputManager> B. die Ereignisse werden für das Erhöhen der Ereignisse verantwortlich gemacht.  
  
 Wenn Sie jedoch ein benutzerdefiniertes angefügtes Ereignis basierend auf <xref:System.Windows.RoutedEvent>dem WPF-Modell definieren, auf dem angefügte Ereignisse basieren, können Sie ein angefügtes Ereignis von einem <xref:System.Windows.UIElement.RaiseEvent%2A> <xref:System.Windows.UIElement> oder <xref:System.Windows.ContentElement>aus aus angehängt. Das Anheben eines routingierten Ereignisses (angefügt oder nicht) erfordert, dass Sie ein bestimmtes Element in der Elementstruktur als Ereignisquelle deklarieren. diese Quelle wird <xref:System.Windows.UIElement.RaiseEvent%2A> als Aufrufer gemeldet. Das Element zu bestimmen, welches als die Quelle in der Struktur gemeldet ist, unterliegt Ihrer Verantwortung des Dienstes.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md)
- [XAML- und benutzerdefinierte Klassen für WPF](xaml-and-custom-classes-for-wpf.md)
