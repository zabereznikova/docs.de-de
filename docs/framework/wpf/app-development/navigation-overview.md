---
title: Übersicht über die Navigation
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
ms.openlocfilehash: 24b872fcf58db3ef0ef7d04165129804dc46d641
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364289"
---
# <a name="navigation-overview"></a>Übersicht über die Navigation

Windows Presentation Foundation (WPF) unterstützt die Navigation im Browser Stil, die in zwei Anwendungs Typen verwendet werden kann: Eigen [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]ständige Anwendungen und. Zum Verpacken von Inhalten für die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Navigation stellt <xref:System.Windows.Controls.Page> die-Klasse bereit. Sie können mithilfe <xref:System.Windows.Controls.Page> vonvon<xref:System.Windows.Documents.Hyperlink>einer zu einer anderen deklarativ und mithilfe von oder Programm gesteuert navigieren. <xref:System.Windows.Navigation.NavigationService> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verwendet das Journal, um Seiten zu speichern, von denen weg navigiert wurde, und um wieder zu den Seiten zurück zu navigieren.

<xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], <xref:System.Windows.Navigation.NavigationService>und das Journal bilden den Kern der Navigationsunterstützung, die von angeboten wird. In dieser Übersicht werden diese Features ausführlich erläutert, bevor die erweiterte Navigationsunterstützung behandelt wird, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] die die [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] Navigation zu losen Dateien, Dateien und Objekten einschließt.

> [!NOTE]
> In diesem Thema bezieht sich der Begriff "Browser" nur auf Browser, die- [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen hosten können, [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] die derzeit und Firefox enthalten. Wenn bestimmte [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Funktionen nur von einem bestimmten Browser unterstützt werden, wird auf die Browserversion verwiesen.

## <a name="navigation-in-wpf-applications"></a>Navigation in WPF-Anwendungen

Dieses Thema enthält eine Übersicht über die wichtigsten Navigationsfunktionen in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Diese Funktionen sind sowohl für eigenständige Anwendungen als [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]auch für verfügbar, obwohl Sie in diesem Thema im Kontext [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]von dargestellt werden.

> [!NOTE]
> In diesem Thema wird nicht erläutert, wie Sie [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]erstellen und bereitstellen. Weitere Informationen zu [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]finden Sie unter [Übersicht über WPF-XAML-Browser Anwendungen](wpf-xaml-browser-applications-overview.md).

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

In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]können Sie zu verschiedenen Inhaltstypen navigieren, die .NET Framework-Objekte, benutzerdefinierte Objekte, Enumerationswerte, Benutzer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Steuerelemente, [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] Dateien und Dateien einschließen. Sie werden jedoch feststellen, dass die gängigste und bequeme Methode zum Verpacken von Inhalten die <xref:System.Windows.Controls.Page>Verwendung von ist. <xref:System.Windows.Controls.Page> Außerdem implementiert Navigations spezifische Features, um ihre Darstellung zu verbessern und die Entwicklung zu vereinfachen.

Mithilfe <xref:System.Windows.Controls.Page>von können Sie eine Navigier Bare [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite mit Inhalt deklarativ implementieren, indem Sie ein Markup wie das folgende verwenden.

[!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]

Eine <xref:System.Windows.Controls.Page> , die im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup implementiert ist `Page` , hat als Stamm Element und erfordert [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Namespace Deklaration. Das `Page` -Element enthält den Inhalt, zu dem Sie navigieren und den Sie anzeigen möchten. Sie fügen Inhalt hinzu, indem `Page.Content` Sie das Eigenschafts Element festlegen, wie im folgenden Markup gezeigt.

[!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]

`Page.Content` kann nur ein untergeordnetes Element enthalten. Im vorherigen Beispiel besteht der Inhalt aus einer einzelnen Zeichenfolge, „Hello, Page!“. In der Praxis verwenden Sie in der Regel ein Layoutsteuerelement als untergeordnetes Element (siehe [Layout](../advanced/layout.md)), um Ihre Inhalte zu speichern und zu verfassen.

Die untergeordneten Elemente eines `Page` <xref:System.Windows.Controls.Page> -Elements werden als Inhalt eines-Elements betrachtet, und folglich müssen Sie die explizite `Page.Content` -Deklaration nicht verwenden. Das folgende Markup stellt die deklarative Entsprechung zum vorherigen Beispiel dar.

[!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]

In diesem Fall `Page.Content` wird automatisch mit den untergeordneten Elementen `Page` des-Elements festgelegt. Weitere Informationen finden Sie unter [WPF-Inhaltsmodell](../controls/wpf-content-model.md).

Ein Markup <xref:System.Windows.Controls.Page> ist zum Anzeigen von Inhalten nützlich. Ein <xref:System.Windows.Controls.Page> kann jedoch auch Steuerelemente anzeigen, die es Benutzern ermöglichen, mit der Seite zu interagieren, und kann auf Benutzerinteraktionen reagieren, indem Ereignisse behandelt und Anwendungslogik aufgerufen wird. Eine interaktive <xref:System.Windows.Controls.Page> wird mithilfe einer Kombination aus Markup und Code Behind implementiert, wie im folgenden Beispiel gezeigt.

[!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]

[!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
[!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]

Damit eine Markup- und eine Code-Behind-Datei zusammenarbeiten können, ist die folgende Konfiguration erforderlich:

- Im Markup muss das `Page` -Element das `x:Class` -Attribut enthalten. Wenn die Anwendung erstellt wird `x:Class` , bewirkt [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] das vorhanden sein von in der Markup Datei, dass `partial` eine Klasse erstellt, <xref:System.Windows.Controls.Page> die von abgeleitet wird und den Namen hat, `x:Class` der vom-Attribut angegeben wird. Dies erfordert das Hinzufügen einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespace Deklaration für [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] das Schema `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` (). Die generierte `partial` -Klasse `InitializeComponent`implementiert, die aufgerufen wird, um die Ereignisse zu registrieren und die Eigenschaften festzulegen, die im Markup implementiert werden.

- Bei Code-Behind muss die Klasse eine `partial` Klasse mit dem gleichen Namen sein, der im Markup durch das `x:Class` -Attribut angegeben ist, und Sie muss von <xref:System.Windows.Controls.Page>abgeleitet werden. Dadurch kann die Code-Behind-Datei mit der `partial` -Klasse verknüpft werden, die beim Erstellen der Anwendung für die Markup Datei generiert wird (siehe [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md)).

- Im Code-Behind muss die <xref:System.Windows.Controls.Page> Klasse einen Konstruktor implementieren, der die `InitializeComponent` -Methode aufruft. `InitializeComponent`wird durch die generierte `partial` -Klasse der Markup Datei implementiert, um Ereignisse zu registrieren und im Markup definierte Eigenschaften festzulegen.

> [!NOTE]
> Wenn Sie dem Projekt mithilfe <xref:System.Windows.Controls.Page> [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]von ein neues hinzufügen, <xref:System.Windows.Controls.Page> wird der mithilfe von Markup und Code Behind implementiert und umfasst die erforderliche Konfiguration zum Erstellen der Zuordnung zwischen dem Markup und den Code-Behind-Dateien als. hier beschrieben.

Wenn Sie über ein <xref:System.Windows.Controls.Page>verfügen, können Sie dorthin navigieren. Um den ersten <xref:System.Windows.Controls.Page> anzugeben, zu dem eine Anwendung navigiert, müssen Sie den Start <xref:System.Windows.Controls.Page>konfigurieren.

<a name="Configuring_a_Start_Page"></a>

### <a name="configuring-a-start-page"></a>Konfigurieren einer Startseite

[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]s erfordern einen gewissen Umfang an Anwendungsinfrastruktur, um in einem Browser gehostet zu werden. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]ist die <xref:System.Windows.Application> -Klasse Teil einer Anwendungs Definition, die die erforderliche Anwendungs Infrastruktur festlegt (siehe [Übersicht über die Anwendungs Verwaltung](application-management-overview.md)).

Eine Anwendungs Definition wird in der Regel unter Verwendung von Markup und Code Behind implementiert, wobei die Markup Datei als [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `ApplicationDefinition` Element konfiguriert ist. Im folgenden finden Sie eine Anwendungs Definition für [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]eine.

[!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

[!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
[!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]

Ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] kann seine Anwendungs Definition verwenden, um einen Start <xref:System.Windows.Controls.Page>anzugeben. dabei handelt <xref:System.Windows.Controls.Page> es sich um den, der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] beim Starten von automatisch geladen wird. Hierzu legen Sie die <xref:System.Windows.Application.StartupUri%2A> -Eigenschaft [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] mit der für die gewünschte <xref:System.Windows.Controls.Page>fest.

> [!NOTE]
> In den meisten Fällen wird <xref:System.Windows.Controls.Page> der entweder in kompiliert oder mit einer Anwendung bereitgestellt. In diesen Fällen ist das [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , das einen <xref:System.Windows.Controls.Page> identifiziert, ein [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]Paket, das ein [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] ist, das dem *Paket* Schema entspricht. Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] werden in Paket- [URIs in WPF](pack-uris-in-wpf.md)ausführlicher erläutert. Sie können auch mit dem HTTP-Schema zum Inhalt navigieren. Das Schema wird nachfolgend erklärt.

Sie können deklarativ in Markup festlegen <xref:System.Windows.Application.StartupUri%2A> , wie im folgenden Beispiel gezeigt.

[!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

In diesem Beispiel wird das `StartupUri` -Attribut mit einem relativen Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] festgelegt, das Homepage. XAML identifiziert. Wenn das [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] gestartet wird, wird Homepage. XAML automatisch zu navigieren und angezeigt. Dies wird in der folgenden Abbildung veranschaulicht, die eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] anzeigt, die von einem Webserver gestartet wurde.

![XBAP-Seite](./media/navigation-overview/xbap-launched-from-a-web-server.png "Dadurch wird eine XBAP angezeigt, die von einem Webserver gestartet wurde.")

> [!NOTE]
> Weitere Informationen zur Entwicklung und Bereitstellung von [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]finden Sie unter [Übersicht über WPF-XAML-Browser Anwendungen](wpf-xaml-browser-applications-overview.md) und bereitstellen [einer WPF-Anwendung](deploying-a-wpf-application-wpf.md).

<a name="ConfiguringAXAMLPage"></a>

### <a name="configuring-the-host-windows-title-width-and-height"></a>Konfigurieren von Titel, Breite und Höhe des Hostfensters

Möglicherweise haben Sie in der vorherigen Abbildung bemerkt, dass der Titel sowohl des Browsers als auch des Registerkarten Bereichs der [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]ist. Der Titel ist zum einen lang und zum anderen weder ansprechend noch informativ. Aus diesem Grund bietet <xref:System.Windows.Controls.Page> Ihnen die Möglichkeit, den Titel durch Festlegen der <xref:System.Windows.Controls.Page.WindowTitle%2A> -Eigenschaft zu ändern. Darüber hinaus können Sie die Breite und Höhe des Browserfensters konfigurieren <xref:System.Windows.Controls.Page.WindowWidth%2A> <xref:System.Windows.Controls.Page.WindowHeight%2A>, indem Sie bzw. festlegen.

<xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A> und<xref:System.Windows.Controls.Page.WindowHeight%2A> können im Markup deklarativ festgelegt werden, wie im folgenden Beispiel gezeigt.

[!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]

Das Ergebnis ist in der folgenden Abbildung dargestellt.

![Fenstertitel, Höhe, Breite](./media/navigation-overview/window-title-width-height.png "Dies zeigt den Titel, die Höhe und die Breite des Fensters, die Sie konfigurieren können.")

<a name="NavigatingBetweenXAMLPages"></a>

### <a name="hyperlink-navigation"></a>Linknavigation

Eine typische [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] umfasst mehrere Seiten. Die einfachste Möglichkeit, von einer Seite zu einer anderen zu navigieren, ist <xref:System.Windows.Documents.Hyperlink>die Verwendung von. Sie können einem deklarativ ein <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Controls.Page> -Element hinzufügen, `Hyperlink` indem Sie das-Element verwenden, das im folgenden Markup gezeigt wird.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

Für `Hyperlink` ein-Element ist Folgendes erforderlich:

- Das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] <xref:System.Windows.Controls.Page> der, zu der navigiert werden soll, wie `NavigateUri` durch das-Attribut angegeben.

- Inhalt, auf den ein Benutzer klicken kann, um die Navigation zu initiieren, z. b. Text und Bilder `Hyperlink` (für den Inhalt, <xref:System.Windows.Documents.Hyperlink>den das Element enthalten kann, finden Sie unter).

In der folgenden Abbildung ist [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] ein mit einem-Wert <xref:System.Windows.Documents.Hyperlink>dargestellt ,dereinenaufweist.<xref:System.Windows.Controls.Page>

![Seite mit Hyperlink](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "Dadurch wird eine XBAP mit einer Seite mit einem Hyperlink angezeigt.")

Das Klicken auf <xref:System.Windows.Documents.Hyperlink> den bewirkt, dass das [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] durch Klicken auf die zu <xref:System.Windows.Controls.Page> der navigiert, die `NavigateUri` durch das-Attribut identifiziert wird. Außerdem fügt der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Liste zuletzt verwendete Seiten in [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]einen <xref:System.Windows.Controls.Page> Eintrag für den vorherigen hinzu. Das wird in der folgenden Abbildung gezeigt.

![Zurück-und vorwärts-Schalt] Flächen (./media/navigation-overview/back-and-forward-navigation.png "Navigieren Sie mit den Schaltflächen zurück und weiter.")

Und unterstützen die Navigation von einem <xref:System.Windows.Controls.Page> zum anderen, <xref:System.Windows.Documents.Hyperlink> unterstützt auch die Fragmentnavigation.

<a name="FragmentNavigation"></a>

### <a name="fragment-navigation"></a>Fragmentnavigation

Bei der *FragmentNavigation* handelt es sich um die Navigation zu einem <xref:System.Windows.Controls.Page> Inhalts Fragment <xref:System.Windows.Controls.Page>im aktuellen oder einem anderen. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]ist ein Inhalts Fragment der Inhalt, der in einem benannten Element enthalten ist. Ein benanntes Element ist ein Element, `Name` dessen Attribut festgelegt ist. Das folgende Markup zeigt ein benanntes `TextBlock` Element, das ein Inhalts Fragment enthält.

[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]

Damit ein <xref:System.Windows.Documents.Hyperlink> zu einem Inhalts Fragment navigiert, muss `NavigateUri` das-Attribut Folgendes enthalten:

- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Der<xref:System.Windows.Controls.Page> der mit dem Inhalts Fragment, zu der navigiert werden soll.

- Ein „#“-Zeichen.

- Der Name des Elements in der <xref:System.Windows.Controls.Page> , das das Inhalts Fragment enthält.

Ein Fragment [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] weist das folgende Format auf.

*SeitenURI* `#` *Elementname*

Im folgenden finden Sie ein Beispiel für `Hyperlink` einen, der für die Navigation zu einem Inhalts Fragment konfiguriert ist.

[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]

> [!NOTE]
> In diesem Abschnitt wird die Standard Implementierung der FragmentNavigation in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]beschrieben. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]mit können Sie auch Ihr eigenes fragmentnavigationschema implementieren, das teilweise die Behandlung des <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType> -Ereignisses erfordert.

> [!IMPORTANT]
> Sie können [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zu Fragmenten in losen Seiten (nur [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Markup-Dateien mit `Page` als Stamm Element) navigieren, wenn die Seiten über durch [!INCLUDE[TLA2#tla_http](../../../../includes/tla2sharptla-http-md.md)]sucht werden können.
>
> Eine lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite kann jedoch zu ihren eigenen Fragmenten navigieren.

<a name="NavigationService"></a>

### <a name="navigation-service"></a>Navigationdienst

Ermöglicht es einem Benutzer, die Navigation zu einem bestimmten <xref:System.Windows.Controls.Page>zu initiieren, das Auffinden und Herunterladen der Seite wird jedoch <xref:System.Windows.Navigation.NavigationService> von der-Klasse durchgeführt. <xref:System.Windows.Documents.Hyperlink> Bietet im Wesentlichen die Möglichkeit, eine Navigations Anforderung im Namen des Client Codes zu verarbeiten, z <xref:System.Windows.Documents.Hyperlink>. b. <xref:System.Windows.Navigation.NavigationService> <xref:System.Windows.Navigation.NavigationService> Außerdem implementiert eine höhere Unterstützung für das Nachverfolgen und beeinflussen einer Navigations Anforderung.

Wenn auf <xref:System.Windows.Documents.Hyperlink> ein geklickt wird [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> wird von aufgerufen, um <xref:System.Windows.Controls.Page> den im angegebenen Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]zu suchen und herunterzuladen. Der herunter <xref:System.Windows.Controls.Page> geladene wird in eine Struktur von-Objekten konvertiert, deren Stamm Objekt eine Instanz des <xref:System.Windows.Controls.Page>heruntergeladenen ist. Ein Verweis auf das <xref:System.Windows.Controls.Page> -Stamm Objekt wird in der <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType> -Eigenschaft gespeichert. Das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für den Inhalt, zu dem navigiert wurde, wird in <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> der-Eigenschaft gespeichert <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> , während das [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Paket für die letzte Seite speichert, zu der navigiert wurde.

> [!NOTE]
> Es ist möglich, dass [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eine Anwendung mehr als eine derzeit aktive <xref:System.Windows.Navigation.NavigationService>hat. Weitere Informationen finden Sie unter [Navigations Hosts](#Navigation_Hosts) weiter unten in diesem Thema.

<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>

### <a name="programmatic-navigation-with-the-navigation-service"></a>Programmgesteuerte Navigation mit dem Navigationsdienst

Sie <xref:System.Windows.Navigation.NavigationService> müssen nicht wissen, ob die Navigation deklarativ in Markup mithilfe <xref:System.Windows.Documents.Hyperlink>von implementiert wird, <xref:System.Windows.Documents.Hyperlink> da die <xref:System.Windows.Navigation.NavigationService> in Ihrem Namen verwendet. Dies bedeutet, dass, solange das direkte oder indirekte über <xref:System.Windows.Documents.Hyperlink> geordnete Element eines Navigations Hosts (siehe [Navigations Hosts](#Navigation_Hosts)), <xref:System.Windows.Documents.Hyperlink> der Navigationsdienst des Navigations Hosts zum Verarbeiten einer Navigations Anforderung gefunden und verwendet werden kann.

Es gibt jedoch Situationen, in denen Sie direkt verwenden <xref:System.Windows.Navigation.NavigationService> müssen, einschließlich der folgenden:

- Wenn Sie einen <xref:System.Windows.Controls.Page> mit einem nicht parameterlosen Konstruktor instanziieren müssen.

- Wenn Sie Eigenschaften für <xref:System.Windows.Controls.Page> festlegen müssen, bevor Sie dorthin navigieren.

- Wenn die <xref:System.Windows.Controls.Page> , zu der navigiert werden muss, nur zur Laufzeit bestimmt werden kann.

In diesen Fällen müssen Sie Code schreiben, um die Navigation Programm gesteuert zu initiieren, indem <xref:System.Windows.Navigation.NavigationService.Navigate%2A> Sie die- <xref:System.Windows.Navigation.NavigationService> Methode des-Objekts aufrufen. Hierfür muss ein Verweis auf einen <xref:System.Windows.Navigation.NavigationService>-Wert erhalten werden.

#### <a name="getting-a-reference-to-the-navigationservice"></a>Abrufen eines Verweises auf NavigationService

Aus Gründen, die im Abschnitt [Navigations Hosts](#Navigation_Hosts) behandelt werden, kann [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eine-Anwendung mehr als eine <xref:System.Windows.Navigation.NavigationService>-Anwendung aufweisen. Dies bedeutet, dass der Code eine Methode zum Suchen eines <xref:System.Windows.Navigation.NavigationService>benötigt, bei der es <xref:System.Windows.Navigation.NavigationService> sich normalerweise um die handelt <xref:System.Windows.Controls.Page>, die zum aktuellen navigiert ist. Sie können einen Verweis auf einen <xref:System.Windows.Navigation.NavigationService> abrufen, indem Sie die `static` <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType> -Methode aufrufen. Um den <xref:System.Windows.Navigation.NavigationService> zu einem bestimmten <xref:System.Windows.Controls.Page>zu navigieren, übergeben Sie einen Verweis an den <xref:System.Windows.Controls.Page> als das-Argument der <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A> -Methode. Der folgende Code zeigt, wie Sie die <xref:System.Windows.Navigation.NavigationService> für den aktuellen <xref:System.Windows.Controls.Page>-Wert von erhalten.

[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]

<xref:System.Windows.Navigation.NavigationService> Als Verknüpfung für die Suche nach einem <xref:System.Windows.Controls.Page>implementiert, <xref:System.Windows.Controls.Page> implementiert die <xref:System.Windows.Controls.Page.NavigationService%2A> -Eigenschaft. Dies wird im folgenden Beispiel gezeigt.

[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]

> [!NOTE]
> Ein <xref:System.Windows.Controls.Page> kann nur einen Verweis auf seinen <xref:System.Windows.Navigation.NavigationService> erhalten, <xref:System.Windows.Controls.Page> wenn das <xref:System.Windows.FrameworkElement.Loaded> -Ereignis auslöst.

#### <a name="programmatic-navigation-to-a-page-object"></a>Programmgesteuerte Navigation zu einem Seitenobjekt

Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Navigation.NavigationService> verwendet wird, um Programm gesteuert <xref:System.Windows.Controls.Page>zu einer zu navigieren. Die programmgesteuerte Navigation ist erforderlich <xref:System.Windows.Controls.Page> , da die, zu der navigiert wird, nur mit einem einzigen, nicht parameterlosen Konstruktor instanziiert werden kann. Das <xref:System.Windows.Controls.Page> -Element mit dem nicht Parameter losen Konstruktor wird im folgenden Markup und Code gezeigt.

[!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]

[!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
[!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]

Der <xref:System.Windows.Controls.Page> , der <xref:System.Windows.Controls.Page> zum mit dem nicht Parameter losen Konstruktor navigiert, wird im folgenden Markup und Code gezeigt.

[!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]

<xref:System.Windows.Documents.Hyperlink> Wenn <xref:System.Windows.Controls.Page> <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> auf das geklickt wird,wirddieNavigationdurchInstanziierenvoninitiiert,umzuzunavigieren,indemdernichtparameterloseKonstruktorverwendetunddie-<xref:System.Windows.Controls.Page> Methode aufgerufen wird. <xref:System.Windows.Navigation.NavigationService.Navigate%2A>akzeptiert einen Verweis auf das Objekt, zu <xref:System.Windows.Navigation.NavigationService> dem der navigiert, anstelle eines Pakets [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].

#### <a name="programmatic-navigation-with-a-pack-uri"></a>Programmgesteuerte Navigation mit einem Paket-URI

Wenn Sie ein Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Programm gesteuert erstellen müssen (wenn Sie z. b. nur das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] zur Laufzeit bestimmen können), können Sie die <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> -Methode verwenden. Dies wird im folgenden Beispiel gezeigt.

[!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]

#### <a name="refreshing-the-current-page"></a>Aktualisieren der aktuellen Seite

Ein <xref:System.Windows.Controls.Page> -Objekt wird nicht heruntergeladen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , wenn es [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] über das Paket verfügt, das in der <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> -Eigenschaft gespeichert ist. Um zu [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] erzwingen, dass die aktuelle Seite erneut heruntergeladen wird, <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> können Sie die-Methode wie im folgenden Beispiel gezeigt aufzurufen.

[!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]

[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]

<a name="Navigation_Lifetime"></a>

### <a name="navigation-lifetime"></a>Navigationslebensdauer

Wie Sie sehen, gibt es viele Möglichkeiten zum Einleiten der Navigation. Wenn die Navigation initiiert wird und während der Navigation ausgeführt wird, können Sie die Navigation mithilfe der folgenden Ereignisse, die von <xref:System.Windows.Navigation.NavigationService>implementiert werden, nachverfolgen und beeinflussen:

- <xref:System.Windows.Navigation.NavigationService.Navigating>. Tritt ein, wenn eine neue Navigation angefordert wird. Kann zum Abbrechen der Navigation verwendet werden.

- <xref:System.Windows.Navigation.NavigationService.NavigationProgress> Tritt regelmäßig während eines Downloadvorgangs auf, um Informationen zum Navigationsstatus bereitzustellen.

- <xref:System.Windows.Navigation.NavigationService.Navigated>. Tritt ein, nachdem die Seite gefunden und heruntergeladen wurde.

- <xref:System.Windows.Navigation.NavigationService.NavigationStopped> Tritt auf, wenn die Navigation beendet wird ( <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>durch Aufrufen von) oder wenn eine neue Navigation angefordert wird, während eine aktuelle Navigation ausgeführt wird.

- <xref:System.Windows.Navigation.NavigationService.NavigationFailed> Tritt ein, wenn ein Fehler ausgelöst wird, während zum angeforderten Inhalt navigiert wird.

- <xref:System.Windows.Navigation.NavigationService.LoadCompleted> Tritt ein, wenn der Inhalt, zu dem navigiert wurde, geladen und analysiert wird und mit dem Rendering begonnen wurde.

- <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>. Tritt ein, wenn die Navigation zu einem Inhaltsfragment beginnt, was in folgenden Fällen geschieht:

  - Sofort, falls sich das gewünschte Fragment im aktuellen Inhalt befindet.

  - Nachdem der Inhalt der Quelldatei geladen wurde und sich das gewünschte Fragment in einem anderen Inhalt befindet.

Die Navigationsereignisse werden in der Reihenfolge ausgelöst, die in der folgenden Abbildung dargestellt wird.

![Flussdiagramm für die Seitennavigation](./media/navigation-overview/order-of-navigation-events.png "Flussdiagramm für das Seiten Navigations Ereignis")

Im Allgemeinen sind <xref:System.Windows.Controls.Page> diese Ereignisse von nicht betroffen. Es ist wahrscheinlicher, dass sich eine Anwendung mit Ihnen beschäftigt, und aus diesem Grund werden diese Ereignisse auch von der <xref:System.Windows.Application> -Klasse ausgelöst:

- <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>

- <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>

- <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>

- <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>

Jedes Mal <xref:System.Windows.Navigation.NavigationService> , wenn ein Ereignis ausgelöst <xref:System.Windows.Application> wird, löst die-Klasse das entsprechende-Ereignis aus. <xref:System.Windows.Controls.Frame>und <xref:System.Windows.Navigation.NavigationWindow> bieten die gleichen Ereignisse, um die Navigation innerhalb ihrer jeweiligen Bereiche zu erkennen.

In manchen Fällen könnte ein <xref:System.Windows.Controls.Page> für diese Ereignisse von Interesse sein. Ein <xref:System.Windows.Controls.Page> kann z. b. das <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> -Ereignis behandeln, um zu bestimmen, ob die Navigation von sich selbst abgebrochen werden soll. Dies wird im folgenden Beispiel gezeigt.

[!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]

Wenn Sie einen Handler mit einem Navigations Ereignis von einem <xref:System.Windows.Controls.Page>registrieren, müssen Sie wie im vorangehenden Beispiel auch die Registrierung des Ereignis Handlers aufheben. Wenn dies nicht der Fall ist, können Nebeneffekte in Bezug darauf [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] auftreten, <xref:System.Windows.Controls.Page> wie die Navigation die Navigation mithilfe des Journals speichert.

<a name="NavigationHistory"></a>

### <a name="remembering-navigation-with-the-journal"></a>Aufzeichnung der Navigation mithilfe des Journals

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verwendet zwei Stapel, um die Seiten zu speichern, von denen Sie weg navigiert sind: jeweils einen Stapel für die Rückwärts- und einen Stapel für die Vorwärtsnavigation. Wenn Sie <xref:System.Windows.Controls.Page> von der aktuellen zu einer neuen <xref:System.Windows.Controls.Page> oder vorwärts zu einer vorhandenen <xref:System.Windows.Controls.Page>navigieren, wird die <xref:System.Windows.Controls.Page> aktuelle dem *BackStack*hinzugefügt. Wenn <xref:System.Windows.Controls.Page> Sie von der aktuellen zurück zum vorherigen <xref:System.Windows.Controls.Page>navigieren, wird die aktuelle <xref:System.Windows.Controls.Page> dem *Vorwärts Stapel*hinzugefügt. Der Rückwärts- und der Vorwärtsstapel sowie die Funktion zum Verwalten der Stapel werden zusammen als das Journal bezeichnet. Jedes Element im Hintergrund Stapel und der vorwärts Stapel ist eine Instanz der <xref:System.Windows.Navigation.JournalEntry> -Klasse und wird als *Journal Eintrag*bezeichnet.

#### <a name="navigating-the-journal-from-internet-explorer"></a>Navigieren im Journal in Internet Explorer

Konzeptionell funktioniert das Journal genauso wie die Schalt [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] Flächen " **zurück** " und " **Vorwärts** ". Diese sind in der folgenden Abbildung dargestellt.

![Zurück-und vorwärts-Schalt] Flächen (./media/navigation-overview/back-and-forward-navigation.png "Navigieren Sie mit den Schaltflächen zurück und weiter.")

Bei [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] , die von [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]gehostet werden [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , wird das Journal in die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Navigation [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]von integriert. Dadurch können Benutzer mithilfe der Schaltflächen " [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] **zurück**", " **Vorwärts**" und " **Letzte Seiten** " in [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]auf Seiten in einem navigieren. Das Journal ist nicht [!INCLUDE[TLA2#tla_ie6](../../../../includes/tla2sharptla-ie6-md.md)] in die gleiche Weise wie für [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] oder Internet Explorer 8 in integriert. Stattdessen wird [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eine Ersatz Navigation [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]gerendert.

> [!IMPORTANT]
> Wenn [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]ein Benutzer in von und zurück zu einem [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]navigiert, werden nur die Journal Einträge für Seiten, die nicht aktiv gehalten wurden, im Journal beibehalten. Weitere Informationen zur Aufrechterhaltung von Seiten finden Sie unter [Seiten Lebensdauer und das Journal](#PageLifetime) weiter unten in diesem Thema.

Standardmäßig ist der Text für jeden <xref:System.Windows.Controls.Page> , der in der [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Liste **zuletzt** verwendete Seiten [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] von angezeigt wird, <xref:System.Windows.Controls.Page>für das. In vielen Fällen ist das für den Benutzer nicht besonders sinnvoll. Sie können den Text jedoch mithilfe einer der folgenden Optionen ändern:

1. Der angefügte `JournalEntry.Name` Attribut Wert.

2. Der `Page.Title` Attribut Wert.

3. Der `Page.WindowTitle` -Attribut Wert und [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] der für die <xref:System.Windows.Controls.Page>aktuelle.

4. Der [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die aktuelle <xref:System.Windows.Controls.Page>. (Standard)

Die Reihenfolge, in der die Optionen aufgeführt sind, entspricht der Rangfolge zum Suchen von Text. Wenn `JournalEntry.Name` z. b. festgelegt ist, werden die anderen Werte ignoriert.

Im folgenden Beispiel wird das `Page.Title` -Attribut verwendet, um den Text zu ändern, der für einen Journal Eintrag angezeigt wird.

[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]

[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]

#### <a name="navigating-the-journal-using-wpf"></a>Navigieren im Journal mit WPF

Obwohl ein Benutzer mithilfe der **zurück**-, **Vorwärts**-und **letzten Seiten** in [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]durch das Journal navigieren kann, können Sie auch mithilfe von deklarativen und programmatischen Mechanismen, die von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]bereitgestellt werden, durch das Journal navigieren. Ein Grund hierfür ist die Bereitstellung einer benutzerdefinierten [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] Navigation in Ihren Seiten.

Sie können die Unterstützung für Journal Navigation deklarativ hinzufügen, indem Sie <xref:System.Windows.Input.NavigationCommands>die von verfügbar gemachten Navigations Befehle verwenden. Im folgenden Beispiel wird veranschaulicht, wie der `BrowseBack` Navigations Befehl verwendet wird.

[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]

Sie können das Journal Programm gesteuert mithilfe eines der folgenden Member der <xref:System.Windows.Navigation.NavigationService> -Klasse navigieren:

- <xref:System.Windows.Navigation.NavigationService.GoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.GoForward%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>

Das Journal kann auch Programm gesteuert bearbeitet werden, wie unter [beibehalten des Inhalts Zustands mit dem Navigationsverlauf](#RetainingContentStateWithNavigationHistory) weiter unten in diesem Thema erläutert.

<a name="PageLifetime"></a>

### <a name="page-lifetime-and-the-journal"></a>Seitenlebensdauer und das Journal

Stellen Sie [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] sich eine mit mehreren Seiten vor, die umfangreiche Inhalte enthalten, einschließlich Grafiken, Animationen und Medien. Die Speicherbeanspruchung für Seiten wie diese könnte recht groß sein, insbesondere, wenn Video- und Audiomedien verwendet werden. Da das Journal die Seiten "speichert", zu denen navigiert wurde, [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] könnte eine solche Menge schnell einen großen und merkbaren Arbeitsspeicher beanspruchen.

Aus diesem Grund ist das Standardverhalten des Journals das speichern <xref:System.Windows.Controls.Page> von Metadaten in jedem Journal Eintrag anstelle eines Verweises auf ein <xref:System.Windows.Controls.Page> -Objekt. Wenn ein Journal Eintrag zu navigiert wird, werden <xref:System.Windows.Controls.Page> seine Metadaten verwendet, um eine neue Instanz des angegebenen <xref:System.Windows.Controls.Page>-Objekts zu erstellen. Folglich hat jede <xref:System.Windows.Controls.Page> , die navigiert wird, die Gültigkeitsdauer, die in der folgenden Abbildung veranschaulicht wird.

![Seiten Lebensdauer](./media/navigation-overview/navigated-page-lifetime.png "Dadurch wird die Lebensdauer angezeigt, wenn eine Seite navigiert wird.")

Obwohl die Verwendung des standardmäßigen journalingverhaltens die Arbeitsspeicher Nutzung einsparen kann, kann die Renderingleistung pro Seite reduziert werden. die Neuerstellung einer <xref:System.Windows.Controls.Page> kann sehr zeitaufwändig sein, insbesondere, wenn Sie über umfangreiche Inhalte verfügt. Wenn Sie eine <xref:System.Windows.Controls.Page> -Instanz im Journal beibehalten müssen, können Sie hierfür zwei Verfahren zeichnen. Zuerst können Sie Programm gesteuert durch Aufrufen der <xref:System.Windows.Controls.Page> <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> -Methode zu einem-Objekt navigieren.

Zweitens können Sie angeben, dass [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eine Instanz <xref:System.Windows.Controls.Page> eines im Journal beibehalten soll, indem Sie die <xref:System.Windows.Controls.Page.KeepAlive%2A> -Eigenschaft `true` auf festlegen (der `false`Standardwert ist). Wie im folgenden Beispiel gezeigt, können Sie deklarativ <xref:System.Windows.Controls.Page.KeepAlive%2A> in Markup festlegen.

[!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]

Die Lebensdauer eines <xref:System.Windows.Controls.Page> -s, der beibehalten wird, unterscheidet sich ganz leicht von einem, der nicht ist. Wenn Sie das erste <xref:System.Windows.Controls.Page> Mal, wenn ein aktiv bleibt, zu der navigiert wird, wird es wie ein <xref:System.Windows.Controls.Page> instanziiert, das nicht aktiv bleibt. Da eine Instanz von <xref:System.Windows.Controls.Page> im Journal beibehalten wird, wird Sie jedoch nie so lange instanziiert, wie Sie im Journal verbleibt. Wenn eine <xref:System.Windows.Controls.Page> Initialisierungs Logik aufweist, die jedes Mal aufgerufen werden muss, wenn der <xref:System.Windows.Controls.Page> navigiert, sollten Sie Sie aus dem Konstruktor in einen Handler für das <xref:System.Windows.FrameworkElement.Loaded> -Ereignis verschieben. Wie in der folgenden Abbildung gezeigt, werden <xref:System.Windows.FrameworkElement.Loaded> das <xref:System.Windows.FrameworkElement.Unloaded> -Ereignis und das-Ereignis immer <xref:System.Windows.Controls.Page> dann ausgelöst, wenn eine zu bzw. von der navigiert wird.

![Wenn die geladenen und entladenen Ereignisse ausgelöst werden](./media/navigation-overview/loaded-and-unloaded-events.png "Geladene und entladene Ereignisse werden ausgelöst, wenn eine Seite zu und aus navigiert wird.")

Wenn ein <xref:System.Windows.Controls.Page> nicht aktiv bleibt, sollten Sie keines der folgenden Aktionen ausführen:

- Speichern eines Verweises auf die Seite oder einen Teil der Seite

- Registrieren von Ereignishandlern für Ereignisse, die nicht von ihr implementiert werden

Bei einem dieser beiden werden Verweise erstellt, die erzwingen <xref:System.Windows.Controls.Page> , dass im Speicher beibehalten wird, auch nachdem er aus dem Journal entfernt wurde.

Im Allgemeinen sollten Sie das Standard <xref:System.Windows.Controls.Page> Verhalten bevorzugen, wenn Sie nicht aktiv <xref:System.Windows.Controls.Page> bleiben. Dies zieht jedoch Auswirkungen auf den Zustand nach sich, die im nächsten Abschnitt erörtert werden.

<a name="RetainingContentStateWithNavigationHistory"></a>

### <a name="retaining-content-state-with-navigation-history"></a>Beibehalten des Inhaltszustands über den Navigationsverlauf

Wenn ein <xref:System.Windows.Controls.Page> nicht aktiv bleibt und über Steuerelemente verfügt, die Daten vom Benutzer sammeln, was geschieht mit den Daten, wenn ein Benutzer von und zurück zu der <xref:System.Windows.Controls.Page>navigiert? Aus Gründen der Benutzererfahrung sollte der Benutzer erwarten, dass die zuvor eingegebenen Daten angezeigt werden. Da bei jeder Navigation eine neue Instanz von <xref:System.Windows.Controls.Page> erstellt wird, werden die Steuerelemente, die die Daten gesammelt haben, neu erstellt, und die Daten gehen verloren.

Glücklicherweise bietet das Journal Unterstützung für die Daten übergreifende <xref:System.Windows.Controls.Page> Daten Navigation, einschließlich der Steuerungsdaten. Insbesondere fungiert der Journal Eintrag für jeden <xref:System.Windows.Controls.Page> als temporärer Container für den zugeordneten <xref:System.Windows.Controls.Page> Zustand. Die folgenden Schritte beschreiben, wie diese Unterstützung verwendet wird <xref:System.Windows.Controls.Page> , wenn eine von der navigiert wird:

1. Dem Journal wird ein Eintrag <xref:System.Windows.Controls.Page> für den aktuellen hinzugefügt.

2. Der Zustand <xref:System.Windows.Controls.Page> der wird mit dem Journal Eintrag für diese Seite gespeichert, der dem BackStack hinzugefügt wird.

3. Die neue <xref:System.Windows.Controls.Page> wird zu navigiert.

Wenn die Seite <xref:System.Windows.Controls.Page> wieder mit dem Journal navigiert wird, werden die folgenden Schritte ausgeführt:

1. Der <xref:System.Windows.Controls.Page> (der obere Journal Eintrag im BackStack) wird instanziiert.

2. Die <xref:System.Windows.Controls.Page> wird mit dem Status aktualisiert, der mit dem Journal Eintrag für den <xref:System.Windows.Controls.Page>gespeichert wurde.

3. <xref:System.Windows.Controls.Page> Wird zurück zu.

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]Diese Unterstützung wird von automatisch verwendet, wenn die folgenden Steuer <xref:System.Windows.Controls.Page>Elemente in einem verwendet werden:

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

Wenn eine <xref:System.Windows.Controls.Page> diese Steuerelemente verwendet, werden die in Sie eingegebenen Daten <xref:System.Windows.Controls.Page> über Navigationen hinweg gespeichert, wie in der folgenden Abbildung anhand der **bevorzugten Farbe** <xref:System.Windows.Controls.ListBox> veranschaulicht.

![Seite mit Steuerelementen, die den Zustand speichern] Die (./media/navigation-overview/data-remembered-across-page-navigations.png "eingegebenen Daten werden über die Seitennavigation hinweg gespeichert.")

Wenn eine <xref:System.Windows.Controls.Page> andere Steuerelemente als die in der vorangehenden Liste aufweist oder wenn State in benutzerdefinierten Objekten gespeichert wird, müssen Sie Code schreiben, damit das Journal den Zustand über <xref:System.Windows.Controls.Page> die Navigation hinweg speichert.

Wenn Sie kleine Zustands übergreifende <xref:System.Windows.Controls.Page> Zustandsänderungen speichern müssen, können Sie Abhängigkeits Eigenschaften (siehe <xref:System.Windows.DependencyProperty>) verwenden, die mit dem <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> Metadata-Flag konfiguriert sind.

Wenn der Status, den <xref:System.Windows.Controls.Page> Sie über die Navigation hinweg berücksichtigen müssen, mehrere Datenelemente umfasst, ist es möglicherweise weniger Code intensiv, den Zustand in einer einzigen Klasse zu kapseln und <xref:System.Windows.Navigation.IProvideCustomContentState> die Schnittstelle zu implementieren.

Wenn Sie durch <xref:System.Windows.Controls.Page>verschiedene Zustände eines einzelnen navigieren müssen, ohne von der <xref:System.Windows.Controls.Page> selbst zu navigieren, können Sie und <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType>verwenden <xref:System.Windows.Navigation.IProvideCustomContentState> .

<a name="Cookies"></a>

### <a name="cookies"></a>Cookies

Eine andere Möglichkeit [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , Daten zu speichern, ist die Verwendung von Cookies, die mithilfe der-Methode und der <xref:System.Windows.Application.SetCookie%2A> - <xref:System.Windows.Application.GetCookie%2A> Methode erstellt, aktualisiert und gelöscht werden. Bei den Cookies, die Sie in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] erstellen können, handelt es sich um dieselben Cookies, die von anderen Webanwendungs Typen verwendet werden. Cookies sind beliebige Daten, die von einer Anwendung auf einem Client Computer entweder während oder über Anwendungs Sitzungen hinweg gespeichert werden. Cookiedaten weisen meist das folgende Format eines Name-Wert-Paares auf.

*Name* `=` *Wert*

Wenn die Daten an <xref:System.Windows.Application.SetCookie%2A>weitergegeben werden, sowie die <xref:System.Uri> des Speicher Orts, für den das Cookie festgelegt werden soll, wird ein Cookie im Arbeitsspeicher erstellt und ist nur für die Dauer der aktuellen Anwendungs Sitzung verfügbar. Diese Art von Cookie wird als *Sitzungs Cookie*bezeichnet.

Wenn Sie ein Cookie über Anwendungssitzungen speichern möchten, muss dem Cookie unter Verwendung des folgenden Formats ein Ablaufdatum hinzugefügt werden.

*NAME* `=` *WERT* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`

Ein Cookie mit einem Ablaufdatum wird im Ordner "temporäre [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Internet Dateien" der aktuellen Installation gespeichert, bis das Cookie abläuft. Ein solches Cookie wird als *dauerhaftes Cookie* bezeichnet, da es über Anwendungs Sitzungen hinweg beibehalten wird.

Sie rufen sowohl Sitzungs-als auch persistente Cookies <xref:System.Windows.Application.GetCookie%2A> durch Aufrufen der- <xref:System.Uri> Methode ab, indem Sie die der Position übergeben, <xref:System.Windows.Application.SetCookie%2A> an der das Cookie mit der-Methode festgelegt wurde

Im folgenden finden Sie einige Möglichkeiten, wie Cookies in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]unterstützt werden:

- [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]eigenständige Anwendungen [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] und können Cookies erstellen und verwalten.

- Auf Cookies, die von einem [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] erstellt werden, kann über den Browser zugegriffen werden.

- [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]s aus derselben Domäne können Cookies erstellen und gemeinsam verwenden.

- [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]und [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] Seiten aus derselben Domäne können Cookies erstellen und freigeben.

- Cookies werden gesendet, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] wenn und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] lose Seiten Webanforderungen stellen.

- Sowohl der obere [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] als auch [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] der gehostete in iframes können auf Cookies zugreifen.

- Die Unterstützung [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] von Cookies in ist für alle unterstützten Browser identisch.

- In [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]wird die P3P-Richtlinie, die sich auf Cookies [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]bezieht, von berücksichtigt, insbesondere in Bezug auf die erst Anbieter [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]-und Drittanbieter.

<a name="Structured_Navigation"></a>

### <a name="structured-navigation"></a>Strukturierte Navigation

Wenn Sie Daten von einem <xref:System.Windows.Controls.Page> an einen anderen übergeben müssen, können Sie die Daten als Argumente an einen nicht parameterlosen Konstruktor <xref:System.Windows.Controls.Page>von übergeben. Beachten Sie Folgendes: Wenn Sie dieses Verfahren verwenden, müssen Sie <xref:System.Windows.Controls.Page> den Alive beibehalten; wenn dies nicht der Fall ist, wird <xref:System.Windows.Controls.Page>das [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.Windows.Controls.Page> mit dem Parameter losen Konstruktor neu installiert, wenn Sie zum nächsten Mal zu navigieren.

Alternativ können Sie <xref:System.Windows.Controls.Page> Eigenschaften implementieren, die mit den Daten, die übermittelt werden müssen, festgelegt werden. Es ist jedoch knifflig, wenn ein <xref:System.Windows.Controls.Page> Daten an die <xref:System.Windows.Controls.Page> zurückgeben muss, die zu ihm navigiert sind. Das Problem besteht darin, dass die Navigation keine Mechanismen unterstützt, mit <xref:System.Windows.Controls.Page> denen sichergestellt wird, dass eine nach der Navigation von zurück an zurückgegeben wird. Im Grunde unterstützt die Navigation keine Semantik mit Aufruf/Rückgabe. Um dieses Problem zu beheben [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , stellt <xref:System.Windows.Navigation.PageFunction%601> die-Klasse bereit, mit der Sie sicher <xref:System.Windows.Controls.Page> stellen können, dass ein auf vorhersagbare und strukturierte Weise zurückgegeben wird. Weitere Informationen finden Sie unter [Übersicht über die strukturierte Navigation](structured-navigation-overview.md).

<a name="The_NavigationWindow_Class"></a>

## <a name="the-navigationwindow-class"></a>Die NavigationWindow-Klasse

Bis jetzt haben Sie das Spektrum der Navigationsdienste kennengelernt, die Sie zum Erstellen von Anwendungen mit navigierbarem Inhalt normalerweise verwenden werden. Diese Dienste wurden im Kontext von [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]erläutert, auch wenn Sie nicht auf [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]beschränkt sind. Moderne Betriebssysteme und Windows-Anwendungen nutzen die Browser Darstellung moderner Benutzer, um die Navigation im Browser Stil in eigenständige Anwendungen zu integrieren. Gängige Beispiele:

- **Wort Thesaurus**: Navigieren Sie zu Wort Auswahl.

- **Datei-Explorer**: Navigieren Sie in Dateien und Ordner.

- **Assistenten**: Aufteilen einer komplexen Aufgabe in mehrere Seiten, zwischen denen navigiert werden kann. Ein Beispiel ist der Assistent für Windows-Komponenten, der das Hinzufügen und Entfernen von Windows-Features behandelt.

Um die Navigation im Browser Stil in ihre eigenständigen Anwendungen zu integrieren, können <xref:System.Windows.Navigation.NavigationWindow> Sie die-Klasse verwenden. <xref:System.Windows.Navigation.NavigationWindow>wird von <xref:System.Windows.Window> abgeleitet und mit derselben Unterstützung für die Navigation erweitert [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] , die bereitstellt. Sie können entweder <xref:System.Windows.Navigation.NavigationWindow> als Hauptfenster der eigenständigen Anwendung oder als sekundäres Fenster (z. b. ein Dialogfeld) verwenden.

Um einen <xref:System.Windows.Navigation.NavigationWindow>zu implementieren, wie bei den meisten Klassen der obersten Ebene<xref:System.Windows.Window>in <xref:System.Windows.Controls.Page> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] (, usw.), verwenden Sie eine Kombination aus Markup und Code Behind. Dies wird im folgenden Beispiel gezeigt.

[!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]

[!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
[!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]

Mit diesem Code <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Navigation.NavigationWindow> wird ein erstellt, das automatisch zu <xref:System.Windows.Controls.Page> einer (Homepage. XAML) navigiert, wenn geöffnet wird. Wenn das das Hauptanwendungsfenster `StartupUri` ist,könnenSieesmitdem-Attributstarten.<xref:System.Windows.Navigation.NavigationWindow> Dies wird im folgenden Markup gezeigt.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]

<xref:System.Windows.Navigation.NavigationWindow> In der folgenden Abbildung wird als Hauptfenster einer eigenständigen Anwendung gezeigt.

![Ein Hauptfenster](./media/navigation-overview/navigation-window-as-main-window.png "Navigationsfenster als Hauptfenster")

In der Abbildung sehen Sie, dass die <xref:System.Windows.Navigation.NavigationWindow> über einen Titel verfügt, obwohl Sie nicht im ImplementierungsCodeausdemvorherigenBeispielfestgelegtwurde.<xref:System.Windows.Navigation.NavigationWindow> Stattdessen wird der Titel mithilfe der <xref:System.Windows.Controls.Page.WindowTitle%2A> -Eigenschaft festgelegt, die im folgenden Code gezeigt wird.

[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]

Das Festlegen <xref:System.Windows.Controls.Page.WindowWidth%2A> der <xref:System.Windows.Controls.Page.WindowHeight%2A> Eigenschaften und wirkt sich <xref:System.Windows.Navigation.NavigationWindow>auch auf die aus.

Normalerweise implementieren Sie Ihre eigenen <xref:System.Windows.Navigation.NavigationWindow> , wenn Sie entweder das Verhalten oder die Darstellung anpassen müssen. Wenn keines von beiden angepasst werden muss, können Sie eine Verknüpfung verwenden. Wenn Sie [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] das Paket <xref:System.Windows.Controls.Page> von als <xref:System.Windows.Application.StartupUri%2A> in einer eigenständigen <xref:System.Windows.Application> <xref:System.Windows.Navigation.NavigationWindow> Anwendung angeben, erstellt automatisch eine zum Hosten von <xref:System.Windows.Controls.Page>. Im folgenden Markup wird gezeigt, wie Sie das aktivieren.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]

Wenn Sie möchten, dass ein sekundäres Anwendungsfenster, z. b <xref:System.Windows.Navigation.NavigationWindow>. ein Dialogfeld, ein ist, können Sie den Code im folgenden Beispiel verwenden, um ihn zu öffnen.

[!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
[!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]

Die folgende Abbildung zeigt das Ergebnis.

![Ein Dialogfeld](./media/navigation-overview/navigation-window-as-dialog-box.png "Navigationsfenster als Dialogfeld")

Wie Sie sehen <xref:System.Windows.Navigation.NavigationWindow> , zeigt [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]die Schaltflächen " **zurück** " und " **weiterleiten** " im Stil an, mit denen Benutzer im Journal navigieren können. Wie in der folgenden Abbildung veranschaulicht, bieten diese Schaltflächen dieselbe Benutzererfahrung.

![Zurück-und vorwärts-Schaltflächen in einem NavigationWindow](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "Zurück-und vorwärts-Schaltflächen in einem Navigationsfenster")

Wenn Ihre Seiten eine eigene Journal Navigationsunterstützung und eine Benutzeroberfläche bereitstellen, können Sie die  <xref:System.Windows.Navigation.NavigationWindow> Schaltflächen " **zurück** " und "Vorwärts" ausblenden <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> , indem `false`Sie den Wert der-Eigenschaft auf festlegen.

Alternativ können Sie die Anpassungs Unterstützung in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verwenden, um den [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von <xref:System.Windows.Navigation.NavigationWindow> sich selbst zu ersetzen.

<a name="Frame_in_Standalone_Applications"></a>

## <a name="the-frame-class"></a>Die Frame-Klasse

Der Browser und <xref:System.Windows.Navigation.NavigationWindow> sind Fenster, die navigierbaren Inhalt hosten. In einigen Fällen verfügen Anwendungen über Inhalt, der nicht von einem ganzen Fenster gehostet werden muss. Stattdessen kann solcher Inhalt in anderem Inhalt gehostet werden. Sie können navigierbaren Inhalt mithilfe der <xref:System.Windows.Controls.Frame> -Klasse in anderen Inhalt einfügen. <xref:System.Windows.Controls.Frame>bietet dieselbe Unterstützung wie <xref:System.Windows.Navigation.NavigationWindow> und [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].

Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.Frame> zu einem <xref:System.Windows.Controls.Page> deklarativ mithilfe des `Frame` -Elements hinzugefügt wird.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]

Mit diesem Markup wird `Source` das-Attribut `Frame` des-Elements mit [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] einem Paket <xref:System.Windows.Controls.Page> für das <xref:System.Windows.Controls.Frame> festgelegt, zu dem das zuerst navigieren soll. In der folgenden Abbildung wird [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] ein- <xref:System.Windows.Controls.Page> Wert mit einem <xref:System.Windows.Controls.Frame> angezeigt, der über einen verfügt, der zwischen mehreren Seiten navigiert ist.

![Ein Frame, der zwischen mehreren Seiten navigiert ist] . (./media/navigation-overview/frame-navigation-between-multiple-pages.png "Dadurch wird eine Frame Navigation zwischen mehreren Seiten angezeigt.")

Sie müssen nicht nur innerhalb des <xref:System.Windows.Controls.Frame> Inhalts <xref:System.Windows.Controls.Page>eines verwenden. Es ist auch üblich, ein <xref:System.Windows.Controls.Frame> im Inhalt <xref:System.Windows.Window>eines zu hosten.

Standardmäßig verwendet <xref:System.Windows.Controls.Frame> nur ein eigenes Journal, wenn kein anderes Journal vorhanden ist. Wenn ein <xref:System.Windows.Controls.Frame> Teil des Inhalts ist, der in einem <xref:System.Windows.Navigation.NavigationWindow> oder einem [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]gehostet wird <xref:System.Windows.Navigation.NavigationWindow> , <xref:System.Windows.Controls.Frame> verwendet das Journal, das zum oder [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]gehört. Manchmal ist es jedoch erforderlich <xref:System.Windows.Controls.Frame> , dass eine für das eigene Journal verantwortlich ist. Ein Grund hierfür ist das Zulassen der Journal Navigation innerhalb der Seiten, die von einem <xref:System.Windows.Controls.Frame>gehostet werden. Dies wird in der folgenden Abbildung verdeutlicht.

![Frame-und Seiten Diagramm](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "Dies zeigt die Journal Navigation in Seiten, die von einem Frame gehostet werden.")

In diesem Fall können Sie das <xref:System.Windows.Controls.Frame> so konfigurieren, dass es ein eigenes Journal verwendet, indem Sie die <xref:System.Windows.Controls.Frame> <xref:System.Windows.Controls.Frame.JournalOwnership%2A> - <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>Eigenschaft von auf festlegen. Dies wird im folgenden Markup gezeigt.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]

In der folgenden Abbildung werden die Auswirkungen der Navigation innerhalb <xref:System.Windows.Controls.Frame> eines veranschaulicht, das sein eigenes Journal verwendet.

![Ein Frame, der sein eigenes Journal verwendet](./media/navigation-overview/frame-uses-its-own-journal.png "Dies zeigt die Auswirkung der Navigation innerhalb eines Frames, der ein eigenes Journal verwendet.")

Beachten Sie, dass die Journal Einträge von der Navigation [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in der <xref:System.Windows.Controls.Frame>angezeigt werden, und [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]nicht von.

> [!NOTE]
> Wenn ein <xref:System.Windows.Controls.Frame> Teil des Inhalts ist, der in einem <xref:System.Windows.Window>gehostet wird <xref:System.Windows.Controls.Frame> , verwendet ein eigenes Journal und zeigt folglich eine eigene Navigation [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]an.

Wenn die Benutzerumgebung eine zum <xref:System.Windows.Controls.Frame> Bereitstellen eines eigenen Journal erfordert, ohne die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]Navigation anzuzeigen, können Sie <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Navigation ausblenden, indem <xref:System.Windows.Visibility.Hidden>Sie auf festlegen. Dies wird im folgenden Markup gezeigt.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]

<a name="Navigation_Hosts"></a>

## <a name="navigation-hosts"></a>Navigationshosts

<xref:System.Windows.Controls.Frame>und <xref:System.Windows.Navigation.NavigationWindow> sind Klassen, die als Navigations Hosts bezeichnet werden. Ein *Navigations Host* ist eine Klasse, die zum Inhalt navigieren und Inhalte anzeigen kann. Um dies zu erreichen, verwendet jeder Navigations Host ein <xref:System.Windows.Navigation.NavigationService> eigenes-und-Journal. Die grundlegende Konstruktion eines Navigationshosts wird in der folgenden Abbildung gezeigt.

![Navigationdiagramme](./media/navigation-overview/navigation-host-construction.png "Grundlegende Erstellung eines Navigations Hosts")

Dadurch können <xref:System.Windows.Navigation.NavigationWindow> und <xref:System.Windows.Controls.Frame> die gleiche Navigationsunterstützung bereitstellen, die eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] bereitstellt, wenn Sie im Browser gehostet wird.

Neben der <xref:System.Windows.Navigation.NavigationService> Verwendung von und einem Journal implementieren Navigations Hosts dieselben <xref:System.Windows.Navigation.NavigationService> Member, die von implementiert werden. Dies wird in der folgenden Abbildung verdeutlicht.

![Ein Journal in einem Frame und in einem NavigationWindow](./media/navigation-overview/navigation-window-and-frame.png "Navigationsfenster und-Frame")

Dies ermöglicht es Ihnen, Navigationsunterstützung direkt für sie zu programmieren. Dies kann in Erwägung gezogen werden, wenn Sie eine benutzerdefinierte [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Navigation für <xref:System.Windows.Controls.Frame> einen bereitstellen müssen, <xref:System.Windows.Window>der in einem gehostet wird. Außerdem implementieren beide Typen zusätzliche Navigations bezogene Member, einschließlich `BackStack` (<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>) und `ForwardStack` (<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>), mit denen Sie die Journal Einträge im Hintergrund aufzählen können. Stapel-bzw. vorwärts Stapel.

Wie bereits erwähnt, können in einer Anwendung mehrere Journale vorhanden sein. Die folgende Abbildung enthält ein Beispiel für die Fälle, in denen das auftreten kann.

![Mehrere Journale in einer Anwendung](./media/navigation-overview/multiple-journals-in-one-application.png "Dies ist ein Beispiel für mehr als ein Journal in einer Anwendung.")

<a name="Navigating_to_Content_Other_than_Pages"></a>

## <a name="navigating-to-content-other-than-xaml-pages"></a>Navigieren zu anderem Inhalt als XAML-Seiten

In diesem Thema werden <xref:System.Windows.Controls.Page> die verschiedenen [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] Navigationsfunktionen von mithilfe von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]Pack veranschaulicht. Eine <xref:System.Windows.Controls.Page> , die in eine Anwendung kompiliert wird, ist jedoch nicht die einzige Art von Inhalt, zu der navigiert werden kann, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] und Pack ist nicht die einzige Möglichkeit, Inhalte zu identifizieren.

Wie in diesem Abschnitt gezeigt, können Sie auch zu " [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] lose Dateien [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] ", "Dateien" und "Objekte" navigieren.

<a name="Navigating_to_Loose_XAML_Files"></a>

### <a name="navigating-to-loose-xaml-files"></a>Navigieren zu Loose XAML-Dateien

Eine lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei ist eine Datei mit den folgenden Merkmalen:

- Enthält nur [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (d. h. keinen Code).

- Verfügt über eine entsprechende Namespacedeklaration.

- Hat die Dateierweiterung .xaml.

Sehen Sie sich beispielsweise den folgenden Inhalt an, der als lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei Person. XAML gespeichert wird.

[!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]

Wenn Sie auf die Datei doppelklicken, wird der Browser geöffnet und navigiert zur Datei und zeigt den Inhalt an. Das wird in der folgenden Abbildung gezeigt.

![Anzeige des Inhalts in der Person. XAML-Datei](./media/navigation-overview/contents-of-person-xaml-file.png "Zeigt den Inhalt der Datei \"Person. XAML\" an.")

Sie können eine lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei aus folgendem anzeigen:

- Einer Website auf dem lokalen Computer, dem Intranet oder dem Internet

- Eine [!INCLUDE[TLA#tla_unc](../../../../includes/tlasharptla-unc-md.md)] Dateifreigabe.

- Dem lokalen Datenträger

Eine Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Datei kann den Favoriten des Browsers hinzugefügt werden, oder Sie ist die Startseite des Browsers.

> [!NOTE]
> Weitere Informationen zum Veröffentlichen und starten von lockeren [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seiten finden Sie unter Bereitstellen [einer WPF-Anwendung](deploying-a-wpf-application-wpf.md).

Eine Einschränkung in Bezug auf Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] besteht darin, dass Sie nur Inhalte hosten können, die sicher mit teilweiser Vertrauenswürdigkeit ausgeführt werden können. `Window` Kann z. b. nicht das Stamm Element einer Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Datei sein. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_Frame"></a>

### <a name="navigating-to-html-files-by-using-frame"></a>Navigieren zu HTML-Dateien mit Frame

Wie Sie vielleicht schon erwartet haben, können Sie [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]auch zu navigieren. Sie müssen lediglich eine [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] bereitstellen, die das http-Schema verwendet. Im folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel wird ein <xref:System.Windows.Controls.Frame> -Wert angezeigt, der zu einer [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] -Seite navigiert.

[!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]

Die Navigation [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] zu erfordert spezielle Berechtigungen. Beispielsweise können Sie nicht von einer [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] navigieren, die in der Sicherheits Sandbox für die teilweise vertrauenswürdige Zone der Internet Zone ausgeführt wird. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>

### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>Navigieren mit dem WebBrowser-Steuerelement zu HTML-Dateien

Das <xref:System.Windows.Controls.WebBrowser> -Steuer [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] Element unterstützt die Interoperabilität von Dokument Hosting, Navigation und Skript/verwaltetem Code. Ausführliche Informationen <xref:System.Windows.Controls.WebBrowser> zum-Steuerelement finden <xref:System.Windows.Controls.WebBrowser>Sie unter.

Wie <xref:System.Windows.Controls.Frame>beim Navigieren zu [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] mithilfe <xref:System.Windows.Controls.WebBrowser> von sind spezielle Berechtigungen erforderlich. Beispielsweise können Sie von einer teilweise vertrauenswürdigen Anwendung nur zu [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] navigieren, die sich auf der Ursprungs Site befindet. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../wpf-partial-trust-security.md).

<a name="Navigating_to_Objects"></a>

### <a name="navigating-to-custom-objects"></a>Navigieren zu benutzerdefinierten Objekten

Wenn Sie über Daten verfügen, die als benutzerdefinierte Objekte gespeichert sind, besteht eine Möglichkeit zum Anzeigen dieser Daten <xref:System.Windows.Controls.Page> darin, einen mit Inhalt zu erstellen, der an diese Objekte gebunden ist (siehe [Übersicht über die Datenbindung](../data/data-binding-overview.md)). Wenn Sie eine ganze Seite nicht nur zu dem Zweck erstellen möchten, die Objekte anzuzeigen, können Sie stattdessen direkt zu ihnen navigieren.

Sehen Sie `Person` sich die-Klasse an, die im folgenden Code implementiert ist.

[!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
[!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]

Um dorthin zu navigieren, rufen Sie die <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> -Methode auf, wie im folgenden Code veranschaulicht.

[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]

[!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
[!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]

Die folgende Abbildung zeigt das Ergebnis.

![Eine Seite, die zu einer Klasse navigiert] . (./media/navigation-overview/page-navigates-to-an-object.png "Dies ist ein Beispiel für eine Seite, die zu einem Objekt navigiert.")

Aus dieser Abbildung können Sie ersehen, dass nichts Nützliches angezeigt wird. Tatsächlich ist der angezeigte Wert der Rückgabewert der `ToString` -Methode für das **Person** -Objekt. Standardmäßig ist dies [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] der einzige Wert, der zum Darstellen des Objekts verwendet werden kann. Sie könnten die `ToString` -Methode überschreiben, um aussagekräftigere Informationen zurückzugeben, obwohl es sich immer noch um einen Zeichen folgen Wert handelt. Eine Methode, die Sie verwenden können, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ist die Verwendung einer Daten Vorlage. Sie können eine Daten Vorlage implementieren, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die mit einem Objekt eines bestimmten Typs verknüpft werden kann. Der folgende Code zeigt eine Daten Vorlage für das `Person` -Objekt.

[!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]

Hier ist die Daten Vorlage mit `Person` der- `x:Type` Markup Erweiterung im `DataType` -Attribut dem-Typ zugeordnet. Die Daten Vorlage bindet `TextBlock` dann Elemente (siehe <xref:System.Windows.Controls.TextBlock>) `Person` an die Eigenschaften der-Klasse. Die folgende Abbildung zeigt die aktualisierte Darstellung des `Person` -Objekts.

![Navigieren zu einer Klasse mit einer Daten Vorlage](./media/navigation-overview/navigating-to-a-class.png "Navigieren zu einer Klasse, die über eine Daten Vorlage verfügt.")

Ein Vorteil dieser Technik liegt in der Konsistenz, die Ihnen die Wiederverwendung der Datenvorlage zur konsistenten Anzeige Ihrer Objekte in der gesamten Anwendung erlaubt.

Weitere Informationen zu Datenvorlagen finden Sie unter [Übersicht über Daten](../data/data-templating-overview.md)Vorlagen.

<a name="Security"></a>

## <a name="security"></a>Sicherheit

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]die Navigationsunterstützung [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] ermöglicht die Navigation zu über das Internet und ermöglicht Anwendungen, Inhalte von Drittanbietern zu hosten. Zum Schutz von Anwendungen und Benutzern vor schädlichem Verhalten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet eine Reihe von Sicherheitsfunktionen, die unter [Sicherheit](../security-wpf.md) und WPF-Sicherheit mit [teilweiser Vertrauens](../wpf-partial-trust-security.md)Würdigkeit erläutert werden.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [Übersicht über die Anwendungsverwaltung](application-management-overview.md)
- [Paket-URI in WPF](pack-uris-in-wpf.md)
- [Übersicht über die strukturierte Navigation](structured-navigation-overview.md)
- [Übersicht über Navigationstopologien](navigation-topologies-overview.md)
- [Themen zu Vorgehensweisen](navigation-how-to-topics.md)
- [Bereitstellen von WPF-Anwendungen](deploying-a-wpf-application-wpf.md)
