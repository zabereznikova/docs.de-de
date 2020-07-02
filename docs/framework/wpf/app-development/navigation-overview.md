---
title: Übersicht über die Navigation
description: Erfahren Sie mehr über die Unterstützung für Browser-Stil Navigation, die in eigenständigen Anwendungen und XAML-Browser Anwendungen in Windows Presentation Foundation (WPF) verwendet wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loose XAML files [WPF]
- windows [WPF]
- Start page [WPF]
- HTML files [WPF]
- structured navigation [WPF]
- fragment navigation [WPF]
- URIs (Uniform Resource Identifiers)
- custom objects [WPF]
- Uniform Resource Identifiers (URIs)
- pages [WPF]
- frames [WPF]
- navigation hosts [WPF]
- journals [WPF]
- lifetimes [WPF]
- retaining content state [WPF]
- content state [WPF]
- programmatic navigation [WPF]
- hyperlinks [WPF]
ms.assetid: 86ad2143-606a-4e34-bf7e-51a2594248b8
ms.openlocfilehash: 2aac1b3a38b6240bfba1b90983fd9cbd18b31b6f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621703"
---
# <a name="navigation-overview"></a>Übersicht über die Navigation

Windows Presentation Foundation (WPF) unterstützt die Navigation im Browser Stil, die in zwei Anwendungs Typen verwendet werden kann: eigenständige Anwendungen und XAML-Browser Anwendungen (XBAPs). Zum Verpacken von Inhalten für die Navigation stellt WPF die- <xref:System.Windows.Controls.Page> Klasse bereit. Sie können mithilfe von von einer <xref:System.Windows.Controls.Page> zu einer anderen deklarativ und mithilfe von <xref:System.Windows.Documents.Hyperlink> oder Programm gesteuert navigieren <xref:System.Windows.Navigation.NavigationService> . WPF verwendet das Journal, um Seiten zu speichern, von denen aus navigiert wurde, und um zurück zu diesen zu navigieren.

<xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink> , <xref:System.Windows.Navigation.NavigationService> und das Journal bilden den Kern der von WPF angebotenen Navigationsunterstützung. In dieser Übersicht werden diese Features ausführlich erläutert, bevor die erweiterte Navigationsunterstützung behandelt wird, die die Navigation zu losen [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Dateien, HTML-Dateien und Objekten umfasst.

> [!NOTE]
> In diesem Thema bezieht sich der Begriff "Browser" nur auf Browser, die WPF-Anwendungen hosten können, die derzeit Microsoft Internet Explorer und Firefox enthalten. Wenn bestimmte WPF-Funktionen nur von einem bestimmten Browser unterstützt werden, wird auf die Browserversion verwiesen.

## <a name="navigation-in-wpf-applications"></a>Navigation in WPF-Anwendungen

Dieses Thema enthält eine Übersicht über die wichtigsten Navigationsfunktionen in WPF. Diese Funktionen sind sowohl für eigenständige Anwendungen als auch für XBAPs verfügbar, obwohl Sie in diesem Thema im Kontext einer XBAP dargestellt werden.

> [!NOTE]
> In diesem Thema wird nicht erläutert, wie XBAPs erstellt und bereitgestellt werden. Weitere Informationen zu XBAPs finden Sie unter [Übersicht über WPF-XAML-Browser Anwendungen](wpf-xaml-browser-applications-overview.md).

In diesem Abschnitt werden die folgenden Aspekte der Navigation erklärt und veranschaulicht:

- [Implementieren einer Seite](#CreatingAXAMLPage)

- [Konfigurieren einer Startseite](#Configuring_a_Start_Page)

- [Konfigurieren von Titel, Breite und Höhe des Hostfensters](#ConfiguringAXAMLPage)

- [Linknavigation](#NavigatingBetweenXAMLPages)

- [Fragmentnavigation](#FragmentNavigation)

- [Navigationdienst](#NavigationService)

- [Programmgesteuerte Navigation mit dem Navigationsdienst](#Programmatic_Navigation_with_the_Navigation_Service)

- [Navigationslebensdauer](#Navigation_Lifetime)

- [Aufzeichnung der Navigation mithilfe des Journals](#NavigationHistory)

- [Seitenlebensdauer und das Journal](#PageLifetime)

- [Beibehalten des Inhaltszustands über den Navigationsverlauf](#RetainingContentStateWithNavigationHistory)

- [Cookies](#Cookies)

- [Strukturierte Navigation](#Structured_Navigation)

<a name="CreatingAXAMLPage"></a>

### <a name="implementing-a-page"></a>Implementieren einer Seite

In WPF können Sie zu verschiedenen Inhaltstypen navigieren, die .NET Framework-Objekte, benutzerdefinierte Objekte, Enumerationswerte, Benutzer Steuerelemente, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateien und HTML-Dateien enthalten. Sie werden jedoch feststellen, dass die gängigste und bequeme Methode zum Verpacken von Inhalten die Verwendung von ist <xref:System.Windows.Controls.Page> . Außerdem <xref:System.Windows.Controls.Page> implementiert Navigations spezifische Features, um ihre Darstellung zu verbessern und die Entwicklung zu vereinfachen.

Mithilfe <xref:System.Windows.Controls.Page> von können Sie eine Navigier Bare Seite mit Inhalt deklarativ implementieren, indem Sie ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup wie das folgende verwenden.

[!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]

Eine <xref:System.Windows.Controls.Page> , die im Markup implementiert ist, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hat `Page` als Stamm Element und erfordert die WPF-XML-Namespace Deklaration. Das `Page` -Element enthält den Inhalt, zu dem Sie navigieren und den Sie anzeigen möchten. Sie fügen Inhalt hinzu, indem Sie das `Page.Content` Eigenschafts Element festlegen, wie im folgenden Markup gezeigt.

[!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]

`Page.Content` kann nur ein untergeordnetes Element enthalten. Im vorherigen Beispiel besteht der Inhalt aus einer einzelnen Zeichenfolge, „Hello, Page!“. In der Praxis verwenden Sie in der Regel ein Layoutsteuerelement als untergeordnetes Element (siehe [Layout](../advanced/layout.md)), um Ihre Inhalte zu speichern und zu verfassen.

Die untergeordneten Elemente eines `Page` -Elements werden als Inhalt eines-Elements betrachtet <xref:System.Windows.Controls.Page> , und folglich müssen Sie die explizite- `Page.Content` Deklaration nicht verwenden. Das folgende Markup stellt die deklarative Entsprechung zum vorherigen Beispiel dar.

[!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]

In diesem Fall `Page.Content` wird automatisch mit den untergeordneten Elementen des-Elements festgelegt `Page` . Weitere Informationen finden Sie unter [WPF-Inhaltsmodell](../controls/wpf-content-model.md).

Ein Markup <xref:System.Windows.Controls.Page> ist zum Anzeigen von Inhalten nützlich. Ein kann jedoch <xref:System.Windows.Controls.Page> auch Steuerelemente anzeigen, die es Benutzern ermöglichen, mit der Seite zu interagieren, und kann auf Benutzerinteraktionen reagieren, indem Ereignisse behandelt und Anwendungslogik aufgerufen wird. Eine interaktive <xref:System.Windows.Controls.Page> wird mithilfe einer Kombination aus Markup und Code Behind implementiert, wie im folgenden Beispiel gezeigt.

[!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]

[!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
[!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]

Damit eine Markup- und eine Code-Behind-Datei zusammenarbeiten können, ist die folgende Konfiguration erforderlich:

- Im Markup muss das- `Page` Element das- `x:Class` Attribut enthalten. Wenn die Anwendung erstellt wird, bewirkt das vorhanden sein von `x:Class` in der Markup Datei, dass Microsoft Build Engine (MSBuild) eine Klasse erstellt, die `partial` von abgeleitet <xref:System.Windows.Controls.Page> wird und den Namen hat, der vom-Attribut angegeben wird `x:Class` . Dies erfordert das Hinzufügen einer XML-Namespace Deklaration für das [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). Die generierte- `partial` Klasse implementiert `InitializeComponent` , die aufgerufen wird, um die Ereignisse zu registrieren und die Eigenschaften festzulegen, die im Markup implementiert werden.

- Bei Code-Behind muss die Klasse eine `partial` Klasse mit dem gleichen Namen sein, der im Markup durch das `x:Class` -Attribut angegeben ist, und Sie muss von abgeleitet werden <xref:System.Windows.Controls.Page> . Dadurch kann die Code-Behind-Datei mit der-Klasse verknüpft werden `partial` , die beim Erstellen der Anwendung für die Markup Datei generiert wird (siehe [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md)).

- Im Code-Behind muss die <xref:System.Windows.Controls.Page> Klasse einen Konstruktor implementieren, der die- `InitializeComponent` Methode aufruft. `InitializeComponent`wird durch die generierte-Klasse der Markup Datei implementiert `partial` , um Ereignisse zu registrieren und im Markup definierte Eigenschaften festzulegen.

> [!NOTE]
> Wenn Sie <xref:System.Windows.Controls.Page> Ihrem Projekt mithilfe von Visual Studio eine neue hinzufügen, <xref:System.Windows.Controls.Page> wird der mithilfe von Markup und Code Behind implementiert und umfasst die erforderliche Konfiguration zum Erstellen der Zuordnung zwischen dem Markup und den Code-Behind-Dateien, wie hier beschrieben.

Wenn Sie über ein verfügen <xref:System.Windows.Controls.Page> , können Sie dorthin navigieren. Um den ersten anzugeben, <xref:System.Windows.Controls.Page> zu dem eine Anwendung navigiert, müssen Sie den Start konfigurieren <xref:System.Windows.Controls.Page> .

<a name="Configuring_a_Start_Page"></a>

### <a name="configuring-a-start-page"></a>Konfigurieren einer Startseite

XBAPs erfordert, dass eine bestimmte Menge an Anwendungs Infrastruktur in einem Browser gehostet wird. In WPF ist die- <xref:System.Windows.Application> Klasse Teil einer Anwendungs Definition, die die erforderliche Anwendungs Infrastruktur festlegt (siehe [Übersicht über die Anwendungs Verwaltung](application-management-overview.md)).

Eine Anwendungs Definition wird in der Regel unter Verwendung von Markup und Code Behind implementiert, wobei die Markup Datei als MSBuild-Element konfiguriert ist `ApplicationDefinition` . Im folgenden finden Sie eine Anwendungs Definition für eine XBAP.

[!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

[!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
[!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]

Eine XBAP kann die Anwendungs Definition verwenden, um einen Start anzugeben <xref:System.Windows.Controls.Page> . dabei handelt es sich um den, der <xref:System.Windows.Controls.Page> beim Starten der XBAP automatisch geladen wird. Hierzu legen Sie die- <xref:System.Windows.Application.StartupUri%2A> Eigenschaft mit dem URI (Uniform Resource Identifier) für den gewünschten fest <xref:System.Windows.Controls.Page> .

> [!NOTE]
> In den meisten Fällen <xref:System.Windows.Controls.Page> wird der entweder in kompiliert oder mit einer Anwendung bereitgestellt. In diesen Fällen ist der URI, der einen identifiziert, <xref:System.Windows.Controls.Page> ein Paket-URI, bei dem es sich um einen URI handelt, der dem *Paket* Schema entspricht. Paket-URIs werden in [Paket-URIs in WPF](pack-uris-in-wpf.md)ausführlicher erläutert. Sie können auch mit dem HTTP-Schema zum Inhalt navigieren. Das Schema wird nachfolgend erklärt.

Sie können <xref:System.Windows.Application.StartupUri%2A> deklarativ in Markup festlegen, wie im folgenden Beispiel gezeigt.

[!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

In diesem Beispiel wird das- `StartupUri` Attribut mit einem relativen Paket-URI festgelegt, der Homepage. XAML identifiziert. Wenn die XBAP gestartet wird, wird Homepage. XAML automatisch zu navigieren und angezeigt. Dies wird in der folgenden Abbildung veranschaulicht, die eine XBAP anzeigt, die von einem Webserver gestartet wurde.

![XBAP-Seite](./media/navigation-overview/xbap-launched-from-a-web-server.png "Dadurch wird eine XBAP angezeigt, die von einem Webserver gestartet wurde.")

> [!NOTE]
> Weitere Informationen zur Entwicklung und Bereitstellung von XBAPs finden Sie unter [Übersicht über WPF-XAML-Browser Anwendungen](wpf-xaml-browser-applications-overview.md) und bereitstellen [einer WPF-Anwendung](deploying-a-wpf-application-wpf.md).

<a name="ConfiguringAXAMLPage"></a>

### <a name="configuring-the-host-windows-title-width-and-height"></a>Konfigurieren von Titel, Breite und Höhe des Hostfensters

Möglicherweise haben Sie in der vorherigen Abbildung bemerkt, dass der Titel sowohl des Browsers als auch des Registerkarten Bereichs der URI für die XBAP ist. Der Titel ist zum einen lang und zum anderen weder ansprechend noch informativ. Aus diesem Grund <xref:System.Windows.Controls.Page> bietet Ihnen die Möglichkeit, den Titel durch Festlegen der-Eigenschaft zu ändern <xref:System.Windows.Controls.Page.WindowTitle%2A> . Darüber hinaus können Sie die Breite und Höhe des Browserfensters konfigurieren, indem Sie <xref:System.Windows.Controls.Page.WindowWidth%2A> <xref:System.Windows.Controls.Page.WindowHeight%2A> bzw. festlegen.

<xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A> und <xref:System.Windows.Controls.Page.WindowHeight%2A> können im Markup deklarativ festgelegt werden, wie im folgenden Beispiel gezeigt.

[!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]

Das Ergebnis ist in der folgenden Abbildung dargestellt.

![Fenstertitel, -höhe, -breite](./media/navigation-overview/window-title-width-height.png "Dies zeigt den Titel, die Höhe und die Breite des Fensters, die Sie konfigurieren können.")

<a name="NavigatingBetweenXAMLPages"></a>

### <a name="hyperlink-navigation"></a>Linknavigation

Eine typische XBAP besteht aus mehreren Seiten. Die einfachste Möglichkeit, von einer Seite zu einer anderen zu navigieren, ist die Verwendung von <xref:System.Windows.Documents.Hyperlink> . Sie können einem deklarativ ein-Element hinzufügen <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Controls.Page> , indem Sie das- `Hyperlink` Element verwenden, das im folgenden Markup gezeigt wird.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

Für ein- `Hyperlink` Element ist Folgendes erforderlich:

- Der Paket-URI der, <xref:System.Windows.Controls.Page> zu der navigiert werden soll, wie durch das- `NavigateUri` Attribut angegeben.

- Inhalt, auf den ein Benutzer klicken kann, um die Navigation zu initiieren, z. b. Text und Bilder (für den Inhalt, den das `Hyperlink` Element enthalten kann, finden Sie unter <xref:System.Windows.Documents.Hyperlink> ).

In der folgenden Abbildung wird eine XBAP mit einem gezeigt <xref:System.Windows.Controls.Page> , das über eine verfügt <xref:System.Windows.Documents.Hyperlink> .

![Seite mit Link](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "Dadurch wird eine XBAP mit einer Seite mit einem Hyperlink angezeigt.")

Wie Sie erwarten, bewirkt das Klicken auf das, <xref:System.Windows.Documents.Hyperlink> dass die XBAP zu der navigiert, die <xref:System.Windows.Controls.Page> durch das-Attribut identifiziert wird `NavigateUri` . Außerdem fügt XBAP der <xref:System.Windows.Controls.Page> Liste zuletzt verwendete Seiten in Internet Explorer einen Eintrag für den vorherigen hinzu. Das wird in der folgenden Abbildung gezeigt.

![Zurück-und vorwärts-Schaltflächen](./media/navigation-overview/back-and-forward-navigation.png "Navigieren Sie mit den Schaltflächen zurück und weiter.")

Und unterstützen die Navigation von einem <xref:System.Windows.Controls.Page> zum anderen, <xref:System.Windows.Documents.Hyperlink> unterstützt auch die Fragmentnavigation.

<a name="FragmentNavigation"></a>

### <a name="fragment-navigation"></a>Fragmentnavigation

Bei der *FragmentNavigation* handelt es sich um die Navigation zu einem Inhalts Fragment im aktuellen <xref:System.Windows.Controls.Page> oder einem anderen <xref:System.Windows.Controls.Page> . In WPF ist ein Inhalts Fragment der Inhalt, der in einem benannten Element enthalten ist. Ein benanntes Element ist ein Element, dessen `Name` Attribut festgelegt ist. Das folgende Markup zeigt ein benanntes `TextBlock` Element, das ein Inhalts Fragment enthält.

[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]

Damit ein <xref:System.Windows.Documents.Hyperlink> zu einem Inhalts Fragment navigiert, muss das- `NavigateUri` Attribut Folgendes enthalten:

- Der URI des <xref:System.Windows.Controls.Page> mit dem Inhalts Fragment, zu dem navigiert werden soll.

- Ein „#“-Zeichen.

- Der Name des Elements in der <xref:System.Windows.Controls.Page> , das das Inhalts Fragment enthält.

Ein Fragment-URI weist das folgende Format auf.

*SeitenURI* `#` *Elementname*

Im folgenden finden Sie ein Beispiel für einen `Hyperlink` , der für die Navigation zu einem Inhalts Fragment konfiguriert ist.

[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]

> [!NOTE]
> In diesem Abschnitt wird die Standard Implementierung der FragmentNavigation in WPF beschrieben. Mit WPF können Sie auch Ihr eigenes fragmentnavigationschema implementieren, das teilweise die Behandlung des- <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType> Ereignisses erfordert.

> [!IMPORTANT]
> Sie können zu Fragmenten in losen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seiten (nur-Markup- [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateien mit `Page` als Stamm Element) navigieren, wenn die Seiten über HTTP durchsucht werden können.
>
> Eine lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite kann jedoch zu ihren eigenen Fragmenten navigieren.

<a name="NavigationService"></a>

### <a name="navigation-service"></a>Navigationdienst

<xref:System.Windows.Documents.Hyperlink>Ermöglicht es einem Benutzer, die Navigation zu einem bestimmten zu initiieren <xref:System.Windows.Controls.Page> , das Auffinden und Herunterladen der Seite wird jedoch von der-Klasse durchgeführt <xref:System.Windows.Navigation.NavigationService> . Bietet im wesentlichen <xref:System.Windows.Navigation.NavigationService> die Möglichkeit, eine Navigations Anforderung im Namen des Client Codes zu verarbeiten, z <xref:System.Windows.Documents.Hyperlink> . b.. Außerdem <xref:System.Windows.Navigation.NavigationService> implementiert eine höhere Unterstützung für das Nachverfolgen und beeinflussen einer Navigations Anforderung.

Wenn <xref:System.Windows.Documents.Hyperlink> auf ein geklickt wird, ruft WPF <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> auf, um den <xref:System.Windows.Controls.Page> im angegebenen Paket-URI zu suchen und herunterzuladen. Der heruntergeladene <xref:System.Windows.Controls.Page> wird in eine Struktur von-Objekten konvertiert, deren Stamm Objekt eine Instanz des heruntergeladenen ist <xref:System.Windows.Controls.Page> . Ein Verweis auf das-Stamm <xref:System.Windows.Controls.Page> Objekt wird in der- <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType> Eigenschaft gespeichert. Der Paket-URI für den Inhalt, zu dem navigiert wurde, wird in der- <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> Eigenschaft gespeichert, während der den <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> Paket-URI für die letzte Seite speichert, zu der navigiert wurde.

> [!NOTE]
> Es ist möglich, dass für eine WPF-Anwendung mehr als eine derzeit aktive vorhanden ist <xref:System.Windows.Navigation.NavigationService> . Weitere Informationen finden Sie unter [Navigations Hosts](#Navigation_Hosts) weiter unten in diesem Thema.

<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>

### <a name="programmatic-navigation-with-the-navigation-service"></a>Programmgesteuerte Navigation mit dem Navigationsdienst

Sie müssen nicht wissen <xref:System.Windows.Navigation.NavigationService> , ob die Navigation deklarativ in Markup mithilfe von implementiert wird <xref:System.Windows.Documents.Hyperlink> , da <xref:System.Windows.Documents.Hyperlink> die in <xref:System.Windows.Navigation.NavigationService> Ihrem Namen verwendet. Dies bedeutet, dass, solange das direkte oder indirekte übergeordnete Element eines <xref:System.Windows.Documents.Hyperlink> Navigations Hosts (siehe [Navigations Hosts](#Navigation_Hosts)), <xref:System.Windows.Documents.Hyperlink> der Navigationsdienst des Navigations Hosts zum Verarbeiten einer Navigations Anforderung gefunden und verwendet werden kann.

Es gibt jedoch Situationen, in denen Sie direkt verwenden müssen <xref:System.Windows.Navigation.NavigationService> , einschließlich der folgenden:

- Wenn Sie einen <xref:System.Windows.Controls.Page> mit einem nicht parameterlosen Konstruktor instanziieren müssen.

- Wenn Sie Eigenschaften für festlegen müssen <xref:System.Windows.Controls.Page> , bevor Sie dorthin navigieren.

- Wenn die <xref:System.Windows.Controls.Page> , zu der navigiert werden muss, nur zur Laufzeit bestimmt werden kann.

In diesen Fällen müssen Sie Code schreiben, um die Navigation Programm gesteuert zu initiieren, indem Sie die- <xref:System.Windows.Navigation.NavigationService.Navigate%2A> Methode des- <xref:System.Windows.Navigation.NavigationService> Objekts aufrufen. Hierfür muss ein Verweis auf einen-Wert erhalten werden <xref:System.Windows.Navigation.NavigationService> .

#### <a name="getting-a-reference-to-the-navigationservice"></a>Abrufen eines Verweises auf NavigationService

Aus Gründen, die im Abschnitt [Navigations Hosts](#Navigation_Hosts) behandelt werden, kann eine WPF-Anwendung mehr als eine Anwendung aufweisen <xref:System.Windows.Navigation.NavigationService> . Dies bedeutet, dass der Code eine Methode zum Suchen eines benötigt, bei der <xref:System.Windows.Navigation.NavigationService> es sich normalerweise um die handelt, die <xref:System.Windows.Navigation.NavigationService> zum aktuellen navigiert ist <xref:System.Windows.Controls.Page> . Sie können einen Verweis auf einen <xref:System.Windows.Navigation.NavigationService> abrufen, indem Sie die-Methode aufrufen `static` <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType> . Um den <xref:System.Windows.Navigation.NavigationService> zu einem bestimmten zu navigieren <xref:System.Windows.Controls.Page> , übergeben Sie einen Verweis an den <xref:System.Windows.Controls.Page> als das-Argument der- <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A> Methode. Der folgende Code zeigt, wie Sie die <xref:System.Windows.Navigation.NavigationService> für den aktuellen-Wert von erhalten <xref:System.Windows.Controls.Page> .

[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]

Als Verknüpfung für die Suche nach <xref:System.Windows.Navigation.NavigationService> einem <xref:System.Windows.Controls.Page> implementiert, <xref:System.Windows.Controls.Page> implementiert die- <xref:System.Windows.Controls.Page.NavigationService%2A> Eigenschaft. Dies wird im folgenden Beispiel gezeigt.

[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]

> [!NOTE]
> Ein <xref:System.Windows.Controls.Page> kann nur einen Verweis auf seinen erhalten, <xref:System.Windows.Navigation.NavigationService> Wenn <xref:System.Windows.Controls.Page> das-Ereignis auslöst <xref:System.Windows.FrameworkElement.Loaded> .

#### <a name="programmatic-navigation-to-a-page-object"></a>Programmgesteuerte Navigation zu einem Seitenobjekt

Im folgenden Beispiel wird gezeigt, wie die verwendet wird <xref:System.Windows.Navigation.NavigationService> , um Programm gesteuert zu einer zu navigieren <xref:System.Windows.Controls.Page> . Die programmgesteuerte Navigation ist erforderlich, da die, <xref:System.Windows.Controls.Page> zu der navigiert wird, nur mit einem einzigen, nicht parameterlosen Konstruktor instanziiert werden kann. Das <xref:System.Windows.Controls.Page> -Element mit dem nicht Parameter losen Konstruktor wird im folgenden Markup und Code gezeigt.

[!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]

[!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
[!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]

Der <xref:System.Windows.Controls.Page> , der zum <xref:System.Windows.Controls.Page> mit dem nicht Parameter losen Konstruktor navigiert, wird im folgenden Markup und Code gezeigt.

[!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]

Wenn <xref:System.Windows.Documents.Hyperlink> auf das <xref:System.Windows.Controls.Page> geklickt wird, wird die Navigation durch Instanziieren von initiiert, um <xref:System.Windows.Controls.Page> zu zu navigieren, indem der nicht parameterlose Konstruktor verwendet und die-Methode aufgerufen wird <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> . <xref:System.Windows.Navigation.NavigationService.Navigate%2A>akzeptiert einen Verweis auf das Objekt, zu dem der <xref:System.Windows.Navigation.NavigationService> navigiert, anstelle eines Paket-URIs.

#### <a name="programmatic-navigation-with-a-pack-uri"></a>Programmgesteuerte Navigation mit einem Paket-URI

Wenn Sie einen Paket-URI Programm gesteuert erstellen müssen (wenn Sie z. b. nur den Paket-URI zur Laufzeit bestimmen können), können Sie die- <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> Methode verwenden. Dies wird im folgenden Beispiel gezeigt.

[!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]

#### <a name="refreshing-the-current-page"></a>Aktualisieren der aktuellen Seite

Eine <xref:System.Windows.Controls.Page> wird nicht heruntergeladen, wenn Sie denselben Paket-URI wie der Paket-URI aufweist, der in der-Eigenschaft gespeichert ist <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> . Wenn Sie erzwingen möchten, dass WPF die aktuelle Seite erneut herunterlädt, können Sie die- <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> Methode wie im folgenden Beispiel gezeigt aufzurufen.

[!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]

[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]

<a name="Navigation_Lifetime"></a>

### <a name="navigation-lifetime"></a>Navigationslebensdauer

Wie Sie sehen, gibt es viele Möglichkeiten zum Einleiten der Navigation. Wenn die Navigation initiiert wird und während der Navigation ausgeführt wird, können Sie die Navigation mithilfe der folgenden Ereignisse, die von implementiert werden, nachverfolgen und beeinflussen <xref:System.Windows.Navigation.NavigationService> :

- <xref:System.Windows.Navigation.NavigationService.Navigating>. Tritt ein, wenn eine neue Navigation angefordert wird. Kann zum Abbrechen der Navigation verwendet werden.

- <xref:System.Windows.Navigation.NavigationService.NavigationProgress>. Tritt regelmäßig während eines Downloadvorgangs auf, um Informationen zum Navigationsstatus bereitzustellen.

- <xref:System.Windows.Navigation.NavigationService.Navigated>. Tritt ein, nachdem die Seite gefunden und heruntergeladen wurde.

- <xref:System.Windows.Navigation.NavigationService.NavigationStopped>. Tritt auf, wenn die Navigation beendet wird (durch Aufrufen von <xref:System.Windows.Navigation.NavigationService.StopLoading%2A> ) oder wenn eine neue Navigation angefordert wird, während eine aktuelle Navigation ausgeführt wird.

- <xref:System.Windows.Navigation.NavigationService.NavigationFailed>. Tritt ein, wenn ein Fehler ausgelöst wird, während zum angeforderten Inhalt navigiert wird.

- <xref:System.Windows.Navigation.NavigationService.LoadCompleted>. Tritt ein, wenn der Inhalt, zu dem navigiert wurde, geladen und analysiert wird und mit dem Rendering begonnen wurde.

- <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>. Tritt ein, wenn die Navigation zu einem Inhaltsfragment beginnt, was in folgenden Fällen geschieht:

  - Sofort, falls sich das gewünschte Fragment im aktuellen Inhalt befindet.

  - Nachdem der Inhalt der Quelldatei geladen wurde und sich das gewünschte Fragment in einem anderen Inhalt befindet.

Die Navigationsereignisse werden in der Reihenfolge ausgelöst, die in der folgenden Abbildung dargestellt wird.

![Seitennavigations-Flussdiagramm](./media/navigation-overview/order-of-navigation-events.png "Flussdiagramm für das Seiten Navigations Ereignis")

Im Allgemeinen sind <xref:System.Windows.Controls.Page> diese Ereignisse von nicht betroffen. Es ist wahrscheinlicher, dass sich eine Anwendung mit Ihnen beschäftigt, und aus diesem Grund werden diese Ereignisse auch von der- <xref:System.Windows.Application> Klasse ausgelöst:

- <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>

- <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>

- <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>

- <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>

Jedes Mal <xref:System.Windows.Navigation.NavigationService> , wenn ein Ereignis ausgelöst wird, löst die- <xref:System.Windows.Application> Klasse das entsprechende-Ereignis aus. <xref:System.Windows.Controls.Frame>und <xref:System.Windows.Navigation.NavigationWindow> bieten die gleichen Ereignisse, um die Navigation innerhalb ihrer jeweiligen Bereiche zu erkennen.

In manchen Fällen könnte ein für <xref:System.Windows.Controls.Page> diese Ereignisse von Interesse sein. Ein <xref:System.Windows.Controls.Page> kann z. b. das-Ereignis behandeln, <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> um zu bestimmen, ob die Navigation von sich selbst abgebrochen werden soll. Dies wird im folgenden Beispiel gezeigt.

[!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]

Wenn Sie einen Handler mit einem Navigations Ereignis von einem registrieren <xref:System.Windows.Controls.Page> , müssen Sie wie im vorangehenden Beispiel auch die Registrierung des Ereignis Handlers aufheben. Wenn Sie dies nicht tun, können Nebeneffekte in Bezug auf die Art und Weise, wie die WPF-Navigation <xref:System.Windows.Controls.Page> die Navigation mithilfe des Journals speichert

<a name="NavigationHistory"></a>

### <a name="remembering-navigation-with-the-journal"></a>Aufzeichnung der Navigation mithilfe des Journals

WPF verwendet zwei Stapel, um die Seiten zu merken, von denen Sie navigiert sind: einen BackStack und einen vorwärts Stapel. Wenn Sie von der aktuellen <xref:System.Windows.Controls.Page> zu einer neuen <xref:System.Windows.Controls.Page> oder vorwärts zu einer vorhandenen navigieren <xref:System.Windows.Controls.Page> , wird die aktuelle dem <xref:System.Windows.Controls.Page> *BackStack*hinzugefügt. Wenn Sie von der aktuellen <xref:System.Windows.Controls.Page> zurück zum vorherigen navigieren <xref:System.Windows.Controls.Page> , wird die aktuelle dem <xref:System.Windows.Controls.Page> *Vorwärts Stapel*hinzugefügt. Der Rückwärts- und der Vorwärtsstapel sowie die Funktion zum Verwalten der Stapel werden zusammen als das Journal bezeichnet. Jedes Element im Hintergrund Stapel und der vorwärts Stapel ist eine Instanz der <xref:System.Windows.Navigation.JournalEntry> -Klasse und wird als *Journal Eintrag*bezeichnet.

#### <a name="navigating-the-journal-from-internet-explorer"></a>Navigieren im Journal in Internet Explorer

Konzeptionell funktioniert das Journal genauso wie die Schaltflächen " **zurück** " und " **Vorwärts** " in Internet Explorer. Diese sind in der folgenden Abbildung dargestellt.

![Zurück-und vorwärts-Schaltflächen](./media/navigation-overview/back-and-forward-navigation.png "Navigieren Sie mit den Schaltflächen zurück und weiter.")

Bei XBAPs, die von Internet Explorer gehostet werden, wird das Journal von WPF in die Navigation [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von Internet Explorer integriert. Dadurch können Benutzer mithilfe der Schaltflächen " **zurück**", " **Vorwärts**" und " **Letzte Seiten** " in Internet Explorer auf Seiten in einer XBAP navigieren.

> [!IMPORTANT]
> Wenn ein Benutzer in Internet Explorer von und zurück zu einer XBAP navigiert, werden nur die Journal Einträge für Seiten, die nicht aktiv gehalten wurden, im Journal beibehalten. Weitere Informationen zur Aufrechterhaltung von Seiten finden Sie unter [Seiten Lebensdauer und das Journal](#PageLifetime) weiter unten in diesem Thema.

Standardmäßig ist der Text für jeden <xref:System.Windows.Controls.Page> , der in der Liste **zuletzt verwendete Seiten** von Internet Explorer angezeigt wird, der URI für das <xref:System.Windows.Controls.Page> . In vielen Fällen ist das für den Benutzer nicht besonders sinnvoll. Sie können den Text jedoch mithilfe einer der folgenden Optionen ändern:

1. Der angefügte `JournalEntry.Name` Attribut Wert.

2. Der `Page.Title` Attribut Wert.

3. Der `Page.WindowTitle` -Attribut Wert und der URI für die aktuelle <xref:System.Windows.Controls.Page> .

4. Der URI für die aktuelle <xref:System.Windows.Controls.Page> . (Standardwert)

Die Reihenfolge, in der die Optionen aufgeführt sind, entspricht der Rangfolge zum Suchen von Text. Wenn z. b `JournalEntry.Name` . festgelegt ist, werden die anderen Werte ignoriert.

Im folgenden Beispiel wird das- `Page.Title` Attribut verwendet, um den Text zu ändern, der für einen Journal Eintrag angezeigt wird.

[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]

[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]

#### <a name="navigating-the-journal-using-wpf"></a>Navigieren im Journal mit WPF

Obwohl ein Benutzer im Journal mithilfe der Seiten " **zurück**", " **Vorwärts**" und " **zuletzt** verwendet" im Internet Explorer navigieren kann, können Sie auch mit den von WPF bereitgestellten deklarativen und programmatischen Mechanismen durch das Journal navigieren. Ein Grund hierfür ist die Bereitstellung benutzerdefinierter Navigations-UIs auf Ihren Seiten.

Sie können die Unterstützung für Journal Navigation deklarativ hinzufügen, indem Sie die von verfügbar gemachten Navigations Befehle verwenden <xref:System.Windows.Input.NavigationCommands> . Im folgenden Beispiel wird veranschaulicht, wie der `BrowseBack` Navigations Befehl verwendet wird.

[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]

Sie können das Journal Programm gesteuert mithilfe eines der folgenden Member der- <xref:System.Windows.Navigation.NavigationService> Klasse navigieren:

- <xref:System.Windows.Navigation.NavigationService.GoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.GoForward%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>

Das Journal kann auch Programm gesteuert bearbeitet werden, wie unter [beibehalten des Inhalts Zustands mit dem Navigationsverlauf](#RetainingContentStateWithNavigationHistory) weiter unten in diesem Thema erläutert.

<a name="PageLifetime"></a>

### <a name="page-lifetime-and-the-journal"></a>Seitenlebensdauer und das Journal

Stellen Sie sich eine XBAP mit mehreren Seiten vor, die umfangreiche Inhalte enthalten, einschließlich Grafiken, Animationen und Medien. Die Speicherbeanspruchung für Seiten wie diese könnte recht groß sein, insbesondere, wenn Video- und Audiomedien verwendet werden. Da das Journal die Seiten "speichert", zu denen navigiert wurde, könnte eine solche XBAP schnell eine große und spürbare Menge an Arbeitsspeicher beanspruchen.

Aus diesem Grund ist das Standardverhalten des Journals das Speichern von <xref:System.Windows.Controls.Page> Metadaten in jedem Journal Eintrag anstelle eines Verweises auf ein- <xref:System.Windows.Controls.Page> Objekt. Wenn ein Journal Eintrag zu navigiert wird, <xref:System.Windows.Controls.Page> werden seine Metadaten verwendet, um eine neue Instanz des angegebenen-Objekts zu erstellen <xref:System.Windows.Controls.Page> . Folglich hat jede, die <xref:System.Windows.Controls.Page> navigiert wird, die Gültigkeitsdauer, die in der folgenden Abbildung veranschaulicht wird.

![Seitenlebensdauer](./media/navigation-overview/navigated-page-lifetime.png "Dadurch wird die Lebensdauer angezeigt, wenn eine Seite navigiert wird.")

Obwohl die Verwendung des standardmäßigen journalingverhaltens die Arbeitsspeicher Nutzung einsparen kann, kann die Renderingleistung pro Seite reduziert werden. die Neuerstellung einer <xref:System.Windows.Controls.Page> kann sehr zeitaufwändig sein, insbesondere, wenn Sie über umfangreiche Inhalte verfügt. Wenn Sie eine- <xref:System.Windows.Controls.Page> Instanz im Journal beibehalten müssen, können Sie hierfür zwei Verfahren zeichnen. Zuerst können Sie Programm gesteuert <xref:System.Windows.Controls.Page> durch Aufrufen der-Methode zu einem-Objekt navigieren <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> .

Zweitens können Sie angeben, dass WPF eine Instanz eines <xref:System.Windows.Controls.Page> im Journal beibehalten soll, indem Sie die- <xref:System.Windows.Controls.Page.KeepAlive%2A> Eigenschaft auf festlegen `true` (der Standardwert ist `false` ). Wie im folgenden Beispiel gezeigt, können Sie <xref:System.Windows.Controls.Page.KeepAlive%2A> deklarativ in Markup festlegen.

[!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]

Die Lebensdauer eines- <xref:System.Windows.Controls.Page> s, der beibehalten wird, unterscheidet sich ganz leicht von einem, der nicht ist. Wenn Sie das erste Mal, wenn ein aktiv <xref:System.Windows.Controls.Page> bleibt, zu der navigiert wird, wird es wie ein instanziiert, <xref:System.Windows.Controls.Page> das nicht aktiv bleibt. Da eine Instanz von <xref:System.Windows.Controls.Page> im Journal beibehalten wird, wird Sie jedoch nie so lange instanziiert, wie Sie im Journal verbleibt. Wenn eine <xref:System.Windows.Controls.Page> Initialisierungs Logik aufweist, die jedes Mal aufgerufen werden muss, wenn der <xref:System.Windows.Controls.Page> navigiert, sollten Sie Sie aus dem Konstruktor in einen Handler für das-Ereignis verschieben <xref:System.Windows.FrameworkElement.Loaded> . Wie in der folgenden Abbildung gezeigt, <xref:System.Windows.FrameworkElement.Loaded> werden das-Ereignis und das- <xref:System.Windows.FrameworkElement.Unloaded> Ereignis immer dann ausgelöst, wenn eine <xref:System.Windows.Controls.Page> zu bzw. von der navigiert wird.

![Wenn die Loaded- und Unloaded-Ereignisse ausgelöst werden](./media/navigation-overview/loaded-and-unloaded-events.png "Geladene und entladene Ereignisse werden ausgelöst, wenn eine Seite zu und aus navigiert wird.")

Wenn ein <xref:System.Windows.Controls.Page> nicht aktiv bleibt, sollten Sie keines der folgenden Aktionen ausführen:

- Speichern eines Verweises auf die Seite oder einen Teil der Seite

- Registrieren von Ereignishandlern für Ereignisse, die nicht von ihr implementiert werden

Bei einem dieser beiden werden Verweise erstellt, die erzwingen <xref:System.Windows.Controls.Page> , dass im Speicher beibehalten wird, auch nachdem er aus dem Journal entfernt wurde.

Im Allgemeinen sollten Sie das Standardverhalten bevorzugen, wenn Sie <xref:System.Windows.Controls.Page> nicht aktiv bleiben <xref:System.Windows.Controls.Page> . Dies zieht jedoch Auswirkungen auf den Zustand nach sich, die im nächsten Abschnitt erörtert werden.

<a name="RetainingContentStateWithNavigationHistory"></a>

### <a name="retaining-content-state-with-navigation-history"></a>Beibehalten des Inhaltszustands über den Navigationsverlauf

Wenn ein <xref:System.Windows.Controls.Page> nicht aktiv bleibt und über Steuerelemente verfügt, die Daten vom Benutzer sammeln, was geschieht mit den Daten, wenn ein Benutzer von und zurück zu der navigiert <xref:System.Windows.Controls.Page> ? Aus Gründen der Benutzererfahrung sollte der Benutzer erwarten, dass die zuvor eingegebenen Daten angezeigt werden. Da bei jeder Navigation eine neue Instanz von <xref:System.Windows.Controls.Page> erstellt wird, werden die Steuerelemente, die die Daten gesammelt haben, neu erstellt, und die Daten gehen verloren.

Glücklicherweise bietet das Journal Unterstützung für die Daten übergreifende Daten <xref:System.Windows.Controls.Page> Navigation, einschließlich der Steuerungsdaten. Insbesondere fungiert der Journal Eintrag für jeden <xref:System.Windows.Controls.Page> als temporärer Container für den zugeordneten <xref:System.Windows.Controls.Page> Zustand. Die folgenden Schritte beschreiben, wie diese Unterstützung verwendet wird, wenn eine <xref:System.Windows.Controls.Page> von der navigiert wird:

1. Dem Journal wird ein Eintrag für den aktuellen <xref:System.Windows.Controls.Page> hinzugefügt.

2. Der Zustand der <xref:System.Windows.Controls.Page> wird mit dem Journal Eintrag für diese Seite gespeichert, der dem BackStack hinzugefügt wird.

3. Die neue <xref:System.Windows.Controls.Page> wird zu navigiert.

Wenn die Seite <xref:System.Windows.Controls.Page> wieder mit dem Journal navigiert wird, werden die folgenden Schritte ausgeführt:

1. Der <xref:System.Windows.Controls.Page> (der obere Journal Eintrag im BackStack) wird instanziiert.

2. Die <xref:System.Windows.Controls.Page> wird mit dem Status aktualisiert, der mit dem Journal Eintrag für den gespeichert wurde <xref:System.Windows.Controls.Page> .

3. <xref:System.Windows.Controls.Page>Wird zurück zu.

WPF verwendet diese Unterstützung automatisch, wenn die folgenden Steuerelemente in einem verwendet werden <xref:System.Windows.Controls.Page> :

- <xref:System.Windows.Controls.CheckBox>

- <xref:System.Windows.Controls.ComboBox>

- <xref:System.Windows.Controls.Expander>

- <xref:System.Windows.Controls.Frame>

- <xref:System.Windows.Controls.ListBox>

- <xref:System.Windows.Controls.ListBoxItem>

- <xref:System.Windows.Controls.MenuItem>

- <xref:System.Windows.Controls.ProgressBar>

- <xref:System.Windows.Controls.RadioButton>

- <xref:System.Windows.Controls.Slider>

- <xref:System.Windows.Controls.TabControl>

- <xref:System.Windows.Controls.TabItem>

- <xref:System.Windows.Controls.TextBox>

Wenn eine <xref:System.Windows.Controls.Page> diese Steuerelemente verwendet, werden die in Sie eingegebenen Daten über <xref:System.Windows.Controls.Page> Navigationen hinweg gespeichert, wie in der folgenden Abbildung anhand der **bevorzugten Farbe** veranschaulicht <xref:System.Windows.Controls.ListBox> .

![Seite mit Steuerelementen, die den Zustand speichern](./media/navigation-overview/data-remembered-across-page-navigations.png "Die eingegebenen Daten werden über die Seitennavigation hinweg gespeichert.")

Wenn eine <xref:System.Windows.Controls.Page> andere Steuerelemente als die in der vorangehenden Liste aufweist oder wenn State in benutzerdefinierten Objekten gespeichert wird, müssen Sie Code schreiben, damit das Journal den Zustand über die Navigation hinweg speichert <xref:System.Windows.Controls.Page> .

Wenn Sie kleine Zustands übergreifende Zustandsänderungen speichern müssen <xref:System.Windows.Controls.Page> , können Sie Abhängigkeits Eigenschaften (siehe) verwenden <xref:System.Windows.DependencyProperty> , die mit dem Metadata- <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> Flag konfiguriert sind.

Wenn der Status, den Sie <xref:System.Windows.Controls.Page> über die Navigation hinweg berücksichtigen müssen, mehrere Datenelemente umfasst, ist es möglicherweise weniger Code intensiv, den Zustand in einer einzigen Klasse zu kapseln und die <xref:System.Windows.Navigation.IProvideCustomContentState> Schnittstelle zu implementieren.

Wenn Sie durch verschiedene Zustände eines einzelnen navigieren müssen <xref:System.Windows.Controls.Page> , ohne von der selbst zu navigieren <xref:System.Windows.Controls.Page> , können Sie und verwenden <xref:System.Windows.Navigation.IProvideCustomContentState> <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType> .

<a name="Cookies"></a>

### <a name="cookies"></a>Cookies

Eine andere Möglichkeit, wie WPF-Anwendungen Daten speichern können, ist die Verwendung von Cookies, die mithilfe der <xref:System.Windows.Application.SetCookie%2A> -Methode und der-Methode erstellt, aktualisiert und gelöscht werden <xref:System.Windows.Application.GetCookie%2A> . Die Cookies, die Sie in WPF erstellen können, sind dieselben Cookies, die von anderen Webanwendungs Typen verwendet werden. Cookies sind beliebige Daten, die von einer Anwendung entweder während oder über Anwendungs Sitzungen hinweg auf einem Client Computer gespeichert werden. Cookiedaten weisen meist das folgende Format eines Name-Wert-Paares auf.

*Name* `=` *Wert*

Wenn die Daten an weitergegeben <xref:System.Windows.Application.SetCookie%2A> werden, sowie die <xref:System.Uri> des Speicher Orts, für den das Cookie festgelegt werden soll, wird ein Cookie im Arbeitsspeicher erstellt und ist nur für die Dauer der aktuellen Anwendungs Sitzung verfügbar. Diese Art von Cookie wird als *Sitzungs Cookie*bezeichnet.

Wenn Sie ein Cookie über Anwendungssitzungen speichern möchten, muss dem Cookie unter Verwendung des folgenden Formats ein Ablaufdatum hinzugefügt werden.

*NAME* `=` *WERT* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`

Ein Cookie mit einem Ablaufdatum wird im Ordner "temporäre Internet Dateien" der aktuellen Windows-Installation gespeichert, bis das Cookie abläuft. Ein solches Cookie wird als *dauerhaftes Cookie* bezeichnet, da es über Anwendungs Sitzungen hinweg beibehalten wird.

Sie rufen sowohl Sitzungs-als auch persistente Cookies durch Aufrufen der-Methode ab, indem Sie <xref:System.Windows.Application.GetCookie%2A> die der Position übergeben, an der <xref:System.Uri> das Cookie mit der-Methode festgelegt wurde <xref:System.Windows.Application.SetCookie%2A>

Im folgenden finden Sie einige Möglichkeiten, wie Cookies in WPF unterstützt werden:

- Eigenständige WPF-Anwendungen und XBAPs können Cookies erstellen und verwalten.

- Auf Cookies, die von einer XBAP erstellt werden, kann über den Browser zugegriffen werden.

- XBAPs aus derselben Domäne können Cookies erstellen und freigeben.

- XBAPs und HTML-Seiten aus derselben Domäne können Cookies erstellen und freigeben.

- Cookies werden gesendet, wenn XBAPs und lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seiten Webanforderungen stellen.

- Sowohl XBAPs als auch XBAPs, die in iframes gehostet werden, können auf Cookies zugreifen.

- Cookie-Unterstützung in WPF ist für alle unterstützten Browser identisch.

- In Internet Explorer wird die P3P-Richtlinie, die sich auf Cookies bezieht, von WPF berücksichtigt, insbesondere in Bezug auf die erst Anbieter-und Drittanbieter-XBAPs.

<a name="Structured_Navigation"></a>

### <a name="structured-navigation"></a>Strukturierte Navigation

Wenn Sie Daten von einem an einen anderen übergeben müssen <xref:System.Windows.Controls.Page> , können Sie die Daten als Argumente an einen nicht parameterlosen Konstruktor von übergeben <xref:System.Windows.Controls.Page> . Beachten Sie, dass Sie bei Verwendung dieses Verfahrens den Alive beibehalten müssen. wenn dies nicht der Fall ist, wird bei <xref:System.Windows.Controls.Page> der nächsten Navigation zu der <xref:System.Windows.Controls.Page> von WPF das <xref:System.Windows.Controls.Page> mithilfe des Parameter losen Konstruktors neu erstellt.

Alternativ können Sie <xref:System.Windows.Controls.Page> Eigenschaften implementieren, die mit den Daten, die übermittelt werden müssen, festgelegt werden. Es ist jedoch knifflig, wenn ein <xref:System.Windows.Controls.Page> Daten an die zurückgeben muss, die <xref:System.Windows.Controls.Page> zu ihm navigiert sind. Das Problem besteht darin, dass die Navigation keine Mechanismen unterstützt, mit denen sichergestellt wird, dass eine nach der Navigation <xref:System.Windows.Controls.Page> von zurück an zurückgegeben wird. Im Grunde unterstützt die Navigation keine Semantik mit Aufruf/Rückgabe. Um dieses Problem zu beheben, stellt WPF die-Klasse bereit, mit der <xref:System.Windows.Navigation.PageFunction%601> Sie sicherstellen können, dass ein auf <xref:System.Windows.Controls.Page> vorhersagbare und strukturierte Weise zurückgegeben wird. Weitere Informationen finden Sie unter [Übersicht über die strukturierte Navigation](structured-navigation-overview.md).

<a name="The_NavigationWindow_Class"></a>

## <a name="the-navigationwindow-class"></a>Die NavigationWindow-Klasse

Bis jetzt haben Sie das Spektrum der Navigationsdienste kennengelernt, die Sie zum Erstellen von Anwendungen mit navigierbarem Inhalt normalerweise verwenden werden. Diese Dienste wurden im Kontext von XBAPs erläutert, auch wenn Sie nicht auf XBAPs beschränkt sind. Moderne Betriebssysteme und Windows-Anwendungen nutzen die Browser Darstellung moderner Benutzer, um die Navigation im Browser Stil in eigenständige Anwendungen zu integrieren. Häufige Beispiele sind:

- **Word-Thesaurus**: Navigieren durch verschiedene Benennungen (Synonyme)

- **Datei-Explorer**: Navigieren in Dateien und Ordnern

- **Assistenten**: Untergliedern einer komplexen Aufgabe in mehrere Seiten, zwischen denen navigiert werden kann. Ein Beispiel ist der Assistent für Windows-Komponenten, der das Hinzufügen und Entfernen von Windows-Features behandelt.

Um die Navigation im Browser Stil in ihre eigenständigen Anwendungen zu integrieren, können Sie die- <xref:System.Windows.Navigation.NavigationWindow> Klasse verwenden. <xref:System.Windows.Navigation.NavigationWindow>wird von abgeleitet <xref:System.Windows.Window> und mit derselben Unterstützung für die Navigation erweitert, die XBAPs bereitstellt. Sie können <xref:System.Windows.Navigation.NavigationWindow> entweder als Hauptfenster der eigenständigen Anwendung oder als sekundäres Fenster (z. b. ein Dialogfeld) verwenden.

Um einen zu implementieren <xref:System.Windows.Navigation.NavigationWindow> , wie bei den meisten Klassen der obersten Ebene in WPF ( <xref:System.Windows.Window> , <xref:System.Windows.Controls.Page> usw.), verwenden Sie eine Kombination aus Markup und Code Behind. Dies wird im folgenden Beispiel gezeigt.

[!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]

[!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
[!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]

Mit diesem Code wird ein erstellt <xref:System.Windows.Navigation.NavigationWindow> , das automatisch zu einer <xref:System.Windows.Controls.Page> (Homepage. XAML) navigiert, wenn <xref:System.Windows.Navigation.NavigationWindow> geöffnet wird. Wenn das <xref:System.Windows.Navigation.NavigationWindow> das Hauptanwendungsfenster ist, können Sie es mit dem- `StartupUri` Attribut starten. Dies wird im folgenden Markup gezeigt.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]

In der folgenden Abbildung wird <xref:System.Windows.Navigation.NavigationWindow> als Hauptfenster einer eigenständigen Anwendung gezeigt.

![Ein Hauptfenster](./media/navigation-overview/navigation-window-as-main-window.png "Navigationsfenster als Hauptfenster")

In der Abbildung sehen Sie, dass die <xref:System.Windows.Navigation.NavigationWindow> über einen Titel verfügt, obwohl Sie nicht im <xref:System.Windows.Navigation.NavigationWindow> Implementierungs Code aus dem vorherigen Beispiel festgelegt wurde. Stattdessen wird der Titel mithilfe der-Eigenschaft festgelegt <xref:System.Windows.Controls.Page.WindowTitle%2A> , die im folgenden Code gezeigt wird.

[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]

Das Festlegen <xref:System.Windows.Controls.Page.WindowWidth%2A> der <xref:System.Windows.Controls.Page.WindowHeight%2A> Eigenschaften und wirkt sich auch auf die aus <xref:System.Windows.Navigation.NavigationWindow> .

Normalerweise implementieren Sie Ihre eigenen, <xref:System.Windows.Navigation.NavigationWindow> Wenn Sie entweder das Verhalten oder die Darstellung anpassen müssen. Wenn keines von beiden angepasst werden muss, können Sie eine Verknüpfung verwenden. Wenn Sie den Paket-URI eines <xref:System.Windows.Controls.Page> als <xref:System.Windows.Application.StartupUri%2A> in einer eigenständigen Anwendung angeben, <xref:System.Windows.Application> erstellt automatisch eine <xref:System.Windows.Navigation.NavigationWindow> zum Hosten von <xref:System.Windows.Controls.Page> . Im folgenden Markup wird gezeigt, wie Sie das aktivieren.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]

Wenn Sie möchten, dass ein sekundäres Anwendungsfenster, z. b. ein Dialogfeld <xref:System.Windows.Navigation.NavigationWindow> , ein ist, können Sie den Code im folgenden Beispiel verwenden, um ihn zu öffnen.

[!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
[!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]

Die folgende Abbildung zeigt das Ergebnis.

![Ein Dialogfeld](./media/navigation-overview/navigation-window-as-dialog-box.png "Navigationsfenster als Dialogfeld")

Wie Sie sehen, werden <xref:System.Windows.Navigation.NavigationWindow> die Schaltflächen " **zurück** " und " **Vorwärts** " im Internet Explorer-Stil angezeigt, mit denen Benutzer im Journal navigieren können. Wie in der folgenden Abbildung veranschaulicht, bieten diese Schaltflächen dieselbe Benutzererfahrung.

![Zurück- und Vorwärts-Schaltflächen in einem NavigationWindow](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "Zurück-und vorwärts-Schaltflächen in einem Navigationsfenster")

Wenn Ihre Seiten eine eigene Journal Navigationsunterstützung und eine Benutzeroberfläche bereitstellen, können Sie die Schaltflächen " **zurück** " und " **Vorwärts** " ausblenden, <xref:System.Windows.Navigation.NavigationWindow> indem Sie den Wert der- <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> Eigenschaft auf festlegen `false` .

Alternativ können Sie die Anpassungs Unterstützung in WPF verwenden, um den [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von <xref:System.Windows.Navigation.NavigationWindow> sich selbst zu ersetzen.

<a name="Frame_in_Standalone_Applications"></a>

## <a name="the-frame-class"></a>Die Frame-Klasse

Der Browser und <xref:System.Windows.Navigation.NavigationWindow> sind Fenster, die navigierbaren Inhalt hosten. In einigen Fällen verfügen Anwendungen über Inhalt, der nicht von einem ganzen Fenster gehostet werden muss. Stattdessen kann solcher Inhalt in anderem Inhalt gehostet werden. Sie können navigierbaren Inhalt mithilfe der-Klasse in anderen Inhalt einfügen <xref:System.Windows.Controls.Frame> . <xref:System.Windows.Controls.Frame>bietet dieselbe Unterstützung wie <xref:System.Windows.Navigation.NavigationWindow> und XBAPs.

Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.Frame> zu einem <xref:System.Windows.Controls.Page> deklarativ mithilfe des-Elements hinzugefügt wird `Frame` .

[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]

Mit diesem Markup wird das- `Source` Attribut des- `Frame` Elements mit einem Paket-URI für das festgelegt <xref:System.Windows.Controls.Page> , zu dem das <xref:System.Windows.Controls.Frame> zuerst navigieren soll. In der folgenden Abbildung wird eine XBAP mit einem gezeigt <xref:System.Windows.Controls.Page> , das über einen verfügt <xref:System.Windows.Controls.Frame> , der zwischen mehreren Seiten navigiert ist.

![Ein Frame, der zwischen mehreren Seiten navigiert](./media/navigation-overview/frame-navigation-between-multiple-pages.png "Dadurch wird eine Frame Navigation zwischen mehreren Seiten angezeigt.")

Sie müssen nicht nur <xref:System.Windows.Controls.Frame> innerhalb des Inhalts eines verwenden <xref:System.Windows.Controls.Page> . Es ist auch üblich, ein <xref:System.Windows.Controls.Frame> im Inhalt eines zu hosten <xref:System.Windows.Window> .

Standardmäßig <xref:System.Windows.Controls.Frame> verwendet nur ein eigenes Journal, wenn kein anderes Journal vorhanden ist. Wenn ein <xref:System.Windows.Controls.Frame> Teil des Inhalts ist, der in einer- <xref:System.Windows.Navigation.NavigationWindow> oder einer-XBAP gehostet wird, <xref:System.Windows.Controls.Frame> verwendet das Journal, das zum <xref:System.Windows.Navigation.NavigationWindow> oder XBAP gehört. Manchmal ist <xref:System.Windows.Controls.Frame> es jedoch erforderlich, dass eine für das eigene Journal verantwortlich ist. Ein Grund hierfür ist das Zulassen der Journal Navigation innerhalb der Seiten, die von einem gehostet werden <xref:System.Windows.Controls.Frame> . Dies wird in der folgenden Abbildung verdeutlicht.

![Frame- und Seiten-Diagramm](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "Dies zeigt die Journal Navigation in Seiten, die von einem Frame gehostet werden.")

In diesem Fall können Sie das so konfigurieren, dass <xref:System.Windows.Controls.Frame> es ein eigenes Journal verwendet, indem Sie die- <xref:System.Windows.Controls.Frame.JournalOwnership%2A> Eigenschaft von <xref:System.Windows.Controls.Frame> auf festlegen <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal> . Dies wird im folgenden Markup gezeigt.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]

In der folgenden Abbildung werden die Auswirkungen der Navigation innerhalb eines veranschaulicht <xref:System.Windows.Controls.Frame> , das sein eigenes Journal verwendet.

![Ein Frame mit einem eigenen Journal](./media/navigation-overview/frame-uses-its-own-journal.png "Dies zeigt die Auswirkung der Navigation innerhalb eines Frames, der ein eigenes Journal verwendet.")

Beachten Sie, dass die Journal Einträge von der Navigation [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in der angezeigt werden <xref:System.Windows.Controls.Frame> , und nicht von Internet Explorer.

> [!NOTE]
> Wenn ein <xref:System.Windows.Controls.Frame> Teil des Inhalts ist, der in einem gehostet wird <xref:System.Windows.Window> , <xref:System.Windows.Controls.Frame> verwendet ein eigenes Journal und zeigt folglich eine eigene Navigation an [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] .

Wenn die Benutzer <xref:System.Windows.Controls.Frame> Umgebung eine zum Bereitstellen eines eigenen Journal erfordert, ohne die Navigation anzuzeigen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , können Sie die Navigation ausblenden, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] indem Sie <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> auf festlegen <xref:System.Windows.Visibility.Hidden> . Dies wird im folgenden Markup gezeigt.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]

<a name="Navigation_Hosts"></a>

## <a name="navigation-hosts"></a>Navigationshosts

<xref:System.Windows.Controls.Frame>und <xref:System.Windows.Navigation.NavigationWindow> sind Klassen, die als Navigations Hosts bezeichnet werden. Ein *Navigations Host* ist eine Klasse, die zum Inhalt navigieren und Inhalte anzeigen kann. Um dies zu erreichen, verwendet jeder Navigations Host ein eigenes <xref:System.Windows.Navigation.NavigationService> -und-Journal. Die grundlegende Konstruktion eines Navigationshosts wird in der folgenden Abbildung gezeigt.

![Navigatordiagramme](./media/navigation-overview/navigation-host-construction.png "Grundlegende Erstellung eines Navigations Hosts")

Dadurch können <xref:System.Windows.Navigation.NavigationWindow> und <xref:System.Windows.Controls.Frame> die gleiche Navigationsunterstützung bereitstellen, die eine XBAP bereitstellt, wenn Sie im Browser gehostet wird.

Neben der Verwendung von <xref:System.Windows.Navigation.NavigationService> und einem Journal implementieren Navigations Hosts dieselben Member, die von <xref:System.Windows.Navigation.NavigationService> implementiert werden. Dies wird in der folgenden Abbildung verdeutlicht.

![Ein Journal in einem Frame und in einem NavigationWindow](./media/navigation-overview/navigation-window-and-frame.png "Navigationsfenster und-Frame")

Dies ermöglicht es Ihnen, Navigationsunterstützung direkt für sie zu programmieren. Dies kann in Erwägung gezogen werden, wenn Sie eine benutzerdefinierte Navigation für einen bereitstellen müssen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] <xref:System.Windows.Controls.Frame> , der in einem gehostet wird <xref:System.Windows.Window> . Außerdem implementieren beide Typen zusätzliche Navigations bezogene Member, einschließlich `BackStack` ( <xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType> , <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType> ) und `ForwardStack` ( <xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType> , <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType> ), mit denen Sie die Journal Einträge im BackStack bzw. vorwärts Stapel auflisten können.

Wie bereits erwähnt, können in einer Anwendung mehrere Journale vorhanden sein. Die folgende Abbildung enthält ein Beispiel für die Fälle, in denen das auftreten kann.

![Mehrere Journale in einer Anwendung](./media/navigation-overview/multiple-journals-in-one-application.png "Dies ist ein Beispiel für mehr als ein Journal in einer Anwendung.")

<a name="Navigating_to_Content_Other_than_Pages"></a>

## <a name="navigating-to-content-other-than-xaml-pages"></a>Navigieren zu anderem Inhalt als XAML-Seiten

In diesem Thema werden <xref:System.Windows.Controls.Page> die verschiedenen Navigationsfunktionen von WPF mithilfe von Paket-XBAPs veranschaulicht. Eine, die <xref:System.Windows.Controls.Page> in eine Anwendung kompiliert wird, ist jedoch nicht die einzige Art von Inhalt, zu der navigiert werden kann, und Pack XBAPs sind nicht die einzige Möglichkeit, Inhalte zu identifizieren.

Wie in diesem Abschnitt gezeigt, können Sie auch zu lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateien, HTML-Dateien und Objekten navigieren.

<a name="Navigating_to_Loose_XAML_Files"></a>

### <a name="navigating-to-loose-xaml-files"></a>Navigieren zu Loose XAML-Dateien

Eine lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei ist eine Datei mit den folgenden Merkmalen:

- Enthält nur [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (d. h. keinen Code).

- Verfügt über eine entsprechende Namespacedeklaration.

- Hat die Dateierweiterung .xaml.

Sehen Sie sich beispielsweise den folgenden Inhalt an, der als lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei Person. XAML gespeichert wird.

[!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]

Wenn Sie auf die Datei doppelklicken, wird der Browser geöffnet und navigiert zur Datei und zeigt den Inhalt an. Das wird in der folgenden Abbildung gezeigt.

![Anzeige des Inhalts in der Datei Person.XAML.](./media/navigation-overview/contents-of-person-xaml-file.png "Zeigt den Inhalt der Datei "Person. XAML" an.")

Sie können eine lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei aus folgendem anzeigen:

- Einer Website auf dem lokalen Computer, dem Intranet oder dem Internet

- Eine Universal Naming Convention Dateifreigabe (UNC).

- Dem lokalen Datenträger

Eine Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Datei kann den Favoriten des Browsers hinzugefügt werden, oder Sie ist die Startseite des Browsers.

> [!NOTE]
> Weitere Informationen zum Veröffentlichen und starten von lockeren [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seiten finden Sie unter Bereitstellen [einer WPF-Anwendung](deploying-a-wpf-application-wpf.md).

Eine Einschränkung in Bezug auf Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] besteht darin, dass Sie nur Inhalte hosten können, die sicher mit teilweiser Vertrauenswürdigkeit ausgeführt werden können. `Window`Kann z. b. nicht das Stamm Element einer Loose- [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei sein. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_Frame"></a>

### <a name="navigating-to-html-files-by-using-frame"></a>Navigieren zu HTML-Dateien mit Frame

Wie Sie vielleicht erwarten, können Sie auch zu HTML navigieren. Sie müssen lediglich einen URI angeben, der das http-Schema verwendet. Im folgenden Beispiel wird ein-Wert angezeigt, der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.Controls.Frame> zu einer HTML-Seite navigiert.

[!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]

Zum Navigieren zu HTML sind spezielle Berechtigungen erforderlich. Beispielsweise können Sie nicht von einer XBAP aus navigieren, die in der Sicherheits Sandbox für die teilweise vertrauenswürdige Zone der Internet Zone ausgeführt wird. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>

### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>Navigieren mit dem WebBrowser-Steuerelement zu HTML-Dateien

Das <xref:System.Windows.Controls.WebBrowser> -Steuerelement unterstützt die Interoperabilität von HTML-Dokumenten, Navigation und Skript/verwaltetem Code. Ausführliche Informationen zum- <xref:System.Windows.Controls.WebBrowser> Steuerelement finden Sie unter <xref:System.Windows.Controls.WebBrowser> .

Wie <xref:System.Windows.Controls.Frame> bei der Navigation zu HTML mithilfe von sind <xref:System.Windows.Controls.WebBrowser> spezielle Berechtigungen erforderlich. Beispielsweise können Sie in einer teilweise vertrauenswürdigen Anwendung nur zu HTML navigieren, das sich auf der Ursprungs Site befindet. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../wpf-partial-trust-security.md).

<a name="Navigating_to_Objects"></a>

### <a name="navigating-to-custom-objects"></a>Navigieren zu benutzerdefinierten Objekten

Wenn Sie über Daten verfügen, die als benutzerdefinierte Objekte gespeichert sind, besteht eine Möglichkeit zum Anzeigen dieser Daten darin, einen mit Inhalt zu erstellen, <xref:System.Windows.Controls.Page> der an diese Objekte gebunden ist (siehe [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)). Wenn Sie eine ganze Seite nicht nur zu dem Zweck erstellen möchten, die Objekte anzuzeigen, können Sie stattdessen direkt zu ihnen navigieren.

Sehen Sie sich die- `Person` Klasse an, die im folgenden Code implementiert ist.

[!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
[!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]

Um dorthin zu navigieren, rufen Sie die- <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> Methode auf, wie im folgenden Code veranschaulicht.

[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]

[!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
[!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]

Die folgende Abbildung zeigt das Ergebnis.

![Eine Seite, die zu einer Klasse navigiert](./media/navigation-overview/page-navigates-to-an-object.png "Dies ist ein Beispiel für eine Seite, die zu einem Objekt navigiert.")

Aus dieser Abbildung können Sie ersehen, dass nichts Nützliches angezeigt wird. Tatsächlich ist der angezeigte Wert der Rückgabewert der- `ToString` Methode für das **Person** -Objekt. Standardmäßig ist dies der einzige Wert, den WPF zum Darstellen des Objekts verwenden kann. Sie könnten die- `ToString` Methode überschreiben, um aussagekräftigere Informationen zurückzugeben, obwohl es sich immer noch um einen Zeichen folgen Wert handelt. Eine Methode, die Sie verwenden können, die Präsentations Funktionen von WPF nutzt, ist die Verwendung einer Daten Vorlage. Sie können eine Daten Vorlage implementieren, die WPF einem Objekt eines bestimmten Typs zuordnen kann. Der folgende Code zeigt eine Daten Vorlage für das- `Person` Objekt.

[!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]

Hier ist die Daten Vorlage mit der- `Person` `x:Type` Markup Erweiterung im-Attribut dem-Typ zugeordnet `DataType` . Die Daten Vorlage bindet dann `TextBlock` Elemente (siehe <xref:System.Windows.Controls.TextBlock> ) an die Eigenschaften der- `Person` Klasse. Die folgende Abbildung zeigt die aktualisierte Darstellung des- `Person` Objekts.

![Navigation zu einer Klasse mit einer Datenvorlage](./media/navigation-overview/navigating-to-a-class.png "Navigieren zu einer Klasse, die über eine Daten Vorlage verfügt.")

Ein Vorteil dieser Technik liegt in der Konsistenz, die Ihnen die Wiederverwendung der Datenvorlage zur konsistenten Anzeige Ihrer Objekte in der gesamten Anwendung erlaubt.

Weitere Informationen zu Datenvorlagen finden Sie unter [Übersicht über Daten](../data/data-templating-overview.md)Vorlagen.

<a name="Security"></a>

## <a name="security"></a>Sicherheit

Die Unterstützung der WPF-Navigation ermöglicht, dass XBAPs über das Internet navigiert werden kann, und ermöglicht Anwendungen, Inhalte von Drittanbietern zu hosten. Um sowohl Anwendungen als auch Benutzer vor schädlichem Verhalten zu schützen, bietet WPF eine Reihe von Sicherheitsfunktionen, die unter [Sicherheit](../security-wpf.md) und WPF-Sicherheit mit [teilweiser Vertrauens](../wpf-partial-trust-security.md)Würdigkeit erläutert werden.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [Übersicht über die Anwendungs Verwaltung](application-management-overview.md)
- [Paket-URI in WPF](pack-uris-in-wpf.md)
- [Übersicht über die strukturierte Navigation](structured-navigation-overview.md)
- [Übersicht über Navigationstopologien](navigation-topologies-overview.md)
- [Artikel zu Vorgehensweisen](navigation-how-to-topics.md)
- [Bereitstellen von WPF-Anwendungen](deploying-a-wpf-application-wpf.md)
