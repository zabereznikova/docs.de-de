---
title: "Übersicht über die Navigation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "69"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 73bb3a2f43c5bd91d7a107a0a053381ca7bc0559
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="navigation-overview"></a>Übersicht über die Navigation
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]Navigation im Webbrowserstil, die verwendet werden kann in zwei Arten von Anwendungen unterstützt: eigenständige Anwendungen und [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]. Der Paketinhalt für die Navigation [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet die <xref:System.Windows.Controls.Page> Klasse. Können Sie von einem navigieren <xref:System.Windows.Controls.Page> in eine andere deklarativ durch die Verwendung einer <xref:System.Windows.Documents.Hyperlink>, oder programmgesteuert durch die Verwendung der <xref:System.Windows.Navigation.NavigationService>. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verwendet das Journal, um Seiten zu speichern, von denen weg navigiert wurde, und um wieder zu den Seiten zurück zu navigieren.  
  
 <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Navigation.NavigationService>, und die Erfassung bilden den Kern der angebotenen Unterstützung für die Navigation [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. In dieser Übersicht wird diese Funktionen ausführlich erklärt, bevor auf Erweiterte Navigation-Unterstützung, die Navigation zu loose enthält [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Dateien [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] Dateien und Objekte.  
  
> [!NOTE]
>  In diesem Thema bezieht sich der Begriff "Browser" nur in Browsern, die hosten können [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Anwendungen einschließlich derzeit [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] und Firefox. Wenn spezielle [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] nur von einem bestimmten Browser unterstützte Funktionen, die Browserversion bezeichnet wird.  
   
     
## <a name="navigation-in-wpf-applications"></a>Navigation in WPF-Anwendungen  
 Dieses Thema bietet eine Übersicht über die entscheidenden Navigationsfunktionen in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Diese Funktionen stehen sowohl eigenständige Anwendungen und [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], obwohl in diesem Thema diese innerhalb des Kontexts wird einer [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
> [!NOTE]
>  In diesem Thema nicht erläutert das Erstellen und Bereitstellen von [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Weitere Informationen zu [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], finden Sie unter [WPF-XAML Browser Applications Overview](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
 In diesem Abschnitt werden die folgenden Aspekte der Navigation erklärt und veranschaulicht:  
  
-   [Implementieren einer Seite](#CreatingAXAMLPage)  
  
-   [Konfigurieren einer Startseite](#Configuring_a_Start_Page)  
  
-   [Konfigurieren von Titel, Breite und Höhe des Hostfensters](#ConfiguringAXAMLPage)  
  
-   [Linknavigation](#NavigatingBetweenXAMLPages)  
  
-   [Fragmentnavigation](#FragmentNavigation)  
  
-   [Navigationdienst](#NavigationService)  
  
-   [Programmgesteuerte Navigation mit dem Navigationsdienst](#Programmatic_Navigation_with_the_Navigation_Service)  
  
-   [Navigationslebensdauer](#Navigation_Lifetime)  
  
-   [Aufzeichnung der Navigation mithilfe des Journals](#NavigationHistory)  
  
-   [Seitenlebensdauer und das Journal](#PageLifetime)  
  
-   [Beibehalten des Inhaltszustands über den Navigationsverlauf](#RetainingContentStateWithNavigationHistory)  
  
-   [Cookies](#Cookies)  
  
-   [Strukturierte Navigation](#Structured_Navigation)  
  
<a name="CreatingAXAMLPage"></a>   
### <a name="implementing-a-page"></a>Implementieren einer Seite  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], können Sie navigieren, um mehrere Inhaltstypen, die implizit enthalten [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] Objekte, benutzerdefinierte Objekte, Enumerationswerte, Benutzersteuerelemente, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Dateien und [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] Dateien. Allerdings werden Sie feststellen, dass die allgemeinen und bequeme Methode zum Paketinhalt ist <xref:System.Windows.Controls.Page>. Darüber hinaus <xref:System.Windows.Controls.Page> Navigation-spezifische Funktionen, um ihre Darstellung zu verbessern und vereinfachen die Entwicklung implementiert.  
  
 Mit <xref:System.Windows.Controls.Page>, können Sie deklarativ implementieren eine navigierbare Seite von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Inhalt mithilfe von Markup wie folgt.  
  
 [!code-xaml[NavigationOverviewSnippets#Page1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]  
  
 Ein <xref:System.Windows.Controls.Page> in implementiert wird [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup hat `Page` als Stammelement und erfordert die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Namespacedeklaration. Die `Page` Element enthält den Inhalt, die Sie verwenden möchten, navigieren und diese anzuzeigen. Sie Inhalt hinzufügen, indem die `Page.Content` Property-Element, wie im folgenden Markup gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#Page2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]  
  
 `Page.Content` kann nur ein untergeordnetes Element enthalten. Im vorherigen Beispiel besteht der Inhalt aus einer einzelnen Zeichenfolge, „Hello, Page!“. In der Praxis verwenden Sie in der Regel eine Layout-Steuerelement als untergeordnetes Element (siehe [Layout](../../../../docs/framework/wpf/advanced/layout.md)) enthalten, und verfassen Sie den Inhalt.  
  
 Die untergeordneten Elemente des eine `Page` Element gelten als den Inhalt einer <xref:System.Windows.Controls.Page> und folglich benötigen Sie zum Verwenden der expliziten `Page.Content` Deklaration. Das folgende Markup stellt die deklarative Entsprechung zum vorherigen Beispiel dar.  
  
 [!code-xaml[NavigationOverviewSnippets#Page3XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]  
  
 In diesem Fall `Page.Content` wird automatisch festgelegt, mit den untergeordneten Elementen von der `Page` Element. Weitere Informationen finden Sie unter [WPF-Inhaltsmodell](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
 Eine Markup- <xref:System.Windows.Controls.Page> eignet sich zum Anzeigen des Inhalts. Allerdings eine <xref:System.Windows.Controls.Page> können auch Steuerelemente für die Seitenanzeige, mit denen Benutzer mit der Seite interagieren können, und es auf Benutzerinteraktionen reagieren kann, durch die Behandlung von Ereignissen und Aufrufen von Anwendungslogik. Eine interaktive <xref:System.Windows.Controls.Page> wird mithilfe einer Kombination von Markup und CodeBehind, implementiert, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]  
  
 [!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
 [!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]  
  
 Damit eine Markup- und eine Code-Behind-Datei zusammenarbeiten können, ist die folgende Konfiguration erforderlich:  
  
-   Im Markup der `Page` -Element muss enthalten die `x:Class` Attribut. Als die Anwendung erstellt wird, wird das Vorhandensein des `x:Class` im Markup Datei bewirkt, dass [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] zum Erstellen einer `partial` von abgeleitete Klasse <xref:System.Windows.Controls.Page> und hat den Namen, die von angegeben wird die `x:Class` Attribut. Dies erfordert das Hinzufügen einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespacedeklaration für das [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). Die generierte `partial` -Klasse implementiert `InitializeComponent`, die aufgerufen wird, um die Ereignisse zu registrieren, und legen Sie die Eigenschaften, die im Markup implementiert werden.  
  
-   In der CodeBehind-Klasse muss eine `partial` Klasse mit dem gleichen Namen, die von angegeben wird die `x:Class` Attribut in Markup aus, und leiten sich aus <xref:System.Windows.Controls.Page>. Dadurch wird der Code-Behind-Datei zugeordnet werden die `partial` -Klasse, die für die Markupdatei generiert wird, wenn die Anwendung erstellt wurde (finden Sie unter [Erstellen einer WPF-Anwendung](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)).  
  
-   Im Code-Behind die <xref:System.Windows.Controls.Page> Klasse muss einen Konstruktor, der Aufrufe implementieren die `InitializeComponent` Methode. `InitializeComponent`wird implementiert von Markup generierte `partial` Klasse, um Ereignisse zu registrieren, und legen Sie Eigenschaften, die im Markup definiert sind.  
  
> [!NOTE]
>  Beim Hinzufügen einer neuen <xref:System.Windows.Controls.Page> , dem Projekt mit [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], die <xref:System.Windows.Controls.Page> wird mithilfe von Markup und CodeBehind, implementiert und enthält die erforderliche Konfiguration zum Erstellen der Zuordnung zwischen dem Markup und Code-Behind-Dateien als Die hier beschriebenen.  
  
 Nachdem Sie haben eine <xref:System.Windows.Controls.Page>, Sie können zu navigieren. Das erste an <xref:System.Windows.Controls.Page> , dass eine Anwendung navigiert, müssen Sie den Start konfigurieren <xref:System.Windows.Controls.Page>.  
  
<a name="Configuring_a_Start_Page"></a>   
### <a name="configuring-a-start-page"></a>Konfigurieren einer Startseite  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]s erfordern einen gewissen Umfang an Anwendungsinfrastruktur, um in einem Browser gehostet zu werden. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], <xref:System.Windows.Application> Klasse ist Teil der Anwendungsdefinition einer, die die erforderliche Anwendungsinfrastruktur (finden Sie unter [Application Management Overview](../../../../docs/framework/wpf/app-development/application-management-overview.md)).  
  
 Die Anwendungsdefinition einer wird in der Regel mithilfe von Markup und CodeBehind, mit der Markupdatei als konfiguriert implementiert eine [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `ApplicationDefinition` Element. Im folgenden finden Sie die Anwendungsdefinition einer für eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
 [!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]  
  
 [!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
 [!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]  
  
 Ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] können die Anwendungsdefinition zum Angeben einer Start- <xref:System.Windows.Controls.Page>, also die <xref:System.Windows.Controls.Page> , wird automatisch geladen, wenn die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] wird gestartet. Sie dazu die <xref:System.Windows.Application.StartupUri%2A> Eigenschaft mit dem [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] für den gewünschten <xref:System.Windows.Controls.Page>.  
  
> [!NOTE]
>  In den meisten Fällen die <xref:System.Windows.Controls.Page> entweder in kompiliert oder mit einer Anwendung bereitgestellt wird. In diesen Fällen die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , identifiziert eine <xref:System.Windows.Controls.Page> ist ein Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], also eine [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] entspricht der *Pack* Schema. Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] erläutert werden weiter in [Paket-URIs in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md). Sie können auch mit dem HTTP-Schema zum Inhalt navigieren. Das Schema wird nachfolgend erklärt.  
  
 Sie können festlegen, <xref:System.Windows.Application.StartupUri%2A> deklarativ in Markup, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]  
  
 In diesem Beispiel wird die `StartupUri` -Attribut festgelegt ist, mit einem relativen Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] HomePage.xaml identifiziert. Wenn die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] wird gestartet, HomePage.xaml wird automatisch zu der navigiert und angezeigt. Dies wird veranschaulicht, durch die folgende Abbildung zeigt eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] , die von einem Webserver gestartet wurde.  
  
 ![XBAP-Seite](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure9.png "NavigationOverviewFigure9")  
  
> [!NOTE]
>  Weitere Informationen über die Entwicklung und Bereitstellung von [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], finden Sie unter [WPF-XAML Browser Applications Overview](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md) und [Bereitstellen einer WPF-Anwendung](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md).  
  
<a name="ConfiguringAXAMLPage"></a>   
### <a name="configuring-the-host-windows-title-width-and-height"></a>Konfigurieren von Titel, Breite und Höhe des Hostfensters  
 Dabei Sie aus der vorherigen Abbildung bemerkt haben ist, ist der Titel des Browsers und den Registerkartenbereich die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Der Titel ist zum einen lang und zum anderen weder ansprechend noch informativ. Aus diesem Grund <xref:System.Windows.Controls.Page> bietet eine Möglichkeit zum Ändern des Titels durch Festlegen der <xref:System.Windows.Controls.Page.WindowTitle%2A> Eigenschaft. Darüber hinaus die Breite und Höhe des Browserfensters durch Festlegen von konfigurieren <xref:System.Windows.Controls.Page.WindowWidth%2A> und <xref:System.Windows.Controls.Page.WindowHeight%2A>zugeordnet.  
  
 <xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A>, und <xref:System.Windows.Controls.Page.WindowHeight%2A> kann festgelegt werden deklarativ im Markup, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]  
  
 Das Ergebnis ist in der folgenden Abbildung dargestellt.  
  
 ![Fenstertitel, Höhe, Breite](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure2.png "NavigationOverviewFigure2")  
  
<a name="NavigatingBetweenXAMLPages"></a>   
### <a name="hyperlink-navigation"></a>Linknavigation  
 Eine typische [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] mehrere Seiten umfasst. Die einfachste Methode zum Navigieren von einer Seite ist die Verwendung einer <xref:System.Windows.Documents.Hyperlink>. Können Sie deklarativ hinzufügen einer <xref:System.Windows.Documents.Hyperlink> auf eine <xref:System.Windows.Controls.Page> mithilfe der `Hyperlink` -Element, das in das folgende Markup angezeigt wird.  
  
 [!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 Ein `Hyperlink` -Element ist Folgendes erforderlich:  
  
-   Das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] von der <xref:System.Windows.Controls.Page> navigieren, nach den Angaben von der `NavigateUri` Attribut.  
  
-   Inhalt, der durch ein Benutzer klicken kann, um die Navigation, wie z. B. Text und Bilder zu initiieren (für den Inhalt, der `Hyperlink` Element enthalten können, finden Sie unter <xref:System.Windows.Documents.Hyperlink>).  
  
 Die folgende Abbildung zeigt ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] mit einem <xref:System.Windows.Controls.Page> , besitzt eine <xref:System.Windows.Documents.Hyperlink>.  
  
 ![Seite mit Link](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure3.png "NavigationOverviewFigure3")  
  
 Wie zu erwarten, klicken Sie auf die <xref:System.Windows.Documents.Hyperlink> bewirkt, dass die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] zu navigieren der <xref:System.Windows.Controls.Page> , wird anhand der `NavigateUri` Attribut. Darüber hinaus die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Fügt einen Eintrag für die vorherige <xref:System.Windows.Controls.Page> die Liste der zuletzt verwendete Seiten in [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. Das wird in der folgenden Abbildung gezeigt.  
  
 ![Zurück- und Vorwärts-Schaltflächen](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure4.png "NavigationOverviewFigure4")  
  
 Zusätzlich zur Unterstützung der Navigation von einem <xref:System.Windows.Controls.Page> in eine andere <xref:System.Windows.Documents.Hyperlink> auch der FragmentNavigation unterstützt.  
  
<a name="FragmentNavigation"></a>   
### <a name="fragment-navigation"></a>Fragmentnavigation  
 *FragmentNavigation* ist die Navigation zu einem Inhaltsfragment entweder in der aktuellen <xref:System.Windows.Controls.Page> oder ein anderes <xref:System.Windows.Controls.Page>. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], ein Inhaltsfragment befindet sich der Inhalt, der von einem benannten Element enthalten ist. Ein benanntes Element ist ein Element mit seiner `Name` -Attribut festgelegt ist. Das folgende Markup zeigt eine benannte `TextBlock` Element, das ein Inhaltsfragment enthält.  
  
 [!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]  
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]  
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]  
  
 Für eine <xref:System.Windows.Documents.Hyperlink> , zu dem ein Inhaltsfragment navigiert der `NavigateUri` Attribut muss Folgendes enthalten:  
  
-   Die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] von der <xref:System.Windows.Controls.Page> mit dem Inhaltsfragment zu navigieren.  
  
-   Ein „#“-Zeichen.  
  
-   Der Name des Elements auf der <xref:System.Windows.Controls.Page> , die das Inhaltsfragment enthält.  
  
 Ein Fragment [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] weist das folgende Format auf.  
  
 *SeitenURI* `#` *Elementname*  
  
 Im folgenden wird gezeigt, ein Beispiel für eine `Hyperlink` , navigieren Sie zu einem Inhaltsfragment konfiguriert ist.  
  
 [!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]  
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]  
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]  
  
> [!NOTE]
>  In diesem Abschnitt wird beschrieben, die standardmäßige Implementierung der FragmentNavigation in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]Außerdem können Sie eigene Fragmentnavigationsschema zu implementieren, das Teil Verarbeitung erforderlich ist, die <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType> Ereignis.  
  
> [!IMPORTANT]
>  Sie können zur Fragmenten in loose navigieren [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seiten (Markup- [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateien mit `Page` als Stammelement) nur, wenn die Seiten über durchsucht werden können [!INCLUDE[TLA2#tla_http](../../../../includes/tla2sharptla-http-md.md)].  
>   
>  Allerdings eine lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite zu den eigenen Fragmenten navigieren kann.  
  
<a name="NavigationService"></a>   
### <a name="navigation-service"></a>Navigationdienst  
 Während <xref:System.Windows.Documents.Hyperlink> ermöglicht es einem Benutzer die Navigation zu einem bestimmten initiieren <xref:System.Windows.Controls.Page>, die Arbeit von Suchen und Herunterladen von der Seite erfolgt durch die <xref:System.Windows.Navigation.NavigationService> Klasse. Im Wesentlichen <xref:System.Windows.Navigation.NavigationService> bietet die Möglichkeit, die eine navigationsanforderung im Auftrag Clientcode, z. B. verarbeiten die <xref:System.Windows.Documents.Hyperlink>. Darüber hinaus <xref:System.Windows.Navigation.NavigationService> implementiert auf höherer Ebene Unterstützung für das Nachverfolgen und eine navigationsanforderung zu beeinflussen.  
  
 Wenn eine <xref:System.Windows.Documents.Hyperlink> geklickt wird, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Aufrufe <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> zu suchen und Herunterladen der <xref:System.Windows.Controls.Page> angegebenen Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. Das heruntergeladene <xref:System.Windows.Controls.Page> wird konvertiert, um eine Struktur von Objekten, deren Stammobjekt eine Instanz der heruntergeladenen ist <xref:System.Windows.Controls.Page>. Ein Verweis auf den Stamm <xref:System.Windows.Controls.Page> Objekt befindet sich in der <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType> Eigenschaft. Das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für der Inhalt, zu der navigiert wurde, in gespeichert ist der <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> -Eigenschaft, während die <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> speichert das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die letzte Seite, zu der navigiert wurde.  
  
> [!NOTE]
>  Es ist möglich, dass eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung jeweils mehr als eine derzeit aktive <xref:System.Windows.Navigation.NavigationService>. Weitere Informationen finden Sie unter [Navigation Hosts](#Navigation_Hosts) weiter unten in diesem Thema.  
  
<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>   
### <a name="programmatic-navigation-with-the-navigation-service"></a>Programmgesteuerte Navigation mit dem Navigationsdienst  
 Sie müssen nicht wissen <xref:System.Windows.Navigation.NavigationService> Wenn die Navigation im Markup deklarativ implementiert ist <xref:System.Windows.Documents.Hyperlink>, da <xref:System.Windows.Documents.Hyperlink> verwendet die <xref:System.Windows.Navigation.NavigationService> in Ihrem Namen. Dies bedeutet, dass, so lange wie das direkte oder indirekte übergeordnete von einer <xref:System.Windows.Documents.Hyperlink> ist ein Navigationshost (finden Sie unter [Navigation Hosts](#Navigation_Hosts)), <xref:System.Windows.Documents.Hyperlink> zum Suchen und verwenden die Navigation Hostdienst Navigation zum verarbeiten können eine navigationsanforderung.  
  
 Es gibt jedoch Situationen, wenn Sie verwenden müssen <xref:System.Windows.Navigation.NavigationService> direkt, u. a. folgende:  
  
-   Wenn Sie instanziieren müssen eine <xref:System.Windows.Controls.Page> mit einem nicht standardmäßigen Konstruktor.  
  
-   Wenn Sie Eigenschaften für festlegen, müssen die <xref:System.Windows.Controls.Page> , bevor Sie ihm navigieren.  
  
-   Wenn die <xref:System.Windows.Controls.Page> , zu der navigiert werden nur zur Laufzeit bestimmt werden können muss.  
  
 In diesen Situationen müssen Sie Code schreiben, um die Navigation durch Aufrufen von programmgesteuert zu initiieren der <xref:System.Windows.Navigation.NavigationService.Navigate%2A> Methode der <xref:System.Windows.Navigation.NavigationService> Objekt. Erfordert einen Verweis auf eine <xref:System.Windows.Navigation.NavigationService>.  
  
#### <a name="getting-a-reference-to-the-navigationservice"></a>Abrufen eines Verweises auf NavigationService  
 Aus Gründen, die in behandelt werden die [Navigation Hosts](#Navigation_Hosts) Abschnitt eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung kann mehrere haben <xref:System.Windows.Navigation.NavigationService>. Dies bedeutet, dass der Code eine Möglichkeit zum Suchen benötigt einer <xref:System.Windows.Navigation.NavigationService>, ist in der Regel die <xref:System.Windows.Navigation.NavigationService> , die mit dem aktuellen navigiert <xref:System.Windows.Controls.Page>. Sie erhalten einen Verweis auf eine <xref:System.Windows.Navigation.NavigationService> durch Aufrufen der `static` <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType> Methode. Zum Abrufen der <xref:System.Windows.Navigation.NavigationService> , die navigiert zu einem bestimmten <xref:System.Windows.Controls.Page>, übergeben Sie einen Verweis auf die <xref:System.Windows.Controls.Page> als das Argument für die <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A> Methode. Der folgende Code zeigt, wie die <xref:System.Windows.Navigation.NavigationService> für den aktuellen <xref:System.Windows.Controls.Page>.  
  
 [!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]  
  
 Als Verknüpfung zum Auffinden von der <xref:System.Windows.Navigation.NavigationService> für eine <xref:System.Windows.Controls.Page>, <xref:System.Windows.Controls.Page> implementiert die <xref:System.Windows.Controls.Page.NavigationService%2A> Eigenschaft. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]  
  
> [!NOTE]
>  Ein <xref:System.Windows.Controls.Page> erhalten nur einen Verweis auf die <xref:System.Windows.Navigation.NavigationService> Wenn <xref:System.Windows.Controls.Page> löst die <xref:System.Windows.FrameworkElement.Loaded> Ereignis.  
  
#### <a name="programmatic-navigation-to-a-page-object"></a>Programmgesteuerte Navigation zu einem Seitenobjekt  
 Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Navigation.NavigationService> zur programmgesteuerten Navigation zu einer <xref:System.Windows.Controls.Page>. Programmgesteuerte Navigation ist erforderlich, da die <xref:System.Windows.Controls.Page> , zu dem navigiert kann nur instanziiert werden mit einem einzelnen, nicht standardmäßiger Konstruktor. Die <xref:System.Windows.Controls.Page> mit dem Standardkonstruktor wird im folgenden Markup und Code gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
 [!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]  
  
 Die <xref:System.Windows.Controls.Page> , die navigiert zu der <xref:System.Windows.Controls.Page> mit dem Standardkonstruktor wird im folgenden Markup und Code gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]  
  
 Wenn die <xref:System.Windows.Documents.Hyperlink> für dieses <xref:System.Windows.Controls.Page> ist geklickt, Navigation durch Instanziierung initiiert die <xref:System.Windows.Controls.Page> navigieren, indem die nicht standardmäßigen Konstruktor und die <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> Methode. <xref:System.Windows.Navigation.NavigationService.Navigate%2A>akzeptiert einen Verweis auf das Objekt, das die <xref:System.Windows.Navigation.NavigationService> navigiert, anstatt ein Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
#### <a name="programmatic-navigation-with-a-pack-uri"></a>Programmgesteuerte Navigation mit einem Paket-URI  
 Wenn Sie eine Paket-erstellen müssen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] programmgesteuert (Wenn Sie nur das Pack ermitteln können [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] zur Laufzeit, z. B.), können Sie die <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> Methode. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]  
  
#### <a name="refreshing-the-current-page"></a>Aktualisieren der aktuellen Seite  
 Ein <xref:System.Windows.Controls.Page> wird nicht heruntergeladen, wenn sie das gleiche Pack verfügt [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] als Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , befindet sich in der <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> Eigenschaft. Gezwungen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] um die aktuelle Seite erneut herunterzuladen, rufen Sie die <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> Methode, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
 [!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]  
  
<a name="Navigation_Lifetime"></a>   
### <a name="navigation-lifetime"></a>Navigationslebensdauer  
 Wie Sie sehen, gibt es viele Möglichkeiten zum Einleiten der Navigation. Bei der Navigation wird initiiert, und während der Navigation ausgeführt wird, können Sie verfolgen und beeinflussen die Navigation mit den folgenden Ereignissen, die von implementiert werden <xref:System.Windows.Navigation.NavigationService>:  
  
-   <xref:System.Windows.Navigation.NavigationService.Navigating>. Tritt ein, wenn eine neue Navigation angefordert wird. Kann zum Abbrechen der Navigation verwendet werden.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationProgress>. Tritt regelmäßig während eines Downloadvorgangs auf, um Informationen zum Navigationsstatus bereitzustellen.  
  
-   <xref:System.Windows.Navigation.NavigationService.Navigated>. Tritt ein, nachdem die Seite gefunden und heruntergeladen wurde.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationStopped>. Tritt auf, wenn die Navigation beendet wird (durch Aufrufen von <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>), oder wenn eine neue Navigation angefordert wird, während eine aktuelle Navigation ausgeführt wird.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationFailed>. Tritt ein, wenn ein Fehler ausgelöst wird, während zum angeforderten Inhalt navigiert wird.  
  
-   <xref:System.Windows.Navigation.NavigationService.LoadCompleted>. Tritt ein, wenn der Inhalt, zu dem navigiert wurde, geladen und analysiert wird und mit dem Rendering begonnen wurde.  
  
-   <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>. Tritt ein, wenn die Navigation zu einem Inhaltsfragment beginnt, was in folgenden Fällen geschieht:  
  
    -   Sofort, falls sich das gewünschte Fragment im aktuellen Inhalt befindet.  
  
    -   Nachdem der Inhalt der Quelldatei geladen wurde und sich das gewünschte Fragment in einem anderen Inhalt befindet.  
  
 Die Navigationsereignisse werden in der Reihenfolge ausgelöst, die in der folgenden Abbildung dargestellt wird.  
  
 ![Seitennavigations-Flussdiagramm](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure11.png "NavigationOverviewFigure11")  
  
 Im Allgemeinen eine <xref:System.Windows.Controls.Page> ist nicht auf diese Ereignisse besorgt. Es ist wahrscheinlicher, dass eine Anwendung mit ihnen befassen wird und aus diesem Grund werden diese Ereignisse auch durch ausgelöst der <xref:System.Windows.Application> Klasse:  
  
-   <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>  
  
 Jedes Mal, wenn <xref:System.Windows.Navigation.NavigationService> löst ein Ereignis aus, die <xref:System.Windows.Application> Klasse löst das entsprechende Ereignis aus. <xref:System.Windows.Controls.Frame>und <xref:System.Windows.Navigation.NavigationWindow> bieten dieselben Ereignisse, um die Navigation in ihren jeweiligen Gültigkeitsbereichen erkannt.  
  
 In einigen Fällen ein <xref:System.Windows.Controls.Page> ist ggf. daran interessiert, diese Ereignisse. Z. B. eine <xref:System.Windows.Controls.Page> so verarbeitet die <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> Ereignis, um zu bestimmen, ob Navigation selbst "Abbrechen". Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]  
  
 Wenn Sie einen Handler mit dem ein Navigationsereignis aus Registrieren einer <xref:System.Windows.Controls.Page>, wie im vorherige Beispiel der Fall ist, Sie müssen auch die Registrierung aufheben des ereignishandlers. Wenn Sie dies nicht tun, kommt es möglicherweise Nebeneffekte im Hinblick auf wie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Navigation speichert <xref:System.Windows.Controls.Page> Navigation mit der Erfassung.  
  
<a name="NavigationHistory"></a>   
### <a name="remembering-navigation-with-the-journal"></a>Aufzeichnung der Navigation mithilfe des Journals  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verwendet zwei Stapel, um die Seiten zu speichern, von denen Sie weg navigiert sind: jeweils einen Stapel für die Rückwärts- und einen Stapel für die Vorwärtsnavigation. Wenn Sie navigieren, aus dem aktuellen <xref:System.Windows.Controls.Page> in ein neues <xref:System.Windows.Controls.Page> oder unten, um eine vorhandene <xref:System.Windows.Controls.Page>, den aktuellen <xref:System.Windows.Controls.Page> hinzugefügt wird die *rückwärts-*. Wenn Sie navigieren, aus dem aktuellen <xref:System.Windows.Controls.Page> zurück zur vorherigen <xref:System.Windows.Controls.Page>, den aktuellen <xref:System.Windows.Controls.Page> hinzugefügt wird die *Stapeln*. Der Rückwärts- und der Vorwärtsstapel sowie die Funktion zum Verwalten der Stapel werden zusammen als das Journal bezeichnet. Jedes Element in die rückwärts- und forward-Stapel ist eine Instanz der <xref:System.Windows.Navigation.JournalEntry> Klasse, und wird als bezeichnet eine *Journaleintrags*.  
  
#### <a name="navigating-the-journal-from-internet-explorer"></a>Navigieren im Journal in Internet Explorer  
 Im Prinzip das Journal funktioniert genauso wie die **wieder** und **Vorwärts** Schaltflächen im [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] führen. Diese sind in der folgenden Abbildung dargestellt.  
  
 ![Zurück- und Vorwärts-Schaltflächen](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure4.png "NavigationOverviewFigure4")  
  
 Für [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] die gehostet werden, indem [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] das Journal in der Navigationsleiste integriert [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. Dies ermöglicht es Benutzern in Seiten navigieren ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] mithilfe der **wieder**, **Vorwärts**, und **zuletzt besuchte Seiten** Schaltflächen im [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. Die Erfassung erfolgt keine Integration in [!INCLUDE[TLA2#tla_ie6](../../../../includes/tla2sharptla-ie6-md.md)] auf die gleiche Weise für ist [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] oder Internet Explorer 8. Stattdessen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] rendert eine Ersatz-Navigation [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
> [!IMPORTANT]
>  In [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], wenn ein Benutzer vom navigiert und dann wieder auf ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], nur die Erfassung Einträge für Seiten, die nicht beibehalten wurden, werden in das Journal beibehalten. Erläuterung, wie Sie Seiten beibehalten, finden Sie unter [Seitenlebensdauer und das Journal](#PageLifetime) weiter unten in diesem Thema.  
  
 Standardmäßig wird der Text für jede <xref:System.Windows.Controls.Page> , angezeigt wird, der **zuletzt besuchte Seiten** Liste der [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] ist die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die <xref:System.Windows.Controls.Page>. In vielen Fällen ist das für den Benutzer nicht besonders sinnvoll. Sie können den Text jedoch mithilfe einer der folgenden Optionen ändern:  
  
1.  Der angefügte `JournalEntry.Name` Attributwert.  
  
2.  Die `Page.Title` Attributwert.  
  
3.  Die `Page.WindowTitle` Attributwert und den [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für den aktuellen <xref:System.Windows.Controls.Page>.  
  
4.  Der [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die aktuelle <xref:System.Windows.Controls.Page>. (Standard)  
  
 Die Reihenfolge, in der die Optionen aufgeführt sind, entspricht der Rangfolge zum Suchen von Text. Z. B. wenn `JournalEntry.Name` festgelegt ist, werden die anderen Werte werden ignoriert.  
  
 Im folgenden Beispiel wird die `Page.Title` Attribut zum Ändern des Texts, der für einen Journaleintrag angezeigt wird.  
  
 [!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]  
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]  
  
 [!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
 [!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]  
  
#### <a name="navigating-the-journal-using-wpf"></a>Navigieren im Journal mit WPF  
 Auch wenn ein Benutzer das Journal navigieren kann, mit der **wieder**, **Vorwärts**, und **zuletzt besuchte Seiten** in [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], Sie können auch die Erfassung, Verwendung beider navigieren deklarative und programmgesteuerten Mechanismen von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Ein Grund hierfür besteht darin, benutzerdefinierte Navigation bereitstellen [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] in Ihren Seiten.  
  
 Journal Navigation Unterstützung können Sie deklarativ hinzufügen, die Navigationsbefehle verfügbar gemacht werden, indem Sie mit <xref:System.Windows.Input.NavigationCommands>. Im folgenden Beispiel wird veranschaulicht, wie die `BrowseBack` Navigation-Befehl.  
  
 [!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]  
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]  
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]  
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]  
  
 Sie können die Erfassung programmgesteuert navigieren, indem Sie eines der folgenden Elemente der der <xref:System.Windows.Navigation.NavigationService> Klasse:  
  
-   <xref:System.Windows.Navigation.NavigationService.GoBack%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.GoForward%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>  
  
 Die Erfassung kann auch, wie in beschrieben, programmgesteuert bearbeitet werden [Inhaltszustands mit Navigationsverlauf](#RetainingContentStateWithNavigationHistory) weiter unten in diesem Thema.  
  
<a name="PageLifetime"></a>   
### <a name="page-lifetime-and-the-journal"></a>Seitenlebensdauer und das Journal  
 Betrachten Sie ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] mit mehreren Seiten, die Inhalte enthalten, einschließlich Grafiken, Animationen und Medien. Die Speicherbeanspruchung für Seiten wie diese könnte recht groß sein, insbesondere, wenn Video- und Audiomedien verwendet werden. Das Journal "Seiten, die Navigation zu, z. B. wurden speichert" eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] können schnell eine beträchtlichen Menge an Arbeitsspeicher belegen.  
  
 Aus diesem Grund ist das Standardverhalten der Erfassung zum Speichern von <xref:System.Windows.Controls.Page> Metadaten in jedem Journaleintrag statt einen Verweis auf ein <xref:System.Windows.Controls.Page> Objekt. Wenn eine Journaleintrags navigiert wird, dessen <xref:System.Windows.Controls.Page> Metadaten dient zum Erstellen einer neuen Instanz des angegebenen <xref:System.Windows.Controls.Page>. Daher jedes <xref:System.Windows.Controls.Page> navigiert wird hat die Lebensdauer, die in der folgenden Abbildung dargestellt ist.  
  
 ![Seitenlebensdauer](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure10.PNG "NavigationOverviewFigure10")  
  
 Auch mit dem Standardverhalten Journaling für den Arbeitsspeicherverbrauch speichern kann, kann die Leistung beim Rendern der pro Seite beeinträchtigt werden; umfangreichem eine <xref:System.Windows.Controls.Page> kann zeitaufwändig, insbesondere, wenn es viele Inhalt hat. Wenn Sie beibehalten möchten eine <xref:System.Windows.Controls.Page> Instanz in der Erfassung, die Sie auf diese Weise die folgenden beiden Techniken zeichnen können. Erstens können Sie programmgesteuert zu navigieren eine <xref:System.Windows.Controls.Page> Objekt durch Aufrufen der <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> Methode.  
  
 Zweitens können Sie angeben, die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] beibehalten eine Instanz von einer <xref:System.Windows.Controls.Page> in die Erfassung durch Festlegen der <xref:System.Windows.Controls.Page.KeepAlive%2A> Eigenschaft `true` (die Standardeinstellung ist `false`). Wie im folgenden Beispiel gezeigt, können Sie festlegen <xref:System.Windows.Controls.Page.KeepAlive%2A> deklarativ in Markup.  
  
 [!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]  
  
 Die Lebensdauer einer <xref:System.Windows.Controls.Page> also aufrechterhalten unterscheidet sich leicht von einer nicht. Erstmalig eine <xref:System.Windows.Controls.Page> , bleiben aktiv navigiert wird, ebenso wie instanziiert wird eine <xref:System.Windows.Controls.Page> , die nicht beibehalten. Allerdings da eine Instanz von der <xref:System.Windows.Controls.Page> bleiben in der Erfassung Funktion nie instanziiert wird erneut für solange er in der Erfassung ist. Daher, wenn eine <xref:System.Windows.Controls.Page> verfügt über eine Initialisierungslogik, die jedes Mal aufgerufen werden muss der <xref:System.Windows.Controls.Page> navigiert wird, Sie sollten verschieben Sie sie aus dem Konstruktor in einen Handler für die <xref:System.Windows.FrameworkElement.Loaded> Ereignis. Wie in der folgenden Abbildung gezeigt den <xref:System.Windows.FrameworkElement.Loaded> und <xref:System.Windows.FrameworkElement.Unloaded> Ereignisse werden weiterhin jedes Mal ausgelöst, eine <xref:System.Windows.Controls.Page> navigiert wird in und aus, bzw.  
  
 ![Wenn die Loaded- und Unloaded-Ereignisse ausgelöst werden](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure17.png "NavigationOverviewFigure17")  
  
 Wenn eine <xref:System.Windows.Controls.Page> wird nicht beibehalten, Sie sollten nicht eines der folgenden:  
  
-   Speichern eines Verweises auf die Seite oder einen Teil der Seite  
  
-   Registrieren von Ereignishandlern für Ereignisse, die nicht von ihr implementiert werden  
  
 Eine der folgenden Aktionen werden Verweise, die erzwingen, erstellt die <xref:System.Windows.Controls.Page> im Arbeitsspeicher beibehalten werden sollen, selbst wenn es aus dem Journal entfernt wurde.  
  
 Im Allgemeinen sollten Sie die Standardeinstellung verwenden <xref:System.Windows.Controls.Page> Verhalten nicht halten ein <xref:System.Windows.Controls.Page> aktiv. Dies zieht jedoch Auswirkungen auf den Zustand nach sich, die im nächsten Abschnitt erörtert werden.  
  
<a name="RetainingContentStateWithNavigationHistory"></a>   
### <a name="retaining-content-state-with-navigation-history"></a>Beibehalten des Inhaltszustands über den Navigationsverlauf  
 Wenn eine <xref:System.Windows.Controls.Page> nicht beibehalten, und verfügt über Steuerelemente, die Daten des Benutzers, was geschieht mit Daten, wenn ein Benutzer vom navigiert und zurück zum Sammeln der <xref:System.Windows.Controls.Page>? Aus Gründen der Benutzererfahrung sollte der Benutzer erwarten, dass die zuvor eingegebenen Daten angezeigt werden. Leider, da eine neue Instanz der dem <xref:System.Windows.Controls.Page> wird erstellt, mit jeder Navigation in den Steuerelementen, die gesammelten Daten werden erneut instanziiert und die Daten gehen verloren.  
  
 Glücklicherweise bietet das Journal Unterstützung für die zum Speichern von Daten über <xref:System.Windows.Controls.Page> Navigationen, einschließlich gesteuert werden. Insbesondere Journaleintrags für jede <xref:System.Windows.Controls.Page> fungiert als ein temporärer Container für den zugeordneten <xref:System.Windows.Controls.Page> Zustand. Die folgenden Schritte beschreiben die Verwendung dieser Unterstützung bei einer <xref:System.Windows.Controls.Page> von navigiert wird:  
  
1.  Ein Eintrag für den aktuellen <xref:System.Windows.Controls.Page> Journal hinzugefügt wird.  
  
2.  Der Status der <xref:System.Windows.Controls.Page> wird gespeichert, mit dem Journaleintrag für diese Seite, die die Back-Stapel hinzugefügt wird.  
  
3.  Die neue <xref:System.Windows.Controls.Page> navigiert wird.  
  
 Wenn die Seite <xref:System.Windows.Controls.Page> ist navigiert zurück, mit der Erfassung, die folgenden Schritte erfolgen:  
  
1.  Die <xref:System.Windows.Controls.Page> (der oberste Journaleintrag im Back-Stapel) instanziiert wird.  
  
2.  Die <xref:System.Windows.Controls.Page> wird mit dem Zustand, der mit Journaleintrags für gespeichert wurde, aktualisiert der <xref:System.Windows.Controls.Page>.  
  
3.  Die <xref:System.Windows.Controls.Page> an navigiert wird.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]Diese Unterstützung automatisch verwendet, wenn die folgenden Steuerelemente verwendet werden, auf eine <xref:System.Windows.Controls.Page>:  
  
-   <xref:System.Windows.Controls.CheckBox>  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.Frame>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ProgressBar>  
  
-   <xref:System.Windows.Controls.RadioButton>  
  
-   <xref:System.Windows.Controls.Slider>  
  
-   <xref:System.Windows.Controls.TabControl>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
-   <xref:System.Windows.Controls.TextBox>  
  
 Wenn eine <xref:System.Windows.Controls.Page> diese Steuerelemente verwendet, eingegebene Daten über gespeichert <xref:System.Windows.Controls.Page> Navigationen, wie durch die **Lieblingsfarbe** <xref:System.Windows.Controls.ListBox> in der folgenden Abbildung.  
  
 ![Seite mit Steuerelementen, die den Zustand speichern](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure13.png "NavigationOverviewFigure13")  
  
 Wenn eine <xref:System.Windows.Controls.Page> hat hierfür Steuerelemente als die in der vorangehenden Liste aufgeführt, oder wenn der Status in benutzerdefinierten Objekten gespeichert wird, müssen Sie Code schreiben, um die Erfassung Zustand über dazu führen, dass <xref:System.Windows.Controls.Page> Navigationen.  
  
 Wenn Sie kleine Teile des Zustands merken müssen <xref:System.Windows.Controls.Page> Navigationen, können Sie Abhängigkeitseigenschaften (finden Sie unter <xref:System.Windows.DependencyProperty>), konfiguriert sind, mit der <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> Metadatenflag.  
  
 Wenn der Status, die Ihre <xref:System.Windows.Controls.Page> muss über Navigationen hinweg speichert umfasst mehrere Teile der Daten, die Sie finden es vielleicht weniger Code rechenintensiven kapseln Ihren Zustand in einer einzelnen Klasse und Implementieren der <xref:System.Windows.Navigation.IProvideCustomContentState> Schnittstelle.  
  
 Wenn Sie zum Navigieren durch die verschiedenen Status einer einzelnen müssen <xref:System.Windows.Controls.Page>, ohne Navigieren von den <xref:System.Windows.Controls.Page> selbst, können Sie <xref:System.Windows.Navigation.IProvideCustomContentState> und <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType>.  
  
<a name="Cookies"></a>   
### <a name="cookies"></a>Cookies  
 Eine andere Weise [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen können Daten speichern, ist mit Cookies, die erstellt werden, aktualisiert und gelöscht werden, mithilfe der <xref:System.Windows.Application.SetCookie%2A> und <xref:System.Windows.Application.GetCookie%2A> Methoden. Die Cookies, die Sie, in erstellen können [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sind die gleichen Cookies, die von anderen Arten von Webanwendungen verwenden; Cookies sind beliebige Teile der Daten, die von einer Anwendung auf einem Clientcomputer während oder Anwendung sitzungsübergreifend gespeichert sind. Cookiedaten weisen meist das folgende Format eines Name-Wert-Paares auf.  
  
 *Name* `=` *Wert*  
  
 Wenn Sie die Daten an übergeben <xref:System.Windows.Application.SetCookie%2A>, zusammen mit den <xref:System.Uri> des Speicherorts für den das Cookie festgelegt werden soll, wird ein Cookie im Arbeitsspeicher erstellt, und es ist nur für die Dauer der aktuellen Anwendung Sitzung verfügbar. Diese Art von Cookies wird als bezeichnet eine *Sitzungscookie*.  
  
 Wenn Sie ein Cookie über Anwendungssitzungen speichern möchten, muss dem Cookie unter Verwendung des folgenden Formats ein Ablaufdatum hinzugefügt werden.  
  
 *NAME* `=` *WERT* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`  
  
 Ein Cookie mit einem Ablaufdatum befindet sich in der aktuellen [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] des temporären Internetdateien Installationsordner, bis das Cookie abläuft. Als solches Cookie bezeichnet eine *permanentes Cookie* , da er Anwendung sitzungsübergreifend beibehalten.  
  
 Sie abrufen Sitzung und beständige Cookies durch Aufrufen der <xref:System.Windows.Application.GetCookie%2A> -Methode auf und übergibt die <xref:System.Uri> des Speicherorts, in denen das Cookie wurde festgelegt mit, der <xref:System.Windows.Application.SetCookie%2A> Methode.  
  
 Im folgenden sind einige der Methoden, die Cookies in unterstützt werden [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]:  
  
-   [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]eigenständige Anwendungen und [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] können sowohl erstellen und Verwalten von Cookies.  
  
-   Durch die erstellte Cookies ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] vom Browser aus zugegriffen werden kann.  
  
-   [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]s aus derselben Domäne können Cookies erstellen und gemeinsam verwenden.  
  
-   [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]und [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] Seiten aus der gleichen Domäne erstellen und Freigeben von Cookies können.  
  
-   Cookies werden verteilt, wenn [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] und Netzkabel ordnungsgemäß angeschlossen sind [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seiten erstellen webanforderungen.  
  
-   Sowohl der obersten Ebene [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] und [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] in gehosteten IFRAMES Cookies zugreifen können.  
  
-   Unterstützung von Cookies in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] gilt für alle unterstützten Browsern.  
  
-   In [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], P3P-Richtlinie, die Cookies betrifft, wird berücksichtigt, indem [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], insbesondere in Bezug auf die von erst- und Drittanbietern [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Structured_Navigation"></a>   
### <a name="structured-navigation"></a>Strukturierte Navigation  
 Wenn Sie Daten aus einer übergeben müssen <xref:System.Windows.Controls.Page> zu einem anderen, können Sie die Daten als Argumente übergeben, an einen nicht standardmäßigen Konstruktor eines der <xref:System.Windows.Controls.Page>. Beachten Sie, dass wenn Sie diese Technik verwenden, müssen Sie behalten die <xref:System.Windows.Controls.Page> alive; Wenn nicht, das nächste Mal navigieren Sie zu der <xref:System.Windows.Controls.Page>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] erneut instanziiert die <xref:System.Windows.Controls.Page> mithilfe des Standardkonstruktors.  
  
 Alternativ können Sie Ihre <xref:System.Windows.Controls.Page> können implementieren, Eigenschaften, die mit den Daten, die übergeben werden muss, festgelegt werden. Kompliziert wird dies jedoch, dass bei einer <xref:System.Windows.Controls.Page> müssen Übergabe Daten zurück an die <xref:System.Windows.Controls.Page> , die navigiert. Das Problem besteht darin, dass Navigation Mechanismen nicht systemeigen unterstützen, die sicherstellen einer <xref:System.Windows.Controls.Page> an zurückgegeben wird, nachdem er von dem navigiert wird. Im Grunde unterstützt die Navigation keine Semantik mit Aufruf/Rückgabe. Zur Lösung dieses Problems [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet die <xref:System.Windows.Navigation.PageFunction%601> -Klasse, die Sie verwenden können, um sicherzustellen, dass eine <xref:System.Windows.Controls.Page> an vorhersagbaren und strukturierte Weise zurückgegeben. Weitere Informationen finden Sie unter [strukturierte Navigation Overview](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md).  
  
<a name="The_NavigationWindow_Class"></a>   
## <a name="the-navigationwindow-class"></a>Die NavigationWindow-Klasse  
 Bis jetzt haben Sie das Spektrum der Navigationsdienste kennengelernt, die Sie zum Erstellen von Anwendungen mit navigierbarem Inhalt normalerweise verwenden werden. Diese Dienste wurden im Kontext des erläutert [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], obwohl sie nicht auf beschränkt sind [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Modernen Betriebssysteme und [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] Anwendungen nutzen die Browserfunktionen, um moderne Benutzer im Webbrowserstil Navigation in eigenständigen Anwendungen integriert. Gängige Beispiele:  
  
-   **Word-Thesaurus**: Navigieren durch verschiedene Benennungen (Synonyme)  
  
-   **Datei-Explorer**: Navigieren in Dateien und Ordnern  
  
-   **Assistenten**: Untergliedern einer komplexen Aufgabe in mehrere Seiten, zwischen denen navigiert werden kann. Ein Beispiel ist der Assistent für Windows-Komponenten, die verarbeitet werden, hinzufügen und Entfernen von [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] Funktionen.  
  
 Um die Navigation im Webbrowserstil in eigenständigen Anwendungen zu integrieren, können Sie die <xref:System.Windows.Navigation.NavigationWindow> Klasse. <xref:System.Windows.Navigation.NavigationWindow>leitet sich von <xref:System.Windows.Window> und erweitert Sie sie mit der gleichen Unterstützung für die Navigation, die [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] bereitstellen. Sie können <xref:System.Windows.Navigation.NavigationWindow> als das Hauptfenster der Anwendung eigenständig oder als sekundäres Fenster, z. B. ein Dialogfeld.  
  
 Implementiert eine <xref:System.Windows.Navigation.NavigationWindow>, wie bei den meisten Klassen der obersten Ebene in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] (<xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>usw.), Sie verwenden eine Kombination von Markup und CodeBehind. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]  
  
 [!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
 [!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]  
  
 Dieser Code erstellt ein <xref:System.Windows.Navigation.NavigationWindow> navigiert, die automatisch zu einer <xref:System.Windows.Controls.Page> (HomePage.xaml) Wenn die <xref:System.Windows.Navigation.NavigationWindow> wird geöffnet. Wenn die <xref:System.Windows.Navigation.NavigationWindow> ist das Hauptanwendungsfenster können Sie die `StartupUri` Attribut, um ihn zu starten. Dies wird im folgenden Markup gezeigt.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]  
  
 Die folgende Abbildung zeigt die <xref:System.Windows.Navigation.NavigationWindow> wie das Hauptfenster der eine eigenständige Anwendung.  
  
 ![Ein Hauptfenster](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure18.png "NavigationOverviewFigure18")  
  
 In der Abbildung können Sie sehen, die die <xref:System.Windows.Navigation.NavigationWindow> verfügt über einen Titel, obwohl er, in festgelegt wurde der <xref:System.Windows.Navigation.NavigationWindow> Implementierungscode aus dem vorherigen Beispiel. Der Titel ist legen Sie stattdessen mithilfe der <xref:System.Windows.Controls.Page.WindowTitle%2A> -Eigenschaft, die im folgenden Code dargestellt wird.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]  
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]  
  
 Festlegen der <xref:System.Windows.Controls.Page.WindowWidth%2A> und <xref:System.Windows.Controls.Page.WindowHeight%2A> Eigenschaften wirkt sich auch auf die <xref:System.Windows.Navigation.NavigationWindow>.  
  
 Normalerweise implementieren Sie eine eigene <xref:System.Windows.Navigation.NavigationWindow> Wenn Sie das Verhalten oder die Darstellung anpassen müssen. Wenn keines von beiden angepasst werden muss, können Sie eine Verknüpfung verwenden. Wenn Sie das Pack angeben [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] des eine <xref:System.Windows.Controls.Page> als die <xref:System.Windows.Application.StartupUri%2A> in eine eigenständige Anwendung, <xref:System.Windows.Application> erstellt automatisch eine <xref:System.Windows.Navigation.NavigationWindow> auf Host der <xref:System.Windows.Controls.Page>. Im folgenden Markup wird gezeigt, wie Sie das aktivieren.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]  
  
 Wenn Sie z. B. ein Dialogfeld zu ein sekundären Anwendungsfenster möchten eine <xref:System.Windows.Navigation.NavigationWindow>, Sie können den Code im folgenden Beispiel verwenden, um ihn zu öffnen.  
  
 [!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
 [!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]  
  
 Die folgende Abbildung zeigt das Ergebnis.  
  
 ![Ein Dialogfeld](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure19.png "NavigationOverviewFigure19")  
  
 Wie Sie sehen können, <xref:System.Windows.Navigation.NavigationWindow> zeigt [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]-Stil **wieder** und **Vorwärts** Schaltflächen, mit denen Benutzer im Journal navigieren können. Wie in der folgenden Abbildung veranschaulicht, bieten diese Schaltflächen dieselbe Benutzererfahrung.  
  
 ![Zurück- und Vorwärts-Schaltflächen in einem NavigationWindow](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure20.png "NavigationOverviewFigure20")  
  
 Wenn Ihre Seiten ihre eigenen Journal Navigation Unterstützung und die Benutzeroberfläche bereitstellen, können Sie Ausblenden der **zurück** und **Vorwärts** Schaltflächen angezeigt <xref:System.Windows.Navigation.NavigationWindow> durch Festlegen des Werts von der <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> Eigenschaft `false`.  
  
 Alternativ können Sie die Unterstützung der Anpassung in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] zum Ersetzen der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von der <xref:System.Windows.Navigation.NavigationWindow> selbst.  
  
<a name="Frame_in_Standalone_Applications"></a>   
## <a name="the-frame-class"></a>Die Frame-Klasse  
 Sowohl der Browser und <xref:System.Windows.Navigation.NavigationWindow> sind Fenster, die navigierbaren Inhalt hosten. In einigen Fällen verfügen Anwendungen über Inhalt, der nicht von einem ganzen Fenster gehostet werden muss. Stattdessen kann solcher Inhalt in anderem Inhalt gehostet werden. Andere Inhalte navigierbaren Inhalt einfügen möchten, verwenden die <xref:System.Windows.Controls.Frame> Klasse. <xref:System.Windows.Controls.Frame>bietet die gleiche Unterstützung als <xref:System.Windows.Navigation.NavigationWindow> und [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
 Das folgende Beispiel veranschaulicht das Hinzufügen einer <xref:System.Windows.Controls.Frame> auf eine <xref:System.Windows.Controls.Page> deklarativ mithilfe der `Frame` Element.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]  
  
 Dieses Markup legt die `Source` Attribut des der `Frame` Element mit einem Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die <xref:System.Windows.Controls.Page> , der <xref:System.Windows.Controls.Frame> sollten anfangs navigieren Sie zu. Die folgende Abbildung zeigt ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] mit einem <xref:System.Windows.Controls.Page> , besitzt eine <xref:System.Windows.Controls.Frame> , die zwischen mehreren Seiten navigiert.  
  
 ![Ein Frame, der zwischen mehreren Seiten navigiert](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure5.png "NavigationOverviewFigure5")  
  
 Sie müssen nicht nur verwenden <xref:System.Windows.Controls.Frame> innerhalb des Inhalts von einem <xref:System.Windows.Controls.Page>. Es ist auch häufig zum Hosten einer <xref:System.Windows.Controls.Frame> innerhalb des Inhalts von einem <xref:System.Windows.Window>.  
  
 Standardmäßig <xref:System.Windows.Controls.Frame> verwendet nur ein eigenen Journal in Abwesenheit einer anderen Erfassung. Wenn eine <xref:System.Windows.Controls.Frame> ist Teil des Inhalts, der innerhalb einer gehostet wird eine <xref:System.Windows.Navigation.NavigationWindow> oder ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], <xref:System.Windows.Controls.Frame> verwendet das Journal, gehört zu, den <xref:System.Windows.Navigation.NavigationWindow> oder [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. In einigen Fällen jedoch eine <xref:System.Windows.Controls.Frame> müssen möglicherweise für einen eigenen Journal zuständig ist. Ein Grund dafür besteht darin Journal Navigation innerhalb der Seiten zu ermöglichen, die von gehosteten eine <xref:System.Windows.Controls.Frame>. Dies wird in der folgenden Abbildung verdeutlicht.  
  
 ![Frame- und Seiten-Diagramm](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure7.png "NavigationOverviewFigure7")  
  
 In diesem Fall können Sie konfigurieren die <xref:System.Windows.Controls.Frame> mit einem eigenen Journal durch Festlegen der <xref:System.Windows.Controls.Frame.JournalOwnership%2A> Eigenschaft von der <xref:System.Windows.Controls.Frame> auf <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>. Dies wird im folgenden Markup gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]  
  
 Die folgende Abbildung veranschaulicht die Auswirkung der Navigation in einem <xref:System.Windows.Controls.Frame> , ein eigenen Journal verwendet.  
  
 ![Ein Frame mit einem eigenen Journal](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure8.png "NavigationOverviewFigure8")  
  
 Beachten Sie, die die Einträge, durch die Navigation angezeigt werden [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in der <xref:System.Windows.Controls.Frame>, sondern nach [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)].  
  
> [!NOTE]
>  Wenn eine <xref:System.Windows.Controls.Frame> ist Teil des Inhalts, der in gehostet ist ein <xref:System.Windows.Window>, <xref:System.Windows.Controls.Frame> verwendet ein eigenen Journal und zeigt daher einen eigenen Navigationsbereich [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Wenn benutzerfreundliche erfordert eine <xref:System.Windows.Controls.Frame> eigenen Journal bereitstellen, ohne die Navigation mit [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], können Sie die Navigation ausblenden [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] durch Festlegen der <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> auf <xref:System.Windows.Visibility.Hidden>. Dies wird im folgenden Markup gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]  
  
<a name="Navigation_Hosts"></a>   
## <a name="navigation-hosts"></a>Navigationshosts  
 <xref:System.Windows.Controls.Frame>und <xref:System.Windows.Navigation.NavigationWindow> sind Klassen, die als Navigationshosts für die bekannt sind. Ein *Navigationshost* ist eine Klasse, navigieren Sie zu und Inhalt anzeigen kann. Um dies zu erreichen, jeden Navigationshost verwendet eine eigene <xref:System.Windows.Navigation.NavigationService> und Journal. Die grundlegende Konstruktion eines Navigationshosts wird in der folgenden Abbildung gezeigt.  
  
 ![Navigatordiagramme](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure15.png "NavigationOverviewFigure15")  
  
 Im Wesentlichen ermöglicht dies <xref:System.Windows.Navigation.NavigationWindow> und <xref:System.Windows.Controls.Frame> Navigation bereitstellen identisch zu unterstützen, die eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] bereitstellt, wenn im Browser gehostet.  
  
 Neben der Verwendung von <xref:System.Windows.Navigation.NavigationService> und eine Erfassung Navigationshosts implementieren, das dieselben Member, die <xref:System.Windows.Navigation.NavigationService> implementiert. Dies wird in der folgenden Abbildung verdeutlicht.  
  
 ![Ein Journal in einem Frame und in einem NavigationWindow](../../../../docs/framework/wpf/app-development/media/naivgationoverviewfigure24.png "NaivgationOverviewFigure24")  
  
 Dies ermöglicht es Ihnen, Navigationsunterstützung direkt für sie zu programmieren. Können Sie dies berücksichtigen, wenn Sie eine benutzerdefinierte Navigation bereitstellen müssen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für eine <xref:System.Windows.Controls.Frame> , gehostet einer <xref:System.Windows.Window>. Beide Typen implementieren darüber hinaus zusätzliche, Navigation bezogene Elemente, einschließlich `BackStack` (<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>) und `ForwardStack` (<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>), dem ermöglichen es Ihnen, die Einträge in der Rückseite auflisten Stack- und Stapel bzw. weiterleiten.  
  
 Wie bereits erwähnt, können in einer Anwendung mehrere Journale vorhanden sein. Die folgende Abbildung enthält ein Beispiel für die Fälle, in denen das auftreten kann.  
  
 ![Mehrere Journale in einer Anwendung](../../../../docs/framework/wpf/app-development/media/naivgationoverviewfigure25.png "NaivgationOverviewFigure25")  
  
<a name="Navigating_to_Content_Other_than_Pages"></a>   
## <a name="navigating-to-content-other-than-xaml-pages"></a>Navigieren zu anderem Inhalt als XAML-Seiten  
 In diesem Thema <xref:System.Windows.Controls.Page> und Pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] verwendet werden, um die Veranschaulichung der verschiedenen Navigationsfunktionen der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Allerdings eine <xref:System.Windows.Controls.Page> , kompiliert in eine Anwendung ist nicht der einzige Typ von Inhalt, zu der navigiert werden kann, und Pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] werden nicht die einzige Möglichkeit, Inhalte zu identifizieren.  
  
 Wie in diesem Abschnitt wird veranschaulicht, können Sie auch Navigieren zu loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateien [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] Dateien und Objekte.  
  
<a name="Navigating_to_Loose_XAML_Files"></a>   
### <a name="navigating-to-loose-xaml-files"></a>Navigieren zu Loose XAML-Dateien  
 Eine lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei ist eine Datei mit den folgenden Merkmalen:  
  
-   Enthält nur [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (d. h. kein Code).  
  
-   Verfügt über eine entsprechende Namespacedeklaration.  
  
-   Hat die Dateierweiterung .xaml.  
  
 Betrachten Sie beispielsweise den folgenden Inhalt, die als eine lose gespeichert ist [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei Person.xaml.  
  
 [!code-xaml[NavigationOverviewSnippets#LooseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]  
  
 Wenn Sie auf die Datei doppelklicken, wird der Browser geöffnet und navigiert zur Datei und zeigt den Inhalt an. Das wird in der folgenden Abbildung gezeigt.  
  
 ![Anzeige des Inhalts in der Datei Person.XAML](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure21.png "NavigationOverviewFigure21")  
  
 Sie können eine lose anzeigen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] aus folgender Datei:  
  
-   Einer Website auf dem lokalen Computer, dem Intranet oder dem Internet  
  
-   Ein [!INCLUDE[TLA#tla_unc](../../../../includes/tlasharptla-unc-md.md)] -Dateifreigabe.  
  
-   Dem lokalen Datenträger  
  
 Eine lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei kann die Browser-Favoriten hinzugefügt werden, oder die Browser-Startseite.  
  
> [!NOTE]
>  Weitere Informationen zum Veröffentlichen und Starten von loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seiten angezeigt [Bereitstellen einer WPF-Anwendung](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md).  
  
 Eine Einschränkung in Bezug auf lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] darin, dass Sie nur Inhalt hosten können, der sicher in teilweiser Vertrauenswürdigkeit ausgeführt werden kann. Beispielsweise `Window` nicht das Stammelement einer losen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
<a name="Navigating_to_HTML_Files_Using_Frame"></a>   
### <a name="navigating-to-html-files-by-using-frame"></a>Navigieren zu HTML-Dateien mit Frame  
 Wie zu erwarten, können Sie auch zu navigieren [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]. Sie benötigen, geben Sie eine [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , verwendet das HTTP-Schema. Z. B. die folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zeigt eine <xref:System.Windows.Controls.Frame> , die navigiert zu einem [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] Seite.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]  
  
 Navigieren zu [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] sind spezielle Berechtigungen erforderlich. Angenommen, Sie können nicht aus navigieren eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] , die in der Sandbox der Internetzone teilweiser Vertrauenswürdigkeit Sicherheit ausgeführt wird. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>   
### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>Navigieren mit dem WebBrowser-Steuerelement zu HTML-Dateien  
 Die <xref:System.Windows.Controls.WebBrowser> -Steuerelement unterstützt [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] Dokument hostet, Navigation und Skript/verwalteten code Interoperabilität. Ausführliche Informationen bezüglich der <xref:System.Windows.Controls.WebBrowser> steuern, finden Sie unter <xref:System.Windows.Controls.WebBrowser>.  
  
 Wie <xref:System.Windows.Controls.Frame>, navigieren Sie zu [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] mit <xref:System.Windows.Controls.WebBrowser> sind spezielle Berechtigungen erforderlich. Navigieren z. B. in einer teilweise vertrauenswürdigen Anwendung Sie können nur für [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] am Standort Ursprung befindet. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
<a name="Navigating_to_Objects"></a>   
### <a name="navigating-to-custom-objects"></a>Navigieren zu benutzerdefinierten Objekten  
 Wenn Sie über Daten, die als benutzerdefinierte Objekte gespeichert ist verfügen, wird eine Möglichkeit zum Anzeigen dieser Daten zum Erstellen einer <xref:System.Windows.Controls.Page> mit Inhalt, der an diese Objekte gebunden ist (finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)). Wenn Sie eine ganze Seite nicht nur zu dem Zweck erstellen möchten, die Objekte anzuzeigen, können Sie stattdessen direkt zu ihnen navigieren.  
  
 Betrachten Sie die `Person` -Klasse, die in den folgenden Code implementiert ist.  
  
 [!code-csharp[NavigateToObjectSnippets#PersonClassCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
 [!code-vb[NavigateToObjectSnippets#PersonClassCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]  
  
 Um darauf zu navigieren, rufen Sie die <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> Methode, wie im folgenden Code gezeigt.  
  
 [!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]  
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]  
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]  
  
 [!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
 [!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]  
  
 Die folgende Abbildung zeigt das Ergebnis.  
  
 ![Eine Seite, die zu einer Klasse navigiert](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure22.png "NavigationOverviewFigure22")  
  
 Aus dieser Abbildung können Sie ersehen, dass nichts Nützliches angezeigt wird. Tatsächlich ist der Wert, der angezeigt wird der Rückgabewert von der `ToString` Methode für die **Person** Objekt; standardmäßig ist dies die einzige-Wert, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] können zum Darstellen des Objekts. Sie könnten überschreiben die `ToString` Methode, um aussagekräftigere Informationen zurückzugeben, obwohl es weiterhin nur ein Zeichenfolgenwert sein. Eine Technik können, die die Darstellungsfunktionen von nutzt [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eine Datenvorlage verwendet wird. Sie können eine Datenvorlage implementieren, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] können ein Objekt eines bestimmten Typs zuordnen. Der folgende Code zeigt eine Datenvorlage für den `Person` Objekt.  
  
 [!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]  
  
 Hier wird die Datenvorlage zugeordnet ist die `Person` Typ mithilfe der `x:Type` -Markuperweiterung in der `DataType` Attribut. Klicken Sie dann die Datenvorlage bindet `TextBlock` Elemente (finden Sie unter <xref:System.Windows.Controls.TextBlock>) an den Eigenschaften des der `Person` Klasse. Die folgende Abbildung zeigt die aktualisierte Darstellung der `Person` Objekt.  
  
 ![Navigation zu einer Klasse mit einer Datenvorlage](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure23.png "NavigationOverviewFigure23")  
  
 Ein Vorteil dieser Technik liegt in der Konsistenz, die Ihnen die Wiederverwendung der Datenvorlage zur konsistenten Anzeige Ihrer Objekte in der gesamten Anwendung erlaubt.  
  
 Weitere Informationen zu Datenvorlagen finden Sie unter [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
<a name="Security"></a>   
## <a name="security"></a>Sicherheit  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]Unterstützung für die Navigation können [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] , zu der navigiert werden, über das Internet, und sie können Anwendungen hosten Drittanbieter-Inhalte. Zum Schutz von Anwendungen und Benutzern von schädlichen Verhalten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet eine Vielzahl von Sicherheitsfunktionen, die in beschriebenen [Sicherheit](../../../../docs/framework/wpf/security-wpf.md) und [WPF teilweise Vertrauenswürdigkeit Sicherheit](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Application.SetCookie%2A>  
 <xref:System.Windows.Application.GetCookie%2A>  
 [Übersicht über die Anwendungsverwaltung](../../../../docs/framework/wpf/app-development/application-management-overview.md)  
 [Paket-URI in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)  
 [Übersicht über die strukturierte Navigation](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md)  
 [Übersicht über Navigationstopologien](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/app-development/navigation-how-to-topics.md)  
 [Bereitstellen von WPF-Anwendungen](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)
