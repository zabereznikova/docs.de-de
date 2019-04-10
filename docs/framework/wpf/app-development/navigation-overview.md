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
ms.openlocfilehash: feccd6978d0a3cf8db60bbd505826433c93e3276
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227196"
---
# <a name="navigation-overview"></a>Übersicht über die Navigation
Windows Presentation Foundation (WPF) unterstützt die Navigation im Browserstil, die verwendet werden, kann in zwei Arten von Anwendungen: eigenständige Anwendungen und [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]. Zum Packen von Inhalten für die Navigation [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet die <xref:System.Windows.Controls.Page> Klasse. Können Sie von einem navigieren <xref:System.Windows.Controls.Page> in ein anderes deklarativ mithilfe einer <xref:System.Windows.Documents.Hyperlink>, oder programmgesteuert, durch die Verwendung der <xref:System.Windows.Navigation.NavigationService>. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verwendet das Journal, um Seiten zu speichern, von dem navigiert wurde, und Navigation zu ihnen.  
  
 <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Navigation.NavigationService>, und das Journal bilden den Kern der navigationsunterstützung cloudsicherheitsstandard [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. In dieser Übersicht diese Features ausführlich untersucht, bevor Sie die erweiterte navigationsunterstützung, die Navigation zu loose enthält behandelt [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Dateien [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] Dateien und Objekte.  
  
> [!NOTE]
>  In diesem Thema bezieht sich der Begriff "Browser" nur für Browser, die hosten können [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Anwendungen einschließlich derzeit [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] und Firefox. Wenn spezielle [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Funktionen werden nur von einem bestimmten Browser unterstützt, wird die Version des Browsers bezeichnet.  

## <a name="navigation-in-wpf-applications"></a>Navigation in WPF-Anwendungen  
 Dieses Thema enthält eine Übersicht über die entscheidenden Navigationsfunktionen in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Diese Funktionen sind verfügbar, um sowohl von eigenständigen Anwendungen und [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], obwohl in diesem Thema sie innerhalb des Kontexts werden einer [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
> [!NOTE]
>  In diesem Thema nicht beschrieben, wie erstellen und Bereitstellen von [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Weitere Informationen zu [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], finden Sie unter [Übersicht über WPF-XAML-Browseranwendungen](wpf-xaml-browser-applications-overview.md).  
  
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
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], gelangen Sie zu verschiedenen Inhaltstypen, die enthalten, .NET Framework-Objekten, benutzerdefinierte Objekte, Enumerationswerte, Benutzersteuerelemente, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Dateien und [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] Dateien. Allerdings werden Sie feststellen, dass es sich bei ist die gebräuchlichste und bequemste Methode zum Packen von Inhalten mithilfe von <xref:System.Windows.Controls.Page>. Darüber hinaus <xref:System.Windows.Controls.Page> navigationsspezifische Features, um ihre Darstellung zu verbessern und vereinfachen die Entwicklung implementiert.  
  
 Mithilfe von <xref:System.Windows.Controls.Page>, Ihnen das deklarative Implementieren einer navigierbaren Seite von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Inhalt durch Folgendes Markup verwenden.  
  
 [!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]  
  
 Ein <xref:System.Windows.Controls.Page> in implementiert wird [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup hat `Page` als Stammelement und erfordert die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)][!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Namespacedeklaration. Die `Page` -Element enthält den Inhalt, die Sie verwenden möchten, navigieren und diese anzuzeigen. Sie fügen Inhalt hinzu, durch Festlegen der `Page.Content` Property-Element, wie im folgenden Markup gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]  
  
 `Page.Content` kann nur ein untergeordnetes Element enthalten. im vorherigen Beispiel ist der Inhalt ist eine einzelne Zeichenfolge, die "Hello, Page!" In der Praxis verwenden Sie in der Regel ein Layoutsteuerelement als untergeordnetes Element (finden Sie unter [Layout](../advanced/layout.md)) enthalten, und verfassen Sie den Inhalt.  
  
 Die untergeordneten Elemente des eine `Page` Element gelten als den Inhalt des eine <xref:System.Windows.Controls.Page> und, folglich nicht müssen Sie zum Verwenden der expliziten `Page.Content` Deklaration. Das folgende Markup stellt die deklarative Entsprechung zum vorherigen Beispiel dar.  
  
 [!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]  
  
 In diesem Fall `Page.Content` wird automatisch festgelegt, mit den untergeordneten Elementen von der `Page` Element. Weitere Informationen finden Sie unter [WPF-Inhaltsmodell](../controls/wpf-content-model.md).  
  
 Eine nur-Markup- <xref:System.Windows.Controls.Page> eignet sich zum Anzeigen von Inhalt. Allerdings eine <xref:System.Windows.Controls.Page> können auch Anzeigesteuerelemente, mit denen Benutzer mit der Seite interagieren können, und es kann auf eine Benutzerinteraktion reagieren, indem Ereignisse behandelt und Anwendungslogik aufgerufen. Eine interaktive <xref:System.Windows.Controls.Page> wird mithilfe einer Kombination aus Markup und CodeBehind implementiert, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]  
  
 [!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
 [!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]  
  
 Damit eine Markup- und eine Code-Behind-Datei zusammenarbeiten können, ist die folgende Konfiguration erforderlich:  
  
-   Im Markup der `Page` -Element muss enthalten der `x:Class` Attribut. Wenn die Anwendung erstellt wird, wird das Vorhandensein des `x:Class` im Markup führt [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] zum Erstellen einer `partial` abgeleitete Klasse <xref:System.Windows.Controls.Page> und hat den Namen, die angegeben wird die `x:Class` Attribut. Dies erfordert das Hinzufügen einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespace-Deklaration für die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). Die generierte `partial` -Klasse implementiert `InitializeComponent`, die aufgerufen wird, zum Registrieren der Ereignisse, und legen Sie die Eigenschaften, die im Markup implementiert sind.  
  
-   Im Code-Behind muss die Klasse muss eine `partial` Klasse mit dem gleichen Namen, die angegeben wird die `x:Class` Attribut im Markup, und es muss abgeleitet <xref:System.Windows.Controls.Page>. Dadurch wird der Code-Behind-Datei zugeordnet werden die `partial` -Klasse, die für die Markupdatei generiert wird, wenn die Anwendung erstellt wird (finden Sie unter [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md)).  
  
-   Im Code-Behind muss die <xref:System.Windows.Controls.Page> Klasse implementieren muss einen Konstruktor, der Aufrufe der `InitializeComponent` Methode. `InitializeComponent` wird implementiert, indem Sie das Markup generierte `partial` Klasse zum Registrieren von Ereignissen und Festlegen von Eigenschaften, die im Markup definierte.  
  
> [!NOTE]
>  Beim Hinzufügen einer neuen <xref:System.Windows.Controls.Page> zu Ihrem [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], <xref:System.Windows.Controls.Page> wird mithilfe von Markup und CodeBehind implementiert und enthält die erforderlichen Konfigurationsschritte zum Erstellen der Verknüpfung zwischen Markup- und Code-Behind-Dateien als hier beschrieben.  
  
 Nachdem Sie haben eine <xref:System.Windows.Controls.Page>, können Sie darin navigieren. Die erste an <xref:System.Windows.Controls.Page> , dass eine Anwendung navigiert, müssen Sie den Start konfigurieren <xref:System.Windows.Controls.Page>.  
  
<a name="Configuring_a_Start_Page"></a>   
### <a name="configuring-a-start-page"></a>Konfigurieren einer Startseite  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] benötigen Sie eine bestimmte Menge an Anwendungsinfrastruktur, um in einem Browser gehostet werden. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], <xref:System.Windows.Application> Klasse ist Teil der Definition einer Anwendung, die die erforderliche Anwendungsinfrastruktur (finden Sie unter [Übersicht über die Anwendungsverwaltung](application-management-overview.md)).  
  
 Eine Anwendungsdefinition wird normalerweise mithilfe von Markup und Code-Behind muss mit der Akku oder Netzbetrieb Markup-Datei implementiert eine [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`ApplicationDefinition` Element. Im folgenden finden Sie eine Anwendungsdefinition für eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
 [!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]  
  
 [!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
 [!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]  
  
 Ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] können die Anwendungsdefinition zum Angeben einer Start- <xref:System.Windows.Controls.Page>, d.h. die <xref:System.Windows.Controls.Page> , wird automatisch geladen, wenn die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] gestartet wird. Diesem Zweck legen die <xref:System.Windows.Application.StartupUri%2A> Eigenschaft mit dem [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] für die gewünschte <xref:System.Windows.Controls.Page>.  
  
> [!NOTE]
>  In den meisten Fällen die <xref:System.Windows.Controls.Page> entweder in kompiliert oder mit einer Anwendung bereitgestellt wird. In diesen Fällen die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , identifiziert eine <xref:System.Windows.Controls.Page> ist ein Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], d.h. eine [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] entspricht der *Pack* Schema. Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] werden weiter unten in [Paket-URIs in WPF](pack-uris-in-wpf.md). Sie können auch mit dem HTTP-Schema zum Inhalt navigieren. Das Schema wird nachfolgend erklärt.  
  
 Sie können festlegen, <xref:System.Windows.Application.StartupUri%2A> deklarativ in Markup, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]  
  
 In diesem Beispiel die `StartupUri` -Attribut festgelegt ist, mit einem relativen Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] HomePage.xaml identifiziert. Wenn die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] wird gestartet, HomePage.xaml automatisch navigiert und angezeigt. Dies wird durch die folgende Abbildung veranschaulicht dargestellt eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] , die von einem Webserver gestartet wurde.  
  
 ![XBAP-Seite](./media/navigation-overview/xbap-launched-from-a-web-server.png "dadurch eine XBAP, die von einem Webserver gestartet wird.")  
  
> [!NOTE]
>  Weitere Informationen zu Entwicklung und Bereitstellung von [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], finden Sie unter [Übersicht über WPF-XAML-Browseranwendungen](wpf-xaml-browser-applications-overview.md) und [Bereitstellen von WPF-Anwendungen](deploying-a-wpf-application-wpf.md).  
  
<a name="ConfiguringAXAMLPage"></a>   
### <a name="configuring-the-host-windows-title-width-and-height"></a>Konfigurieren von Titel, Breite und Höhe des Hostfensters  
 Eine Sache, die Sie haben, in der vorherigen Abbildung bemerkt vielleicht ist, dass der Titel des Browsers und Registerkartenbereichs sowohl die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Der Titel ist zum einen lang und zum anderen weder ansprechend noch informativ. Aus diesem Grund <xref:System.Windows.Controls.Page> bietet eine Möglichkeit zum Ändern des Titels durch Festlegen der <xref:System.Windows.Controls.Page.WindowTitle%2A> Eigenschaft. Darüber hinaus die Breite und Höhe des Browserfensters durch Festlegen von konfigurieren <xref:System.Windows.Controls.Page.WindowWidth%2A> und <xref:System.Windows.Controls.Page.WindowHeight%2A>bzw.  
  
 <xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A>, und <xref:System.Windows.Controls.Page.WindowHeight%2A> können werden deklarativ in Markup festgelegt, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]  
  
 Das Ergebnis ist in der folgenden Abbildung dargestellt.  
  
 ![Fenstertitel, Höhe, Breite](./media/navigation-overview/window-title-width-height.png "zeigt den Fenstertitel, Höhe und Breite, die Sie konfigurieren können.")  
  
<a name="NavigatingBetweenXAMLPages"></a>   
### <a name="hyperlink-navigation"></a>Linknavigation  
 Eine typische [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] umfasst mehrere Seiten. Die einfachste Möglichkeit, die von einer Seite zur anderen navigieren ist die Verwendung einer <xref:System.Windows.Documents.Hyperlink>. Sie können deklarativ hinzufügen eine <xref:System.Windows.Documents.Hyperlink> auf eine <xref:System.Windows.Controls.Page> mithilfe der `Hyperlink` -Element, das im folgenden Markup angezeigt wird.  
  
 [!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 Ein `Hyperlink` -Element benötigen Sie Folgendes:  
  
-   Das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] von der <xref:System.Windows.Controls.Page> navigieren, gemäß der `NavigateUri` Attribut.  
  
-   Inhalte, die ein Benutzer klicken kann, zum Einleiten der Navigation, wie z. B. Text und Bildern (für den Inhalt, der die `Hyperlink` -Element enthalten kann, finden Sie unter <xref:System.Windows.Documents.Hyperlink>).  
  
 Die folgende Abbildung zeigt ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] mit einem <xref:System.Windows.Controls.Page> , bei dem ein <xref:System.Windows.Documents.Hyperlink>.  
  
 ![Seite mit Link](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "eine XBAP mit einer Seite mit einem Link angezeigt.")  
  
 Wie zu erwarten ist, klicken auf die <xref:System.Windows.Documents.Hyperlink> bewirkt, dass die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] zu navigieren die <xref:System.Windows.Controls.Page> , die durch gekennzeichnet ist die `NavigateUri` Attribut. Darüber hinaus die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Fügt einen Eintrag für die vorherige <xref:System.Windows.Controls.Page> der Liste zuletzt besuchte Seiten in [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. Das wird in der folgenden Abbildung gezeigt.  
  
 ![Zurück- und Vorwärts-Schaltflächen](./media/navigation-overview/back-and-forward-navigation.png "navigieren, mit der zurück- und Vorwärts-Schaltfläche.")  
  
 Zusätzlich zur Unterstützung der Navigation von einem <xref:System.Windows.Controls.Page> zu einem anderen <xref:System.Windows.Documents.Hyperlink> auch der FragmentNavigation unterstützt.  
  
<a name="FragmentNavigation"></a>   
### <a name="fragment-navigation"></a>Fragmentnavigation  
 *FragmentNavigation* ist die Navigation zu einem Inhaltsfragment entweder in die aktuelle <xref:System.Windows.Controls.Page> oder einem anderen <xref:System.Windows.Controls.Page>. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], einem Inhaltsfragment ist der Inhalt, der von einem benannten Element enthalten ist. Ein benanntes Element ist ein Element mit der `Name` -Attribut festgelegt. Das folgende Markup zeigt eine benannte `TextBlock` -Element, das ein Inhaltsfragment enthält.  
  
 [!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]  
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]  
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]  
  
 Für eine <xref:System.Windows.Documents.Hyperlink> zu einem Inhaltsfragment navigieren die `NavigateUri` Attribut muss Folgendes umfassen:  
  
-   Die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] von der <xref:System.Windows.Controls.Page> mit dem Inhaltsfragment, zu navigieren.  
  
-   Ein „#“-Zeichen.  
  
-   Der Name des Elements in der <xref:System.Windows.Controls.Page> , die das Inhaltsfragment enthält.  
  
 Ein Fragment [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] weist Folgendes Format auf.  
  
 *SeitenURI* `#` *Elementname*  
  
 Das folgende Beispiel zeigt ein Beispiel für eine `Hyperlink` , navigieren Sie zu einem Inhaltsfragment konfiguriert ist.  
  
 [!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]  
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]  
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]  
  
> [!NOTE]
>  In diesem Abschnitt wird beschrieben, die standardmäßige Implementierung der FragmentNavigation in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Außerdem können Sie Ihr eigenes Fragmentnavigationsschema implementieren, das teilweise die Behandlung erfordert die <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType> Ereignis.  
  
> [!IMPORTANT]
>  Sie können die Navigieren zu Fragmenten in loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seiten (nur-Markup- [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateien mit `Page` als Stammelement) nur dann, wenn die Seiten über durchsucht werden können [!INCLUDE[TLA2#tla_http](../../../../includes/tla2sharptla-http-md.md)].  
>   
>  Allerdings eine loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite zu den eigenen Fragmenten navigieren kann.  
  
<a name="NavigationService"></a>   
### <a name="navigation-service"></a>Navigationdienst  
 Während <xref:System.Windows.Documents.Hyperlink> ermöglicht es einem Benutzer zur Einleitung der Navigation zu einem bestimmten <xref:System.Windows.Controls.Page>, die Arbeit suchen und Herunterladen der Seite erfolgt durch die <xref:System.Windows.Navigation.NavigationService> Klasse. Im Wesentlichen <xref:System.Windows.Navigation.NavigationService> bietet die Möglichkeit, eine navigationsanforderung im Namen eine Clientcodes, zu verarbeiten, z.B. die <xref:System.Windows.Documents.Hyperlink>. Darüber hinaus <xref:System.Windows.Navigation.NavigationService> Unterstützung auf höherer Ebene zum Nachverfolgen und beeinflussen einer navigationsanforderung implementiert.  
  
 Wenn eine <xref:System.Windows.Documents.Hyperlink> geklickt wird, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Aufrufe <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> finden und Herunterladen der <xref:System.Windows.Controls.Page> unter dem angegebenen Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. Die heruntergeladene <xref:System.Windows.Controls.Page> wird konvertiert in eine Struktur von Objekten, deren Stammobjekt eine Instanz der heruntergeladenen <xref:System.Windows.Controls.Page>. Ein Verweis auf den Stamm <xref:System.Windows.Controls.Page> Objekt befindet sich in der <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType> Eigenschaft. Das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für der Inhalt, zu dem navigiert wurde, die in gespeichert ist die <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> -Eigenschaft, während die <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> speichert das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die letzte Seite, zu dem navigiert wurde.  
  
> [!NOTE]
>  Es ist möglich, dass eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung mehr als eine aktive <xref:System.Windows.Navigation.NavigationService>. Weitere Informationen finden Sie unter [Navigationshosts](#Navigation_Hosts) weiter unten in diesem Thema.  
  
<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>   
### <a name="programmatic-navigation-with-the-navigation-service"></a>Programmgesteuerte Navigation mit dem Navigationsdienst  
 Sie müssen nicht wissen <xref:System.Windows.Navigation.NavigationService> Wenn Navigation deklarativ im Markup implementiert ist <xref:System.Windows.Documents.Hyperlink>, da <xref:System.Windows.Documents.Hyperlink> verwendet die <xref:System.Windows.Navigation.NavigationService> in Ihrem Namen. Dies bedeutet, dass, solange entweder das direkte oder indirekte übergeordnete Element des eine <xref:System.Windows.Documents.Hyperlink> ein Navigationshost ist (finden Sie unter [Navigationshosts](#Navigation_Hosts)), <xref:System.Windows.Documents.Hyperlink> suchen und Verwenden von Navigationsdienst des Navigationshosts verarbeiten können eine navigationsanforderung.  
  
 Es gibt jedoch Situationen, wenn Sie verwenden müssen <xref:System.Windows.Navigation.NavigationService> direkt darunter die folgenden:  
  
-   Wenn Sie instanziieren müssen eine <xref:System.Windows.Controls.Page> mit einem nicht standardmäßigen Konstruktor.  
  
-   Wenn Sie Eigenschaften für festlegen, müssen die <xref:System.Windows.Controls.Page> , bevor Sie dorthin navigieren.  
  
-   Wenn die <xref:System.Windows.Controls.Page> , zu der navigiert werden nur zur Laufzeit bestimmt werden können muss.  
  
 In diesen Fällen müssen Sie Code schreiben, um die Navigation programmgesteuert durch den Aufruf zu initiieren der <xref:System.Windows.Navigation.NavigationService.Navigate%2A> Methode der <xref:System.Windows.Navigation.NavigationService> Objekt. Abrufen eines Verweises auf erfordert eine <xref:System.Windows.Navigation.NavigationService>.  
  
#### <a name="getting-a-reference-to-the-navigationservice"></a>Abrufen eines Verweises auf NavigationService  
 Aus Gründen, die in behandelt werden die [Navigationshosts](#Navigation_Hosts) Abschnitt eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung kann über mehrere verfügen <xref:System.Windows.Navigation.NavigationService>. Dies bedeutet, dass Ihr Code eine Möglichkeit zum Suchen müsste einer <xref:System.Windows.Navigation.NavigationService>, ist in der Regel die <xref:System.Windows.Navigation.NavigationService> , die mit dem aktuellen navigiert <xref:System.Windows.Controls.Page>. Sie erhalten einen Verweis auf eine <xref:System.Windows.Navigation.NavigationService> durch Aufrufen der `static`<xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType> Methode. Zum Abrufen der <xref:System.Windows.Navigation.NavigationService> , die navigiert zu einem bestimmten <xref:System.Windows.Controls.Page>, übergeben Sie einen Verweis auf die <xref:System.Windows.Controls.Page> als Argument der <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A> Methode. Der folgende Code zeigt, wie Sie erhalten die <xref:System.Windows.Navigation.NavigationService> für die aktuelle <xref:System.Windows.Controls.Page>.  
  
 [!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]  
  
 Als Verknüpfung zum Auffinden der <xref:System.Windows.Navigation.NavigationService> für eine <xref:System.Windows.Controls.Page>, <xref:System.Windows.Controls.Page> implementiert die <xref:System.Windows.Controls.Page.NavigationService%2A> Eigenschaft. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]  
  
> [!NOTE]
>  Ein <xref:System.Windows.Controls.Page> erhalten Sie nur einen Verweis auf die <xref:System.Windows.Navigation.NavigationService> beim <xref:System.Windows.Controls.Page> löst die <xref:System.Windows.FrameworkElement.Loaded> Ereignis.  
  
#### <a name="programmatic-navigation-to-a-page-object"></a>Programmgesteuerte Navigation zu einem Seitenobjekt  
 Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Navigation.NavigationService> zur programmgesteuerten Navigation zu einem <xref:System.Windows.Controls.Page>. Programmgesteuerte Navigation wird benötigt, da die <xref:System.Windows.Controls.Page> d. h., zu dem navigiert kann nur instanziiert werden mit einem einzelnen, nicht standardmäßigen Konstruktor. Die <xref:System.Windows.Controls.Page> mit dem nicht standardmäßigen Konstruktor wird in der folgenden Markup und Code gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
 [!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]  
  
 Die <xref:System.Windows.Controls.Page> , die navigiert zu der <xref:System.Windows.Controls.Page> mit dem nicht standardmäßigen Konstruktor wird in der folgenden Markup und Code gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]  
  
 Wenn die <xref:System.Windows.Documents.Hyperlink> dazu <xref:System.Windows.Controls.Page> ist geklickt, Navigation durch Instanziieren initiiert die <xref:System.Windows.Controls.Page> navigieren, indem der nicht standardmäßigen Konstruktor und die <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> Methode. <xref:System.Windows.Navigation.NavigationService.Navigate%2A> akzeptiert einen Verweis auf das Objekt, das die <xref:System.Windows.Navigation.NavigationService> navigiert, anstatt ein Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
#### <a name="programmatic-navigation-with-a-pack-uri"></a>Programmgesteuerte Navigation mit einem Paket-URI  
 Wenn Sie einen Paket-erstellen müssen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] programmgesteuert (Wenn Sie nur das Pack bestimmen können [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] zur Laufzeit, z. B.), können Sie die <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> Methode. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]  
  
#### <a name="refreshing-the-current-page"></a>Aktualisieren der aktuellen Seite  
 Ein <xref:System.Windows.Controls.Page> wird nicht heruntergeladen werden, wenn sie das gleiche Pack verfügt [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] als Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , befindet sich in der <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> Eigenschaft. Um zu erzwingen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] um die aktuelle Seite erneut herunterzuladen, rufen Sie die <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> Methode, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
 [!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]  
  
<a name="Navigation_Lifetime"></a>   
### <a name="navigation-lifetime"></a>Navigationslebensdauer  
 Wie Sie sehen, gibt es viele Möglichkeiten zum Einleiten der Navigation. Wenn die Navigation initiiert, und während der Navigation noch ausgeführt wird, können Sie nachverfolgen und beeinflussen die Navigation mit den folgenden Ereignissen, die von implementiert werden <xref:System.Windows.Navigation.NavigationService>:  
  
-   <xref:System.Windows.Navigation.NavigationService.Navigating>sein. Tritt ein, wenn eine neue Navigation angefordert wird. Kann zum Abbrechen der Navigation verwendet werden.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationProgress>sein. Tritt regelmäßig während eines Downloadvorgangs auf, um Informationen zum Navigationsstatus bereitzustellen.  
  
-   <xref:System.Windows.Navigation.NavigationService.Navigated>sein. Tritt ein, nachdem die Seite gefunden und heruntergeladen wurde.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationStopped>sein. Tritt auf, wenn die Navigation beendet wird (durch Aufrufen von <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>), oder wenn eine neue Navigation angefordert wird, während eine aktuelle Navigation noch ausgeführt wird.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationFailed>sein. Tritt ein, wenn ein Fehler ausgelöst wird, während zum angeforderten Inhalt navigiert wird.  
  
-   <xref:System.Windows.Navigation.NavigationService.LoadCompleted>sein. Tritt ein, wenn der Inhalt, zu dem navigiert wurde, geladen und analysiert wird und mit dem Rendering begonnen wurde.  
  
-   <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>sein. Tritt ein, wenn die Navigation zu einem Inhaltsfragment beginnt, was in folgenden Fällen geschieht:  
  
    -   Sofort, falls sich das gewünschte Fragment im aktuellen Inhalt befindet.  
  
    -   Nachdem der Inhalt der Quelldatei geladen wurde und sich das gewünschte Fragment in einem anderen Inhalt befindet.  
  
 Die Navigationsereignisse werden in der Reihenfolge ausgelöst, die in der folgenden Abbildung dargestellt wird.  
  
 ![Seitennavigations-Flussdiagramm](./media/navigation-overview/order-of-navigation-events.png "Seitennavigations-Flussdiagramm-Ereignis")  
  
 Im Allgemeinen eine <xref:System.Windows.Controls.Page> ist nicht auf diese Ereignisse sorgen. Es ist wahrscheinlicher, dass eine Anwendung mit ihnen befasst und aus diesem Grund werden diese Ereignisse auch von ausgelöst der <xref:System.Windows.Application> Klasse:  
  
-   <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>  
  
 Jedes Mal, wenn <xref:System.Windows.Navigation.NavigationService> löst ein Ereignis aus, die <xref:System.Windows.Application> Klasse löst das entsprechende Ereignis aus. <xref:System.Windows.Controls.Frame> und <xref:System.Windows.Navigation.NavigationWindow> bieten dieselben Ereignisse, um die Navigation in ihren jeweiligen Gültigkeitsbereichen erkannt.  
  
 In einigen Fällen eine <xref:System.Windows.Controls.Page> ist ggf. daran interessiert, in diesen Ereignissen. Z. B. eine <xref:System.Windows.Controls.Page> übernimmt die <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> Ereignis, um zu bestimmen, ob Sie die Navigation von. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]  
  
 Wenn Sie einen Handler für ein Navigationsereignis aus Registrieren einer <xref:System.Windows.Controls.Page>, wie im vorherige Beispiel der Fall ist, müssen Sie auch den Ereignishandler aufheben. Wenn Sie dies nicht tun, besteht möglicherweise Nebenwirkungen in Bezug auf wie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Navigation speichert <xref:System.Windows.Controls.Page> -Navigation mithilfe des Journals.  
  
<a name="NavigationHistory"></a>   
### <a name="remembering-navigation-with-the-journal"></a>Aufzeichnung der Navigation mithilfe des Journals  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verwendet zwei Stapel, um die Seiten, die Sie weg navigiert sind, denken Sie daran: einen BackStack und einen forward-Stapel. Beim Navigieren aus dem aktuellen <xref:System.Windows.Controls.Page> in ein neues <xref:System.Windows.Controls.Page> oder unten, um eine vorhandene <xref:System.Windows.Controls.Page>, die aktuelle <xref:System.Windows.Controls.Page> hinzugefügt wird die *BackStack*. Beim Navigieren aus dem aktuellen <xref:System.Windows.Controls.Page> zurück zur vorherigen <xref:System.Windows.Controls.Page>, die aktuelle <xref:System.Windows.Controls.Page> wird hinzugefügt, um die *Vorwärtsstapel*. Der Rückwärts- und der Vorwärtsstapel sowie die Funktion zum Verwalten der Stapel werden zusammen als das Journal bezeichnet. Jedes Element in der rückwärts- und der Vorwärtsstapel ist eine Instanz von der <xref:System.Windows.Navigation.JournalEntry> Klasse, und wird als bezeichnet ein *Journaleintrag*.  
  
#### <a name="navigating-the-journal-from-internet-explorer"></a>Navigieren im Journal in Internet Explorer  
 Vom Konzept her funktioniert das Journal auf die gleiche Weise der **zurück** und **weiterleiten** mithilfe der Schaltflächen im [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] führen. Diese sind in der folgenden Abbildung dargestellt.  
  
 ![Zurück- und Vorwärts-Schaltflächen](./media/navigation-overview/back-and-forward-navigation.png "navigieren, mit der zurück- und Vorwärts-Schaltfläche.")  
  
 Für [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] die gehostet werden, indem [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integriert die Erfassung in der Navigation [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. Dadurch können Benutzer Seiten navigieren ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] mithilfe der **wieder**, **weiterleiten**, und **zuletzt besuchte Seiten** mithilfe der Schaltflächen im [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. Die Erfassung nicht integriert ist [!INCLUDE[TLA2#tla_ie6](../../../../includes/tla2sharptla-ie6-md.md)] auf die gleiche Weise für [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] oder Internet Explorer 8. Stattdessen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] rendert eine Ersatznavigations- [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
> [!IMPORTANT]
>  In [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], wenn ein Benutzer weg navigiert und an eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], nur die Journaleinträge für Seiten, die nicht aktiv beibehalten wurden, werden im Journal beibehalten. Erläuterung, wie Sie Seiten beibehalten, finden Sie unter [Seitenlebensdauer und das Journal](#PageLifetime) weiter unten in diesem Thema.  
  
 Standardmäßig wird der Text für die einzelnen <xref:System.Windows.Controls.Page> , angezeigt wird, der **zuletzt besuchte Seiten** Liste der [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] ist die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die <xref:System.Windows.Controls.Page>. In vielen Fällen ist das für den Benutzer nicht besonders sinnvoll. Sie können den Text jedoch mithilfe einer der folgenden Optionen ändern:  
  
1.  Der angefügte `JournalEntry.Name` Attributwert.  
  
2.  Die `Page.Title` Attributwert.  
  
3.  Die `Page.WindowTitle` -Attributwert und dem [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die aktuelle <xref:System.Windows.Controls.Page>.  
  
4.  Der [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die aktuelle <xref:System.Windows.Controls.Page>. (Standard)  
  
 Die Reihenfolge, in der die Optionen aufgeführt sind, entspricht der Rangfolge zum Suchen von Text. Z. B. wenn `JournalEntry.Name` festgelegt ist, werden die anderen Werte ignoriert.  
  
 Im folgenden Beispiel wird die `Page.Title` Attribut zum Ändern des Texts, der für einen Journaleintrag angezeigt wird.  
  
 [!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]  
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]  
  
 [!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
 [!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]  
  
#### <a name="navigating-the-journal-using-wpf"></a>Navigieren im Journal mit WPF  
 Auch wenn ein Benutzer im Journal navigieren kann die **wieder**, **Vorwärts**, und **zuletzt besuchte Seiten** in [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], Sie können auch die Erfassung, Verwendung beider navigieren deklarativ und programmatisch Mechanismus von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Ein Grund dafür ist, benutzerdefinierte Navigations-bereitstellen [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] in Ihren Seiten.  
  
 Sie können die Unterstützung der Journalnavigation deklarativ hinzufügen, mit den Navigationsbefehlen verfügbar gemacht werden, indem <xref:System.Windows.Input.NavigationCommands>. Im folgenden Beispiel wird veranschaulicht, wie die `BrowseBack` Navigationsbefehl.  
  
 [!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]  
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]  
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]  
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]  
  
 Sie können programmgesteuert im Journal navigieren, mit einer der folgenden Elemente von der <xref:System.Windows.Navigation.NavigationService> Klasse:  
  
-   <xref:System.Windows.Navigation.NavigationService.GoBack%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.GoForward%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>  
  
 Das Journal kann auch programmgesteuert geändert werden, wie unter [beibehalten des Inhaltszustands über den Navigationsverlauf](#RetainingContentStateWithNavigationHistory) weiter unten in diesem Thema.  
  
<a name="PageLifetime"></a>   
### <a name="page-lifetime-and-the-journal"></a>Seitenlebensdauer und das Journal  
 Erwägen Sie eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] mit verschiedenen Seiten, die umfangreiche Inhalte, einschließlich Grafiken, Animationen und Medien. Die Speicherbeanspruchung für Seiten wie diese könnte recht groß sein, insbesondere, wenn Video- und Audiomedien verwendet werden. Angesichts der Tatsache, dass das Journal Seiten, die navigiert, z. B. wurden "speichert" eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] konnte schnell eine beträchtlichen Menge an Arbeitsspeicher belegen.  
  
 Aus diesem Grund ist das Standardverhalten des Journals zum Speichern von <xref:System.Windows.Controls.Page> Metadaten in jedem Journaleintrag, anstatt einen Verweis auf eine <xref:System.Windows.Controls.Page> Objekt. Wenn zu einem Journaleintrag navigiert wird, dessen <xref:System.Windows.Controls.Page> Metadaten wird verwendet, um eine neue Instanz des angegebenen <xref:System.Windows.Controls.Page>. Infolgedessen wird jede <xref:System.Windows.Controls.Page> navigiert wird, die in der folgenden Abbildung dargestellte Lebensdauer hat.  
  
 ![Seitenlebensdauer](./media/navigation-overview/navigated-page-lifetime.png "zeigt die Lebensdauer, wenn eine Seite navigiert wird.")  
  
 Auch mithilfe der Journaling-Standardverhalten zum Arbeitsspeicherverbrauch speichern kann, kann die Leistung beim Rendern der pro Seite beeinträchtigt werden; umfangreichem eine <xref:System.Windows.Controls.Page> kann sehr zeitaufwendig, insbesondere, wenn sie viel Inhalt hat sein. Wenn Sie beibehalten müssen eine <xref:System.Windows.Controls.Page> Instanz im Journal, können Sie auf zwei Techniken dafür zeichnen. Erstens können Sie programmgesteuert zu navigieren eine <xref:System.Windows.Controls.Page> -Objekt durch Aufrufen der <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> Methode.  
  
 Zweitens können Sie angeben, die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eine Instanz von einer <xref:System.Windows.Controls.Page> im Journal durch Festlegen der <xref:System.Windows.Controls.Page.KeepAlive%2A> Eigenschaft, um `true` (der Standardwert ist `false`). Wie im folgenden Beispiel gezeigt wird, können Sie festlegen <xref:System.Windows.Controls.Page.KeepAlive%2A> deklarativ in Markup.  
  
 [!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]  
  
 Die Lebensdauer einer <xref:System.Windows.Controls.Page> , aktiv beibehalten unterscheidet sich leicht von einer nicht. Beim ersten ein <xref:System.Windows.Controls.Page> , bleibt aktiv navigiert wird, ist er instanziiert, wie eine <xref:System.Windows.Controls.Page> , die nicht aktiv beibehalten. Aber da eine Instanz von der <xref:System.Windows.Controls.Page> beibehalten im Journal, es ist nicht mehr instanziiert für solange sie in der Erfassung ist. Daher, wenn eine <xref:System.Windows.Controls.Page> Initialisierungslogik, die jedes Mal aufgerufen werden muss, hat die <xref:System.Windows.Controls.Page> navigiert wird, Sie sollten es aus dem Konstruktor in verschieben einen Handler für die <xref:System.Windows.FrameworkElement.Loaded> Ereignis. Wie in der folgenden Abbildung dargestellt die <xref:System.Windows.FrameworkElement.Loaded> und <xref:System.Windows.FrameworkElement.Unloaded> Ereignisse sind immer noch jedes Mal ausgelöst, eine <xref:System.Windows.Controls.Page> navigiert wird und jeweils.  
  
 ![Wenn die Loaded- und Unloaded-Ereignisse ausgelöst werden](./media/navigation-overview/loaded-and-unloaded-events.png "geladen und entladen Ereignisse werden ausgelöst, wenn eine Seite in und aus navigiert wird.")  
  
 Wenn eine <xref:System.Windows.Controls.Page> ist nicht aktiv beibehalten, Sie sollten nicht eines der folgenden:  
  
-   Speichern eines Verweises auf die Seite oder einen Teil der Seite  
  
-   Registrieren von Ereignishandlern für Ereignisse, die nicht von ihr implementiert werden  
  
 Jedem dieser Schritte werden Verweise, die erzwingen, erstellt die <xref:System.Windows.Controls.Page> im Arbeitsspeicher beibehalten werden sollen, auch nachdem sie aus dem Journal entfernt wurde.  
  
 Im Allgemeinen sollten Sie die Standardeinstellung bevorzugen <xref:System.Windows.Controls.Page> Verhalten nicht halten ein <xref:System.Windows.Controls.Page> aktiv. Dies zieht jedoch Auswirkungen auf den Zustand nach sich, die im nächsten Abschnitt erörtert werden.  
  
<a name="RetainingContentStateWithNavigationHistory"></a>   
### <a name="retaining-content-state-with-navigation-history"></a>Beibehalten des Inhaltszustands über den Navigationsverlauf  
 Wenn eine <xref:System.Windows.Controls.Page> nicht beibehalten, und es enthält Steuerelemente, die Datensammlung für den Benutzer, was geschieht mit den Daten, wenn ein Benutzer weg navigiert und dann wieder auf die <xref:System.Windows.Controls.Page>? Aus Gründen der Benutzererfahrung sollte der Benutzer erwarten, dass die zuvor eingegebenen Daten angezeigt werden. Leider, da eine neue Instanz der dem <xref:System.Windows.Controls.Page> wird erstellt, mit jeder Navigation, die den Steuerelementen, die gesammelten Daten sind jedoch neu instanziiert und die Daten gehen verloren.  
  
 Glücklicherweise stellt das Journal Unterstützung für das Speichern von Daten über <xref:System.Windows.Controls.Page> Navigationen hinweg, einschließlich Steuerelementdaten. Insbesondere der Journaleintrag für jede <xref:System.Windows.Controls.Page> fungiert als temporärer Container für das zugeordnete <xref:System.Windows.Controls.Page> Zustand. Die folgenden Schritte beschreiben, wie diese Unterstützung verwendet wird bei einem <xref:System.Windows.Controls.Page> von navigiert wird:  
  
1.  Ein Eintrag für den aktuellen <xref:System.Windows.Controls.Page> das Journal hinzugefügt wird.  
  
2.  Den Status der <xref:System.Windows.Controls.Page> wird gespeichert, mit dem Journaleintrag für diese Seite, die dem Rückwärtsstapel hinzugefügt wird.  
  
3.  Die neue <xref:System.Windows.Controls.Page> navigiert wird.  
  
 Wenn die Seite <xref:System.Windows.Controls.Page> ist zum zurück navigiert, mithilfe des Journals die folgenden Schritte erfolgen:  
  
1.  Die <xref:System.Windows.Controls.Page> (der oberste Journaleintrag im Rückwärtsstapel) instanziiert wird.  
  
2.  Die <xref:System.Windows.Controls.Page> wird mit dem Zustand, der mit dem Journaleintrag für gespeichert wurde, aktualisiert der <xref:System.Windows.Controls.Page>.  
  
3.  Die <xref:System.Windows.Controls.Page> an navigiert wird.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verwendet diese Unterstützung automatisch, wenn die folgenden Steuerelemente verwendet werden, auf eine <xref:System.Windows.Controls.Page>:  
  
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
  
 Wenn eine <xref:System.Windows.Controls.Page> diese Steuerelemente verwendet, in diese eingegebenen Daten über gespeichert <xref:System.Windows.Controls.Page> -Navigationen hinweg, wie die **Lieblingsfarbe** <xref:System.Windows.Controls.ListBox> in der folgenden Abbildung.  
  
 ![Seite mit Steuerelementen, die Zustand speichern](./media/navigation-overview/data-remembered-across-page-navigations.png "eingegebene Daten über Seite Navigationen hinweg gespeichert.")  
  
 Wenn eine <xref:System.Windows.Controls.Page> verfügt über Steuerelemente, die in der obigen Liste nicht, oder wenn der Zustand in benutzerdefinierten Objekten gespeichert wird, müssen Sie Code schreiben, um das Journal den Zustand über <xref:System.Windows.Controls.Page> Navigationen hinweg.  
  
 Wenn Sie kleinere Mengen der Zustandsinformationen über sich merken müssen <xref:System.Windows.Controls.Page> -Navigationen hinweg, können Sie Abhängigkeitseigenschaften (finden Sie unter <xref:System.Windows.DependencyProperty>) konfiguriert sind die <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> Metadatenflag.  
  
 Wenn der Status, die Ihre <xref:System.Windows.Controls.Page> muss über Navigationen hinweg speichert besteht aus mehreren Datenmengen, ist es weniger Code intensive Kapseln Ihres Zustands in einer einzelnen Klasse und Implementieren der <xref:System.Windows.Navigation.IProvideCustomContentState> Schnittstelle.  
  
 Wenn Sie durch verschiedene Zustände einer einzelnen navigieren müssen <xref:System.Windows.Controls.Page>, ohne die Navigation von der <xref:System.Windows.Controls.Page> selbst, können Sie <xref:System.Windows.Navigation.IProvideCustomContentState> und <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType>.  
  
<a name="Cookies"></a>   
### <a name="cookies"></a>Cookies  
 Eine andere Weise [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen können Daten speichern, ist mit Cookies, die erstellt werden, aktualisiert und gelöscht werden, mithilfe der <xref:System.Windows.Application.SetCookie%2A> und <xref:System.Windows.Application.GetCookie%2A> Methoden. Die Cookies, die Sie in erstellen können, die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sind den Cookies identisch, dass andere Arten von Webanwendungen verwenden; Cookies bestehen aus willkürlichen Daten, die von einer Anwendung auf einem Clientcomputer entweder während oder über anwendungssitzungen gespeichert sind. Cookiedaten weisen meist das folgende Format eines Name-Wert-Paares auf.  
  
 *Name* `=` *Wert*  
  
 Wenn die Daten an übergeben <xref:System.Windows.Application.SetCookie%2A>, zusammen mit den <xref:System.Uri> des Speicherorts für den das Cookie festgelegt werden soll, ein Cookie speicherintern erstellt wird, und es ist nur für die Dauer der aktuellen Sitzung verfügbar. Diese Art von Cookies wird als bezeichnet ein *Sitzungscookie*.  
  
 Wenn Sie ein Cookie über Anwendungssitzungen speichern möchten, muss dem Cookie unter Verwendung des folgenden Formats ein Ablaufdatum hinzugefügt werden.  
  
 *NAMEN* `=` *WERT* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`  
  
 Ein Cookie mit einem Ablaufdatum wird gespeichert, in der aktuellen [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] -Installation temporäre Internetdateien bis zum Ablauf der Cookies. Als solches Cookie bezeichnet ein *dauerhaftes Cookie* , da es über anwendungssitzungen erhalten bleibt.  
  
 Sie sitzungsbasierte und beständige Cookies durch den Aufruf Abrufen der <xref:System.Windows.Application.GetCookie%2A> Methode auf und übergibt die <xref:System.Uri> des Speicherorts, in dem das Cookie festgelegt wurde, mit, der <xref:System.Windows.Application.SetCookie%2A> Methode.  
  
 Im folgenden sind einige der Methoden, mit denen Cookies, in unterstützt werden [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]:  
  
-   [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eigenständige Anwendungen und [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] können beide erstellen und Verwalten von Cookies.  
  
-   Cookies, die vom erstellten ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] vom Browser zugegriffen werden kann.  
  
-   [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] aus die gleiche Domäne erstellen und Freigeben von Cookies.  
  
-   [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] und [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] Seiten aus derselben Domäne erstellen und Freigeben von Cookies.  
  
-   Cookies werden verteilt, wenn [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] und loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Seiten webanforderungen stellen.  
  
-   Sowohl der obersten Ebene [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] und [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] in gehosteten IFRAMES können auf Cookies zugreifen.  
  
-   Unterstützung von Cookies in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] gilt für alle unterstützten Browser.  
  
-   In [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], P3P-Richtlinie, die Cookies betrifft, wird vom berücksichtigt [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], insbesondere in Bezug auf erst- und Drittanbietern [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Structured_Navigation"></a>   
### <a name="structured-navigation"></a>Strukturierte Navigation  
 Wenn Sie Daten aus einer übergeben müssen <xref:System.Windows.Controls.Page> zu einem anderen können Sie die Daten als Argumente übergeben, um einen nicht standardmäßigen Konstruktor von den <xref:System.Windows.Controls.Page>. Beachten Sie, dass wenn Sie dieses Verfahren verwenden, müssen Sie halten die <xref:System.Windows.Controls.Page> aktiv ist; wenn nicht, beim nächsten navigieren Sie zum die <xref:System.Windows.Controls.Page>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] erneut instanziiert die <xref:System.Windows.Controls.Page> mithilfe des Standardkonstruktors.  
  
 Sie können auch Ihre <xref:System.Windows.Controls.Page> können implementieren Eigenschaften, die mit den Daten festgelegt werden, die übergeben werden muss. Kompliziert wird dies jedoch, wenn eine <xref:System.Windows.Controls.Page> benötigt, übergeben Daten zurück an die <xref:System.Windows.Controls.Page> , die dorthin navigiert ist. Das Problem besteht darin, dass die Navigation Mechanismen keine direkte Unterstützung garantieren können, die eine <xref:System.Windows.Controls.Page> an zurückgegeben wird, nachdem es von dem navigiert wird. Im Grunde unterstützt die Navigation keine Semantik mit Aufruf/Rückgabe. Um dieses Problem zu lösen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet die <xref:System.Windows.Navigation.PageFunction%601> -Klasse, die Sie verwenden können, um sicherzustellen, dass eine <xref:System.Windows.Controls.Page> an in einer vorhersehbaren und strukturierten Weise zurückgegeben. Weitere Informationen finden Sie unter [Übersicht über die strukturierte Navigation](structured-navigation-overview.md).  
  
<a name="The_NavigationWindow_Class"></a>   
## <a name="the-navigationwindow-class"></a>Die NavigationWindow-Klasse  
 Bis jetzt haben Sie das Spektrum der Navigationsdienste kennengelernt, die Sie zum Erstellen von Anwendungen mit navigierbarem Inhalt normalerweise verwenden werden. Diese Dienste wurden im Kontext des erläutert [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], obwohl sie nicht auf beschränkt sind [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Moderne Betriebssysteme und Windows-Anwendungen nutzen die Browsererfahrung zeitgemäßer Benutzer, um die Navigation im Browserstil in eigenständige Anwendungen integrieren. Gängige Beispiele:  
  
-   **Word-Thesaurus**: Navigieren Sie durch verschiedene.  
  
-   **Datei-Explorer**: Navigieren Sie Dateien und Ordner.  
  
-   **Assistenten**: Untergliedern einer komplexen Aufgabe in mehrere Seiten, zwischen denen navigiert werden kann. Ein Beispiel ist der Assistent für Windows-Komponenten, die hinzufügen und Entfernen von Windows-Funktionen verarbeitet.  
  
 Um die Navigation im Browserstil in Ihre eigenständigen Anwendungen zu integrieren, können Sie die <xref:System.Windows.Navigation.NavigationWindow> Klasse. <xref:System.Windows.Navigation.NavigationWindow> leitet sich von <xref:System.Windows.Window> und bietet die gleiche Unterstützung für die Navigation, die [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] bereitzustellen. Sie können <xref:System.Windows.Navigation.NavigationWindow> als das Hauptfenster der eigenständigen Anwendung oder als sekundäres Fenster, z. B. ein Dialogfeld.  
  
 Implementieren einer <xref:System.Windows.Navigation.NavigationWindow>, wie Sie sich bei den meisten Klassen der obersten Ebene in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] (<xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>und so weiter), Sie verwenden eine Kombination aus Markup und CodeBehind. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]  
  
 [!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
 [!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]  
  
 Dieser Code erstellt eine <xref:System.Windows.Navigation.NavigationWindow> navigiert, die automatisch zu einer <xref:System.Windows.Controls.Page> (HomePage.xaml) Wenn die <xref:System.Windows.Navigation.NavigationWindow> wird geöffnet. Wenn die <xref:System.Windows.Navigation.NavigationWindow> ist das Hauptanwendungsfenster, können Sie die `StartupUri` Attribut, um ihn zu starten. Dies wird im folgenden Markup gezeigt.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]  
  
 Die folgende Abbildung zeigt die <xref:System.Windows.Navigation.NavigationWindow> als Hauptanwendungsfenster einer eigenständigen Anwendung.  
  
 ![Ein Hauptfenster](./media/navigation-overview/navigation-window-as-main-window.png "Navigationsfenster als Hauptfenster")  
  
 In der Abbildung können Sie sehen, die die <xref:System.Windows.Navigation.NavigationWindow> einen Titel hat, obwohl dies nicht, in festgelegt wurde der <xref:System.Windows.Navigation.NavigationWindow> Implementierungscode aus dem vorherigen Beispiel. Stattdessen wird der Titel mit festgelegt die <xref:System.Windows.Controls.Page.WindowTitle%2A> -Eigenschaft, die in den folgenden Code gezeigt wird.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]  
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]  
  
 Festlegen der <xref:System.Windows.Controls.Page.WindowWidth%2A> und <xref:System.Windows.Controls.Page.WindowHeight%2A> Eigenschaften wirkt sich auch auf die <xref:System.Windows.Navigation.NavigationWindow>.  
  
 In der Regel implementieren Sie Ihr eigenes <xref:System.Windows.Navigation.NavigationWindow> Wenn Sie entweder das Verhalten oder die Anzeige anpassen müssen. Wenn keines von beiden angepasst werden muss, können Sie eine Verknüpfung verwenden. Wenn Sie das Pack angeben [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] von einer <xref:System.Windows.Controls.Page> als die <xref:System.Windows.Application.StartupUri%2A> in einer eigenständigen Anwendung, <xref:System.Windows.Application> erstellt automatisch eine <xref:System.Windows.Navigation.NavigationWindow> auf Host der <xref:System.Windows.Controls.Page>. Im folgenden Markup wird gezeigt, wie Sie das aktivieren.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]  
  
 Wenn Sie ein sekundäres Anwendungsfenster, z. B. ein Dialogfeld sein möchten eine <xref:System.Windows.Navigation.NavigationWindow>, Sie können den Code im folgenden Beispiel verwenden, um ihn zu öffnen.  
  
 [!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
 [!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]  
  
 Die folgende Abbildung zeigt das Ergebnis.  
  
 ![Ein Dialogfeld](./media/navigation-overview/navigation-window-as-dialog-box.png "Navigationsfenster als Dialogfeld")  
  
 Wie Sie sehen können, <xref:System.Windows.Navigation.NavigationWindow> zeigt [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]-Stil **wieder** und **Vorwärts** Schaltflächen, die Benutzer im Journal navigieren können. Wie in der folgenden Abbildung veranschaulicht, bieten diese Schaltflächen dieselbe Benutzererfahrung.  
  
 ![Zurück- und Vorwärts-Schaltflächen in einem NavigationWindow](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "zurück- und Vorwärts-Schaltflächen in einem Navigationsfenster")  
  
 Wenn Ihre Seiten eigene navigationsunterstützung für Journal und Benutzeroberfläche bereitstellen, können Sie Ausblenden der **zurück** und **weiterleiten** Schaltflächen angezeigt werden, indem <xref:System.Windows.Navigation.NavigationWindow> durch Festlegen des Werts von der <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> Eigenschaft `false`.  
  
 Alternativ können Sie die Unterstützung der Anpassung in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ersetzen die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von der <xref:System.Windows.Navigation.NavigationWindow> selbst.  
  
<a name="Frame_in_Standalone_Applications"></a>   
## <a name="the-frame-class"></a>Die Frame-Klasse  
 Sowohl Browser und <xref:System.Windows.Navigation.NavigationWindow> sind Fenster, die navigierbaren Inhalt hosten. In einigen Fällen verfügen Anwendungen über Inhalt, der nicht von einem ganzen Fenster gehostet werden muss. Stattdessen kann solcher Inhalt in anderem Inhalt gehostet werden. Sie können navigierbaren Inhalt in anderen Inhalt einfügen, mit der <xref:System.Windows.Controls.Frame> Klasse. <xref:System.Windows.Controls.Frame> bietet dieselbe Unterstützung wie <xref:System.Windows.Navigation.NavigationWindow> und [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
 Das folgende Beispiel veranschaulicht das Hinzufügen einer <xref:System.Windows.Controls.Frame> auf eine <xref:System.Windows.Controls.Page> deklarativ mithilfe der `Frame` Element.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]  
  
 Dieses Markup wird der `Source` Attribut der `Frame` Element mit einem Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die <xref:System.Windows.Controls.Page> , die <xref:System.Windows.Controls.Frame> zunächst navigieren sollte. Die folgende Abbildung zeigt ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] mit einem <xref:System.Windows.Controls.Page> , bei dem ein <xref:System.Windows.Controls.Frame> , die zwischen mehreren Seiten navigiert ist.  
  
 ![Ein Frame, der zwischen mehreren Seiten navigiert](./media/navigation-overview/frame-navigation-between-multiple-pages.png "zeigt eine Frame-Navigation zwischen mehreren Seiten.")  
  
 Müssen Sie nicht nur mit <xref:System.Windows.Controls.Frame> innerhalb des Inhalts von einem <xref:System.Windows.Controls.Page>. Es ist auch üblich, zum Hosten einer <xref:System.Windows.Controls.Frame> innerhalb des Inhalts von einer <xref:System.Windows.Window>.  
  
 In der Standardeinstellung <xref:System.Windows.Controls.Frame> nur sein eigenes Journal verwendet, in dem kein anderes. Wenn eine <xref:System.Windows.Controls.Frame> ist Teil des Inhalts, der weder gehostet wird eine <xref:System.Windows.Navigation.NavigationWindow> oder [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], <xref:System.Windows.Controls.Frame> verwendet das Journal, zu dem gehört die <xref:System.Windows.Navigation.NavigationWindow> oder [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. In einigen Fällen jedoch eine <xref:System.Windows.Controls.Frame> muss unter Umständen für das eigene Journal zuständig sein. Ein Grund dafür ist Navigation mithilfe des Journals innerhalb der Seiten zu ermöglichen, die von gehosteten eine <xref:System.Windows.Controls.Frame>. Dies wird in der folgenden Abbildung verdeutlicht.  
  
 ![Frame- und Seiten-Diagramm](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "Navigation mithilfe des Journals innerhalb von einem Frame gehostete Seiten zeigt.")  
  
 In diesem Fall können Sie konfigurieren die <xref:System.Windows.Controls.Frame> auf sein eigenes Journal verwendet, durch Festlegen der <xref:System.Windows.Controls.Frame.JournalOwnership%2A> Eigenschaft der <xref:System.Windows.Controls.Frame> zu <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>. Dies wird im folgenden Markup gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]  
  
 Die folgende Abbildung zeigt die Auswirkung der Navigation in einem <xref:System.Windows.Controls.Frame> , sein eigenes Journal verwendet.  
  
 ![Ein Frame, der sein eigenes Journal verwendet](./media/navigation-overview/frame-uses-its-own-journal.png "Dies zeigt die Auswirkung der Navigation innerhalb eines Rahmens, der sein eigenes Journal verwendet.")  
  
 Beachten Sie, die die Journaleinträge, von der Navigations-angezeigt werden [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in die <xref:System.Windows.Controls.Frame>, sondern nach [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)].  
  
> [!NOTE]
>  Wenn eine <xref:System.Windows.Controls.Frame> ist Teil des Inhalts, die in gehostet ist eine <xref:System.Windows.Window>, <xref:System.Windows.Controls.Frame> sein eigenes Journal verwendet werden soll, und zeigt folglich die eigene Navigations- [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Wenn Ihre benutzerfreundlichkeit erfordert eine <xref:System.Windows.Controls.Frame> sein eigenes Journal bereitstellen, ohne dass die Navigations- [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], können Sie im Navigationsbereich ausblenden [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] durch Festlegen der <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> zu <xref:System.Windows.Visibility.Hidden>. Dies wird im folgenden Markup gezeigt.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]  
  
<a name="Navigation_Hosts"></a>   
## <a name="navigation-hosts"></a>Navigationshosts  
 <xref:System.Windows.Controls.Frame> und <xref:System.Windows.Navigation.NavigationWindow> sind Klassen, die als Navigationshosts bezeichnet werden. Ein *Navigationshost* ist eine Klasse, navigieren Sie zu und Inhalt anzeigen kann. Um dies zu erreichen, verwendet jeder Navigationshost eigene <xref:System.Windows.Navigation.NavigationService> und Journal. Die grundlegende Konstruktion eines Navigationshosts wird in der folgenden Abbildung gezeigt.  
  
 ![Navigatordiagramme](./media/navigation-overview/navigation-host-construction.png "grundlegende Konstruktion eines Navigationshosts")  
  
 Grundsätzlich werden dadurch <xref:System.Windows.Navigation.NavigationWindow> und <xref:System.Windows.Controls.Frame> Navigation identisch zu unterstützen, die eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] bietet, wenn im Browser gehostet.  
  
 Neben der Verwendung von <xref:System.Windows.Navigation.NavigationService> und einem Journal, implementieren Navigationshosts dieselben Member, die <xref:System.Windows.Navigation.NavigationService> implementiert. Dies wird in der folgenden Abbildung verdeutlicht.  
  
 ![Ein Journal in einem Frame und in einem NavigationWindow](./media/navigation-overview/navigation-window-and-frame.png "Navigationsfenster und Frame")  
  
 Dies ermöglicht es Ihnen, Navigationsunterstützung direkt für sie zu programmieren. Dies in Erwägung, wenn Sie eine benutzerdefinierte Navigation bereitstellen müssen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für eine <xref:System.Windows.Controls.Frame> , befindet sich einem <xref:System.Windows.Window>. Darüber hinaus implementieren beide Typen zusätzliche, navigationsbezogenen-Elemente, einschließlich `BackStack` (<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>) und `ForwardStack` (<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>), mit denen Sie die Journaleinträge im zurück in den aufgelistet werden. Aufrufliste und Vorwärtsstapel.  
  
 Wie bereits erwähnt, können in einer Anwendung mehrere Journale vorhanden sein. Die folgende Abbildung enthält ein Beispiel für die Fälle, in denen das auftreten kann.  
  
 ![Mehrere Journale in einer Anwendung](./media/navigation-overview/multiple-journals-in-one-application.png "Dies ist ein Beispiel für mehrere Journale in einer Anwendung.")  
  
<a name="Navigating_to_Content_Other_than_Pages"></a>   
## <a name="navigating-to-content-other-than-xaml-pages"></a>Navigieren zu anderem Inhalt als XAML-Seiten  
 In diesem Thema <xref:System.Windows.Controls.Page> und Pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] verwendet worden, um die verschiedenen Navigationsfunktionen von veranschaulichen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Allerdings eine <xref:System.Windows.Controls.Page> , kompiliert in eine Anwendung ist nicht die einzige Art von Inhalt, zu der navigiert werden kann, und Pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] sind nicht die einzige Möglichkeit, Inhalte zu identifizieren.  
  
 In diesem Abschnitt wird veranschaulicht, können Sie auch Navigieren zu loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateien [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] Dateien und Objekte.  
  
<a name="Navigating_to_Loose_XAML_Files"></a>   
### <a name="navigating-to-loose-xaml-files"></a>Navigieren zu Loose XAML-Dateien  
 Eine loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei ist eine Datei mit den folgenden Merkmalen:  
  
-   Enthält nur [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (d. h. kein Code).  
  
-   Verfügt über eine entsprechende Namespacedeklaration.  
  
-   Hat die Dateierweiterung .xaml.  
  
 Betrachten Sie beispielsweise den folgenden Inhalt, die als loose gespeichert sind [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei Person.xaml.  
  
 [!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]  
  
 Wenn Sie auf die Datei doppelklicken, wird der Browser geöffnet und navigiert zur Datei und zeigt den Inhalt an. Das wird in der folgenden Abbildung gezeigt.  
  
 ![Anzeige des Inhalts in der Datei Person.XAML](./media/navigation-overview/contents-of-person-xaml-file.png "zeigt den Inhalt der Datei Person.XAML.")  
  
 Sie können eine loose anzeigen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei aus den folgenden:  
  
-   Einer Website auf dem lokalen Computer, dem Intranet oder dem Internet  
  
-   Ein [!INCLUDE[TLA#tla_unc](../../../../includes/tlasharptla-unc-md.md)] -Dateifreigabe.  
  
-   Dem lokalen Datenträger  
  
 Eine loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei kann hinzugefügt werden, zu den Favoriten des Browsers, oder auf der Startseite des Browsers.  
  
> [!NOTE]
>  Weitere Informationen zum Veröffentlichen und Starten von loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seiten finden Sie unter [Bereitstellen von WPF-Anwendungen](deploying-a-wpf-application-wpf.md).  
  
 Eine Einschränkung in Bezug auf lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] besteht darin, dass nur Inhalt gehostet werden können, die sich sicher bei teilweiser Vertrauenswürdigkeit ausgeführt werden kann. Z. B. `Window` nicht das Stammelement einer Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../wpf-partial-trust-security.md).  
  
<a name="Navigating_to_HTML_Files_Using_Frame"></a>   
### <a name="navigating-to-html-files-by-using-frame"></a>Navigieren zu HTML-Dateien mit Frame  
 Wie zu erwarten, können Sie auch zu navigieren [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]. Sie müssen lediglich angeben einer [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , die das HTTP-Schema verwendet. Beispielsweise die folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zeigt eine <xref:System.Windows.Controls.Frame> , die navigiert zu einem [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] Seite.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]  
  
 Navigieren zu [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] sind besondere Berechtigungen erforderlich. Beispielsweise Sie navigieren können nicht von einer [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] , die in der teilweise vertrauenswürdigen sicherheitssandkastens der Internetzone ausgeführt wird. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../wpf-partial-trust-security.md).  
  
<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>   
### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>Navigieren mit dem WebBrowser-Steuerelement zu HTML-Dateien  
 Die <xref:System.Windows.Controls.WebBrowser> -Steuerelement unterstützt [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] Dokumenthosting, Navigation und Skript/verwalteter code-Interoperabilität. Ausführliche Informationen in Bezug auf die <xref:System.Windows.Controls.WebBrowser> steuern, finden Sie unter <xref:System.Windows.Controls.WebBrowser>.  
  
 Wie <xref:System.Windows.Controls.Frame>, Navigation zu [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] mit <xref:System.Windows.Controls.WebBrowser> sind besondere Berechtigungen erforderlich. Z. B. in einer teilweise vertrauenswürdigen Anwendung Sie können navigieren, nur für [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] auf der Ursprungssite befindet. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../wpf-partial-trust-security.md).  
  
<a name="Navigating_to_Objects"></a>   
### <a name="navigating-to-custom-objects"></a>Navigieren zu benutzerdefinierten Objekten  
 Wenn Sie über Daten, die als benutzerdefinierte Objekte gespeichert sind verfügen, eine Möglichkeit, die die Anzeige dieser Daten ist die Erstellung einer <xref:System.Windows.Controls.Page> mit Inhalt, der auf diese Objekte gebunden ist (finden Sie unter [Übersicht über die Datenbindung](../data/data-binding-overview.md)). Wenn Sie eine ganze Seite nicht nur zu dem Zweck erstellen möchten, die Objekte anzuzeigen, können Sie stattdessen direkt zu ihnen navigieren.  
  
 Betrachten Sie die `Person` -Klasse, die in den folgenden Code implementiert wird.  
  
 [!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
 [!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]  
  
 Um dorthin zu navigieren, rufen Sie die <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> -Methode, wie im folgenden Code gezeigt.  
  
 [!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]  
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]  
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]  
  
 [!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
 [!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]  
  
 Die folgende Abbildung zeigt das Ergebnis.  
  
 ![Eine Seite, die zu einer Klasse navigiert](./media/navigation-overview/page-navigates-to-an-object.png "Dies ist ein Beispiel für eine Seite, auf ein Objekt navigiert.")  
  
 Aus dieser Abbildung können Sie ersehen, dass nichts Nützliches angezeigt wird. In der Tat der Wert, der angezeigt wird, ist der Rückgabewert von der `ToString` -Methode für die **Person** Objekt; standardmäßig ist dies die einzige Wert, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] zum Darstellen des Objekts verwenden können. Sie können außer Kraft setzen der `ToString` Methode, um aussagekräftigere Informationen zurückzugeben, allerdings wird auch dann nur ein Zeichenfolgenwert sein. Sie verwenden können, eine Technik, der die Darstellungsfunktionen von nutzt [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ist die Verwendung von Datenvorlagen. Sie können eine Datenvorlage implementieren, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] können mit einem Objekt eines bestimmten Typs zuordnen. Der folgende Code zeigt eine Datenvorlage für die `Person` Objekt.  
  
 [!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]  
  
 Hier ist die Datenvorlage zugeordnet ist die `Person` Typ mithilfe der `x:Type` -Markuperweiterung in der `DataType` Attribut. Die Datenvorlage bindet dann `TextBlock` Elemente (finden Sie unter <xref:System.Windows.Controls.TextBlock>) auf die Eigenschaften der `Person` Klasse. Die folgende Abbildung zeigt die aktualisierte Darstellung des der `Person` Objekt.  
  
 ![Navigation zu einer Klasse, die eine Datenvorlage](./media/navigation-overview/navigating-to-a-class.png "Navigation zu einer Klasse, die eine Datenvorlage.")  
  
 Ein Vorteil dieser Technik liegt in der Konsistenz, die Ihnen die Wiederverwendung der Datenvorlage zur konsistenten Anzeige Ihrer Objekte in der gesamten Anwendung erlaubt.  
  
 Weitere Informationen zu Datenvorlagen finden Sie unter [Übersicht über Datenvorlagen](../data/data-templating-overview.md).  
  
<a name="Security"></a>   
## <a name="security"></a>Sicherheit  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ermöglicht die Unterstützung der Journalnavigation [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] ermöglicht Anwendungen, die zum Hosten von Inhalten von Drittanbietern über das Internet, und sie zu der navigiert werden. Zum Schutz von Benutzer und Anwendungen vor bedrohlichem Verhalten zu [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet eine Vielzahl von Sicherheitsfunktionen, die hier erörtert werden [Sicherheit](../security-wpf.md) und [Sicherheit mit WPF teilweiser Vertrauenswürdigkeit](../wpf-partial-trust-security.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [Übersicht über die Anwendungsverwaltung](application-management-overview.md)
- [Paket-URI in WPF](pack-uris-in-wpf.md)
- [Übersicht über die strukturierte Navigation](structured-navigation-overview.md)
- [Übersicht über Navigationstopologien](navigation-topologies-overview.md)
- [Gewusst wie-Themen](navigation-how-to-topics.md)
- [Bereitstellen von WPF-Anwendungen](deploying-a-wpf-application-wpf.md)
