---
title: "&#220;bersicht &#252;ber angef&#252;gte Ereignisse | Microsoft Docs"
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
  - "Angefügte Ereignisse [WPF], Definition"
  - "Angefügte Ereignisse [WPF], Szenarien für"
  - "Angefügte Ereignisse im Vergleich zu Routingereignissen [WPF]"
  - "Sichern von angefügten Ereignissen im Vergleich zu Routingereignissen [WPF]"
  - "Definieren angefügter Ereignisse als Routingereignisse [WPF]"
  - "Behandeln von angefügten Ereignissen [WPF]"
ms.assetid: 2c40eae3-80e4-4a45-ae09-df6c9ab4d91e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# &#220;bersicht &#252;ber angef&#252;gte Ereignisse
[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definiert eine Sprachkomponente und einen Ereignistyp mit der Bezeichnung *angefügtes Ereignis*.  Das Konzept eines angefügten Ereignisses ermöglicht es, einen Handler für ein bestimmtes Ereignis zu einem beliebigen Element hinzuzufügen, das nicht das Element sein muss, das dieses Ereignis tatsächlich definiert oder erbt.  In diesem Fall wird das Ereignis weder durch das Objekt, das das Ereignis potenziell auslöst, noch durch die behandelnde Zielinstanz definiert oder steht in keiner Weise in einem "Besitzverhältnis" dazu.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird davon ausgegangen, dass Sie [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md) und [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) gelesen haben.  
  
<a name="Syntax"></a>   
## Syntax für angefügte Ereignisse  
 Angefügte Ereignisse haben eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Syntax und ein Codierungsmuster, das der zugrunde liegende Code verwenden muss, damit angefügte Ereignisse unterstützt werden.  
  
 In der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Syntax wird das angefügte Ereignis nicht einfach durch seinen Ereignisnamen angegeben, sondern durch seinen besitzenden Typ plus dem Ereignisnamen, getrennt durch einen Punkt \(.\).  Da der Ereignisname durch den Namen des besitzenden Typs qualifiziert wird, ermöglicht die Syntax für angefügte Ereignisse das Anfügen eines angefügten Ereignisse an jedes Element, das instanziiert werden kann.  
  
 So ist beispielsweise Folgendes die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Syntax für das Anfügen eines Handlers für ein benutzerdefiniertes angefügtes `NeedsCleaning`\-Ereignis:  
  
 [!code-xml[WPFAquariumSln#AE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 Beachten Sie das Präfix `aqua:`. Das Präfix ist in diesem Fall notwendig, da das angefügte Ereignis ein benutzerdefiniertes Ereignis ist, das aus einem benutzerdefinierten zugeordneten xmlns stammt.  
  
<a name="WPFImplements"></a>   
## Implementierung von angefügten Ereignissen in WPF  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] werden angefügte Ereignisse durch ein <xref:System.Windows.RoutedEvent>\-Feld gesichert und nach Auslösen durch die Struktur weitergeleitet.  In der Regel ist die Quelle des angefügten Ereignisses \(das Objekt, das das Ereignis auslöst\) eine System\- oder Dienstquelle, und das Objekt, das den das Ereignis auslösenden Code ausführt, ist daher kein direkter Teil der Elementstruktur.  
  
<a name="Scenarios"></a>   
## Szenarien für angefügte Ereignisse  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind angefügte Ereignisse in bestimmten Featurebereichen vorhanden, in denen eine Abstraktion auf Dienstebene besteht, beispielsweise für durch die statische <xref:System.Windows.Input.Mouse>\-Klasse oder die <xref:System.Windows.Controls.Validation>\-Klasse aktivierte Ereignisse.  Klassen, die mit dem Dienst interagieren oder den Dienst verwenden, können entweder das Ereignis in der Syntax für angefügte Ereignisse verwenden oder das angefügte Ereignis als Routingereignis festlegen, das Teil der Art und Weise ist, in der die Klasse die Funktionen des Diensts integriert.  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind zwar eine Reihe angefügter Ereignisse definiert, aber die Szenarien, in denen angefügte Ereignisse direkt verwendet oder behandelt werden, sind sehr begrenzt.  Im Allgemeinen wird das angefügte Ereignis zu Architekturzwecken eingesetzt, dann aber an ein nicht angefügtes \(durch einen [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-"Wrapper" für Ereignisse gesichertes\) Routingereignis weitergeleitet.  
  
 So kann beispielsweise das zugrunde liegende angefügte Ereignis <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=fullName> einfacher auf einem gegebenen <xref:System.Windows.UIElement> behandelt werden, wenn <xref:System.Windows.UIElement.MouseDown> auf diesem <xref:System.Windows.UIElement> verwendet wird, anstatt die Syntax für angefügte Ereignisse in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder im Code zu verwenden.  Das angefügte Ereignis dient einem Architekturzweck, da es eine zukünftige Erweiterung der Eingabegeräte gestattet.  Das hypothetische Gerät muss nur <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=fullName> auslösen, um eine Mauseingabe zu simulieren und muss dazu nicht von <xref:System.Windows.Input.Mouse> abgeleitet werden.  Dieses Szenario bedingt jedoch eine Codebehandlung der Ereignisse, und die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Behandlung des angefügten Ereignisses ist für dieses Szenario nicht relevant.  
  
<a name="Handling"></a>   
## Behandeln eines angefügten Ereignisses in WPF  
 Die Vorgehensweise zur Behandlung eines angefügten Ereignisses sowie der Handlercode, den Sie schreiben, sind im Prinzip gleich wie bei Routingereignissen.  
  
 Im Allgemeinen unterscheidet sich ein angefügtes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ereignis nur geringfügig von einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Routingereignis.  Die Unterschiede liegen in der Quelle des Ereignisses und wie es durch eine Klasse als Member verfügbar gemacht wird \(dies wirkt sich auch auf die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Handlersyntax aus\).  
  
 Wie oben erwähnt sind jedoch die vorhandenen angefügten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ereignisse nicht speziell für die Behandlung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bestimmt.  Der Zweck des Ereignisses ist meist, einem zusammengesetzten Element die Meldung eines Zustands an ein übergeordnetes Element zu ermöglichen. In diesem Fall wird das Ereignis üblicherweise im Code ausgelöst und beruht auch auf der Klassenbehandlung in der relevanten übergeordneten Klasse.  So wird beispielsweise erwartet, dass Elemente innerhalb eines <xref:System.Windows.Controls.Primitives.Selector> das angefügte <xref:System.Windows.Controls.Primitives.Selector.Selected>\-Ereignis auslösen, das dann durch die <xref:System.Windows.Controls.Primitives.Selector>\-Klasse behandelt wird und anschließend durch die <xref:System.Windows.Controls.Primitives.Selector>\-Klasse potenziell in das Routingereignis <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> umgewandelt wird.  Weitere Informationen über Routingereignisse und Klassenbehandlung finden Sie unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="Custom"></a>   
## Definieren eigener angefügter Ereignisse als Routingereignisse  
 Wenn Sie aus allgemeinen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Basisklassen ableiten, können Sie eigene angefügte Ereignisse durch Einschließen bestimmter Mustermethoden in Ihre Klasse und durch Verwenden von Hilfsmethoden implementieren, die bereits in den Basisklassen vorhanden sind.  
  
 Das Muster sieht wie folgt aus:  
  
-   Ein Methode `Add*Handler` mit zwei Parametern.  Der erste Parameter muss das Ereignis identifizieren, und das identifizierte Ereignis muss Namen mit \* im Methodennamen entsprechen.  Der zweite Parameter ist der hinzuzufügende Handler.  Die Methode muss öffentlich und statisch sein und ohne Rückgabewert.  
  
-   Ein Methode `Remove*Handler` mit zwei Parametern.  Der erste Parameter muss das Ereignis identifizieren, und das identifizierte Ereignis muss Namen mit \* im Methodennamen entsprechen.  Der zweite Parameter ist der zu entfernende Handler.  Die Methode muss öffentlich und statisch sein und ohne Rückgabewert.  
  
 Die `Add*Handler`\-Accessormethode vereinfacht die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Verarbeitung, wenn angefügte Ereignishandlerattribute für ein Element deklariert sind.  Die `Add*Handler`\-Methode und die `Remove*Handler`\-Methode ermöglichen auch den Codezugriff auf den Ereignishandlerspeicher für das angefügte Ereignis.  
  
 Dieses allgemeine Muster ist noch nicht genau genug für die praktische Implementierung in einem Framework, da eine gegebene [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Readerimplementierung unterschiedliche Schemas für das Identifizieren zugrunde liegender Ereignisse in der unterstützenden Sprache und Architektur hat.  Dies ist einer der Gründe, warum [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] angefügte Ereignisse als Routingereignisse implementiert; der Bezeichner, der für ein Ereignis verwendet wird \(<xref:System.Windows.RoutedEvent>\), ist bereits durch das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ereignissystem definiert.  Das Weiterleiten eines Ereignisses ist außerdem eine natürliche Implementierungserweiterung im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Sprachebenenkonzept eines angefügten Ereignisses.  
  
 Die `Add*Handler`\-Implementierung für ein angefügtes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ereignis besteht darin, den <xref:System.Windows.UIElement.AddHandler%2A> mit dem Routingereignis und dem Handler als Argumente aufzurufen.  
  
 Diese Implementierungsstrategie und das Routingereignissystem beschränken im Allgemeinen die Behandlung angefügter Ereignisse auf vom <xref:System.Windows.UIElement> abgeleitete Klassen oder vom <xref:System.Windows.ContentElement> abgeleitete Klassen, da nur diese Klassen über <xref:System.Windows.UIElement.AddHandler%2A>\-Implementierungen verfügen.  
  
 Der folgende Code definiert beispielsweise das angefügte `NeedsCleaning`\-Ereignis für die Besitzerklasse `Aquarium` unter Verwendung der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Strategie für angefügte Ereignisse, bei der das angefügte Ereignis als Routingereignis deklariert wird.  
  
 [!code-csharp[WPFAquariumSln#AECode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 Beachten Sie, dass die Methode, die zur Festlegung des Bezeichnerfelds für das angefügte Ereignis verwendet wird \(<xref:System.Windows.EventManager.RegisterRoutedEvent%2A>\) tatsächlich die gleiche Methode ist, die zum Registrieren eines nicht angefügten Ereignisses verwendet wird.  Angefügte Ereignisse und Routingereignisse werden in einem zentralisierten internen Speicher registriert.  Durch diese Implementierung eines Ereignisspeichers wird das Konzept der "Ereignisse als Schnittstelle" aktiviert, das unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md) erläutert wird.  
  
<a name="Raising"></a>   
## Auslösen eines angefügten WPF\-Ereignisses  
 Sie müssen normalerweise keine vorhandenen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-definierten angefügten Ereignisse von Ihrem Code aus auslösen.  Diese Ereignisse folgen dem allgemeinen Konzeptmodell der "Dienste", und Dienstklassen wie <xref:System.Windows.Input.InputManager> sind verantwortlich für das Auslösen der Ereignisse.  
  
 Wenn Sie jedoch ein benutzerdefiniertes angefügtes Ereignis auf der Basis des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Modells definieren, bei dem angefügte Ereignisse auf <xref:System.Windows.RoutedEvent> basieren, können Sie <xref:System.Windows.UIElement.RaiseEvent%2A> verwenden, um ein angefügtes Ereignis durch jedes <xref:System.Windows.UIElement> oder <xref:System.Windows.ContentElement> auslösen zu lassen.  Für das Auslösen eines Routingereignisses \(ob angefügt oder nicht\) ist es erforderlich, dass Sie ein bestimmtes Element in der Elementstruktur als Ereignisquelle deklarieren. Diese Quelle wird als <xref:System.Windows.UIElement.RaiseEvent%2A>\-Aufrufer gemeldet.  Ihr Dienst ist zuständig dafür, das Element zu bestimmen, das als Quelle in der Struktur gemeldet wird.  
  
## Siehe auch  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Ausführliche Erläuterung der XAML\-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)   
 [XAML\- und benutzerdefinierte Klassen für WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)