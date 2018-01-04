---
title: "Übersicht über die Anwendungsverwaltung"
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
helpviewer_keywords: application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
caps.latest.revision: "56"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9651b55741a607b1c99a813c0011db380dfd38f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="application-management-overview"></a>Übersicht über die Anwendungsverwaltung
Alle Anwendungen nutzen in der Regel einen gemeinsamen Satz von Funktionen, der für die Implementierung und Verwaltung der Anwendung gilt. Dieses Thema enthält eine Übersicht über die Funktionen in der <xref:System.Windows.Application> Klasse zum Erstellen und Verwalten von Anwendungen.  
   
  
## <a name="the-application-class"></a>Die Application-Klasse  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], häufig verwendeten Funktionen im Anwendungsbereich in gekapselt der <xref:System.Windows.Application> Klasse. Die <xref:System.Windows.Application> Klasse enthält die folgende Funktionen:  
  
-   Lebensdauer der Anwendung nachverfolgen und mit ihr interagieren  
  
-   Befehlszeilenparameter abrufen und verarbeiten  
  
-   Nicht behandelte Ausnahmen erkennen und darauf reagieren  
  
-   Anwendungsspezifische Eigenschaften und Ressourcen teilen  
  
-   Fenster in eigenständigen Anwendungen verwalten  
  
-   Navigation nachverfolgen und verwalten  
  
<a name="The_Application_Class"></a>   
## <a name="how-to-perform-common-tasks-using-the-application-class"></a>Ausführen allgemeiner Aufgaben mithilfe der Application-Klasse  
 Wenn Sie nicht alle Details der interessiert sind die <xref:System.Windows.Application> -Klasse, die folgende Tabelle enthält einige der allgemeinen Aufgaben für <xref:System.Windows.Application> und erläutert, wie sie ausgeführt. Weitere Informationen und entsprechenden Beispielcode finden Sie über die zugehörigen APIs und Themen.  
  
|Aufgabe|Ansatz|  
|----------|--------------|  
|Ein Objekt abrufen, das die aktuelle Anwendung darstellt.|Verwenden Sie die <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>-Eigenschaft.|  
|Einen Startbildschirm zu einer Anwendung hinzufügen.|Finden Sie unter [einen Begrüßungsbildschirm hinzufügen, um eine WPF-Anwendung](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).|  
|Eine Anwendung starten.|Verwenden Sie die <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType>-Methode.|  
|Eine Anwendung beenden.|Verwenden der <xref:System.Windows.Application.Shutdown%2A> Methode der <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> Objekt.|  
|Argumente über die Befehlszeile abrufen.|Behandeln der <xref:System.Windows.Application.Startup?displayProperty=nameWithType> Ereignisses und verwenden Sie die <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> Eigenschaft. Ein Beispiel finden Sie unter der <xref:System.Windows.Application.Startup?displayProperty=nameWithType> Ereignis.|  
|Exitcode der Anwendung abrufen und festlegen.|Legen Sie die <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> Eigenschaft in der <xref:System.Windows.Application.Exit?displayProperty=nameWithType> Ereignishandler oder rufen die <xref:System.Windows.Application.Shutdown%2A> -Methode und übergeben Sie eine ganze Zahl.|  
|Nicht behandelte Ausnahmen erkennen und darauf reagieren.|Behandeln der <xref:System.Windows.Application.DispatcherUnhandledException> Ereignis.|  
|Anwendungsspezifische Ressourcen abrufen und festlegen.|Verwenden Sie die <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>-Eigenschaft.|  
|Ein anwendungsspezifisches Ressourcenverzeichnis verwenden.|Finden Sie unter [verwenden eine Anwendungsbereich Ressourcenwörterbuch](../../../../docs/framework/wpf/app-development/how-to-use-an-application-scope-resource-dictionary.md).|  
|Anwendungsspezifische Eigenschaften abrufen und festlegen.|Verwenden Sie die <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType>-Eigenschaft.|  
|Den Zustand einer Anwendung abrufen und speichern.|Finden Sie unter [persistent speichern und Wiederherstellen von anwendungsspezifische Eigenschaften sitzungsübergreifend Anwendung](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md).|  
|Datendateien ohne Code verwalten, einschließlich Ressourcendateien, Inhalts- und Ursprungssitedateien.|Finden Sie unter [Anwendungsressource WPF-Inhalt und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).|  
|Fenster in eigenständigen Anwendungen verwalten.|Weitere Informationen finden Sie unter [Übersicht über WPF-Fenster](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).|  
|Navigation überwachen und verwalten.|Finden Sie unter [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).|  
  
<a name="The_Application_Definition"></a>   
## <a name="the-application-definition"></a>Die Anwendungsdefinition  
 Nutzung der Funktionalität von der <xref:System.Windows.Application> -Klasse, müssen Sie die Anwendungsdefinition einer implementieren. Ein [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungsdefinition wird eine Klasse, die abgeleitet <xref:System.Windows.Application> und konfiguriert ist, mit einer speziellen [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] Einstellung.  
  
### <a name="implementing-an-application-definition"></a>Implementieren einer Anwendungsdefinition  
 Eine typische [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungsdefinition wird mithilfe von Markup und CodeBehind implementiert. Dadurch können Sie Anwendungseigenschaften und Ressourcen deklarativ mithilfe des Markups festlegen und Ereignisse registrieren, während mit CodeBehind Ereignisse behandelt und anwendungsspezifisches Verhalten implementiert wird.  
  
 Das folgende Beispiel veranschaulicht die Implementierung einer Anwendungsdefinition mithilfe von Markup und CodeBehind:  
  
 [!code-xaml[ApplicationSnippets#ApplicationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]  
  
 [!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
 [!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]  
  
 Damit eine Markup- und eine CodeBehind-Datei zusammenarbeiten können, ist Folgendes erforderlich:  
  
-   Im Markup der `Application` -Element muss enthalten die `x:Class` Attribut. Als die Anwendung erstellt wird, wird das Vorhandensein des `x:Class` im Markup Datei bewirkt, dass [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] zum Erstellen einer `partial` von abgeleitete Klasse <xref:System.Windows.Application> und hat den Namen, die von angegeben wird die `x:Class` Attribut. Dies erfordert das Hinzufügen einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespacedeklaration für das [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ).  
  
-   In der CodeBehind-Klasse muss eine `partial` Klasse mit dem gleichen Namen, die von angegeben wird die `x:Class` Attribut im Markup, und leiten sich aus <xref:System.Windows.Application>. Dadurch wird der Code-Behind-Datei zugeordnet werden die `partial` -Klasse, die für die Markupdatei generiert wird, wenn die Anwendung erstellt wurde (finden Sie unter [Erstellen einer WPF-Anwendung](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)).  
  
> [!NOTE]
>  Beim Erstellen einer neuen WPF-Anwendungsprojekt oder mithilfe von WPF-Browseranwendung Projekt [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], die Anwendungsdefinition einer ist standardmäßig enthalten und wird mithilfe von Markup und CodeBehind definiert.  
  
 Dieser Code ist die Mindestanforderung zum Implementieren einer Anwendungsdefinition. Jedoch eine zusätzliche [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] Konfiguration muss in der Anwendungsdefinition vor dem Erstellen und Ausführen der Anwendung vorgenommen werden.  
  
### <a name="configuring-the-application-definition-for-msbuild"></a>Konfigurieren der Anwendungsdefinition für MSBuild  
 Eigenständige Anwendungen und [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] erfordern die Implementierung einer bestimmten Ebene der Infrastruktur, bevor sie ausgeführt werden können. Der wichtigste Teil dieser Infrastruktur ist der Einstiegspunkt. Wenn eine Anwendung von einem Benutzer gestartet wird, ruft das Betriebssystem den Einstiegspunkt auf, der eine bekannte Funktion zum Starten von Anwendungen ist.  
  
 In der Vergangenheit mussten Entwickler je nach Technologie einen Teil oder sämtlichen Code selbst verfassen. Allerdings [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] dieser Code für Sie generiert, wenn die Markupdatei Ihrer Anwendungsdefinition, als konfiguriert ist ein [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `ApplicationDefinition` -Elements, wie im folgenden gezeigt [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] Projektdatei:  
  
```xml  
<Project   
  DefaultTargets="Build"  
                        xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  ...  
  <ApplicationDefinition Include="App.xaml" />  
  <Compile Include="App.xaml.cs" />  
  ...  
</Project>  
```  
  
 Da die Code-Behind-Datei Code enthält, wird Sie als markiert ein [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile` Element als ist normal.  
  
 Die Anwendung dieser [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] Konfigurationen, die das Markup und Code-Behind-Dateien der Anwendungsdefinition einer führt dazu, dass [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] zum Generieren von Code wie folgt:  
  
 [!code-csharp[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode1)]
 [!code-vb[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode1)]  
[!code-csharp[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode2)]
[!code-vb[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode2)]  
  
 Der resultierende Code ergänzt die Anwendungsdefinition zusätzliche Infrastrukturcode, darunter die Einstiegspunktmethode `Main`. Die <xref:System.STAThreadAttribute> -Attribut angewendet wird, um die `Main` Methode, um anzugeben, dass die Main [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread für die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung ist ein STA-Thread, der für erforderlich ist [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen. Bei Aufruf `Main` erstellt eine neue Instanz der `App` vor dem Aufruf der `InitializeComponent` Methode zum Registrieren der Ereignisse, und legen Sie die Eigenschaften, die im Markup implementiert werden. Da `InitializeComponent` generiert wird, müssen Sie nicht explizit aufrufen `InitializeComponent` aus der Anwendungsdefinition einer wie bei der <xref:System.Windows.Controls.Page> und <xref:System.Windows.Window> Implementierungen. Schließlich die <xref:System.Windows.Application.Run%2A> Methode wird aufgerufen, um die Anwendung zu starten.  
  
<a name="Getting_the_Current_Application"></a>   
## <a name="getting-the-current-application"></a>Abrufen der aktuellen Anwendungsdomäne  
 Da die Funktionalität von der <xref:System.Windows.Application> Klasse werden gemeinsam verwendet eine Anwendung, treten möglicherweise nur eine Instanz der <xref:System.Windows.Application> -Klasse pro <xref:System.AppDomain>. Um dies zu erzwingen der <xref:System.Windows.Application> Klasse wird als eine Singleton-Klasse implementiert (finden Sie unter [Implementing Singleton in c#](http://go.microsoft.com/fwlink/?LinkId=100567)), es wird eine einzelne Instanz von sich selbst und bietet Freigabe des Zugriffs auf diese mit der `static` <xref:System.Windows.Application.Current%2A> Diese Eigenschaft.  
  
 Der folgende Code zeigt, wie Sie erwerben Sie einen Verweis auf die <xref:System.Windows.Application> -Objekt für die aktuelle <xref:System.AppDomain>.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]  
  
 <xref:System.Windows.Application.Current%2A>Gibt einen Verweis auf eine Instanz von der <xref:System.Windows.Application> Klasse. Gegebenenfalls einen Verweis auf Ihre <xref:System.Windows.Application> abgeleitete Klasse, die Sie den Wert wandelt müssen der <xref:System.Windows.Application.Current%2A> -Eigenschaft verwenden, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]  
  
 Sie können den Wert der untersuchen <xref:System.Windows.Application.Current%2A> zu einem beliebigen Zeitpunkt während der Lebensdauer der ein <xref:System.Windows.Application> Objekt. Sie sollten dabei jedoch vorsichtig sein. Nach der <xref:System.Windows.Application> Klasse instanziiert wird, wird ein Zeitraum, in dem der Status des der <xref:System.Windows.Application> Objekt ist nicht konsistent. Während dieses Zeitraums <xref:System.Windows.Application> ist Ausführung verschiedener Initialisierungsaufgaben, die von Ihrem Code erforderlich sind, ausgeführt wird, einschließlich-Infrastruktur einrichten, Festlegen von Eigenschaften und Registrieren von Ereignissen. Wenn Sie versuchen, die <xref:System.Windows.Application> -Objekt während dieses Zeitraums der Code möglicherweise unerwartete Ergebnisse, insbesondere, wenn sie die verschiedenen abhängt <xref:System.Windows.Application> Eigenschaften festgelegt.  
  
 Wenn <xref:System.Windows.Application> schließt seine Initialisierungsarbeit tatsächlich beginnt seine Lebensdauer.  
  
<a name="Application_Lifetime"></a>   
## <a name="application-lifetime"></a>Anwendungslebensdauer  
 Die Lebensdauer einer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung ist gekennzeichnet durch mehrere Ereignisse, die vom ausgelöst werden <xref:System.Windows.Application> , damit Sie wissen, wann die Anwendung gestartet wurde, wurde aktiviert und deaktiviert, und wurde heruntergefahren.  
  
  
<a name="Splash_Screen"></a>   
### <a name="splash-screen"></a>Begrüßungsbildschirm  
 Ab der [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], können Sie angeben, ein Bild in einem Startfenster verwendet werden oder *Begrüßungsbildschirm*. Die <xref:System.Windows.SplashScreen> Klasse ganz einfach ein Startfenster anzuzeigen, während die Anwendung geladen wird. Die <xref:System.Windows.SplashScreen> Fenster erstellt und angezeigt, bevor <xref:System.Windows.Application.Run%2A> aufgerufen wird. Weitere Informationen finden Sie unter [Anwendungsstartzeit](../../../../docs/framework/wpf/advanced/application-startup-time.md) und [einen Begrüßungsbildschirm hinzufügen, um eine WPF-Anwendung](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
<a name="Starting_an_Application"></a>   
### <a name="starting-an-application"></a>Starten einer Anwendung  
 Nach dem <xref:System.Windows.Application.Run%2A> wird aufgerufen, und die Anwendung initialisiert wird, wird die Anwendung für die Ausführung bereit ist. Derzeit gekennzeichnet ist, wenn die <xref:System.Windows.Application.Startup> Ereignis ausgelöst wird:  
  
 [!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind1)]
 [!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind1)]  
[!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind2)]
[!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind2)]  
  
 Ist zu diesem Zeitpunkt in der Lebensdauer einer Anwendung, die am häufigsten verwendete Vorgehensweise zum Anzeigen einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
<a name="Showing_a_User_Interface"></a>   
### <a name="showing-a-user-interface"></a>Anzeigen einer Benutzeroberfläche  
 Die meisten eigenständigen [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] Anwendungen Öffnen einer <xref:System.Windows.Window> wenn damit begonnen wird ausgeführt. Die <xref:System.Windows.Application.Startup> -Ereignishandler ist ein Speicherort, von dem Sie dies erreichen, wie im folgenden Code gezeigt.  
  
 [!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]  
  
 [!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
 [!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]  
  
> [!NOTE]
>  Die erste <xref:System.Windows.Window> Anwendung wird in einer eigenständigen instanziiert werden, das Hauptanwendungsfenster standardmäßig. Dies <xref:System.Windows.Window> Objekt verweist auf die <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> Eigenschaft. Der Wert des der <xref:System.Windows.Application.MainWindow%2A> Eigenschaft kann programmgesteuert geändert werden, wenn ein anderes Zeitfenster als der erste instanziiert <xref:System.Windows.Window> im Hauptfenster werden sollte.  
  
 Wenn ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] erste gestartet, es wird wahrscheinlich navigieren Sie zu einer <xref:System.Windows.Controls.Page>. Dies wird im folgenden Code veranschaulicht.  
  
 [!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]  
  
 [!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
 [!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]  
  
 Wenn Sie behandeln <xref:System.Windows.Application.Startup> Öffnen einer <xref:System.Windows.Window> oder navigieren Sie zu einer <xref:System.Windows.Controls.Page>, können Sie festlegen der `StartupUri` Attribut im Markup.  
  
 Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Application.StartupUri%2A> einer eigenständigen Anwendung zu öffnen einer <xref:System.Windows.Window>.  
  
 [!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]  
  
 Das folgende Beispiel zeigt, wie Sie <xref:System.Windows.Application.StartupUri%2A> aus einer [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] , zu dem navigiert ein <xref:System.Windows.Controls.Page>.  
  
 [!code-xaml[PageSnippets#XBAPStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]  
  
 Dieses Markup hat denselben Effekt wie der vorherige Code zum Öffnen eines Fensters.  
  
> [!NOTE]
>  Weitere Informationen zur Navigation finden Sie unter [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
 Sie behandeln müssen die <xref:System.Windows.Application.Startup> Ereignis zu öffnen einer <xref:System.Windows.Window> Wenn mit einem nicht standardmäßigen Konstruktor instanziiert werden müssen, müssen Sie zum Festlegen von Eigenschaften oder Ereignisse abonnieren, die vor der Anzeige oder Befehlszeilenargumente verarbeitet werden muss, wurden angegeben, wenn die Anwendung gestartet wurde.  
  
<a name="Processing_Command_Line_Arguments"></a>   
### <a name="processing-command-line-arguments"></a>Verarbeiten von Befehlszeilenargumenten  
 In [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)], eigenständige Anwendungen können von der Eingabeaufforderung oder den Desktop gestartet werden. In beiden Fällen können Befehlszeilenargumente an die Anwendung übergeben werden. Im folgenden Beispiel sehen Sie eine Anwendung, die mit nur einem Befehlszeilenargument („/StartMinimized“) gestartet wird:  
  
 `wpfapplication.exe /StartMinimized`  
  
 Während der anwendungsinitialisierung [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Ruft die Befehlszeilenargumente vom Betriebssystem ab und übergibt sie an der <xref:System.Windows.Application.Startup> Ereignishandler über die <xref:System.Windows.StartupEventArgs.Args%2A> Eigenschaft von der <xref:System.Windows.StartupEventArgs> Parameter. Mit Code wie dem folgenden können Sie Befehlszeilenargumente abrufen und speichern.  
  
 [!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]  
  
 [!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
 [!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]  
  
 Der Code behandelt <xref:System.Windows.Application.Startup> zu überprüfen, ob die **/StartMinimized** Befehlszeilenargument wurde angegeben; Wenn dies der Fall ist, öffnet Sie im Hauptfenster mit einem <xref:System.Windows.WindowState> von <xref:System.Windows.WindowState.Minimized>. Beachten Sie, dass, weil die <xref:System.Windows.Window.WindowState%2A> Eigenschaft muss programmgesteuert festgelegt werden, den Hauptknoten <xref:System.Windows.Window> explizit geöffnet werden müssen, im Code.  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]kann nicht abgerufen werden und Befehlszeilenargumente verarbeitet werden, da sie gestartet worden sind, mit [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] Bereitstellung (siehe [Bereitstellen einer WPF-Anwendung](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)). Von den zum Starten verwendeten URLs können jedoch Abfragezeichenfolgenparameter abgerufen und verarbeitet werden.  
  
<a name="Application_Activation_and_Deactivation"></a>   
### <a name="application-activation-and-deactivation"></a>Aktivieren und Deaktivieren von Anwendungen  
 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] ermöglicht es Benutzern, zwischen Anwendungen zu wechseln. Meistens wird dazu die Tastenkombination ALT+TAB verwendet. Eine Anwendung kann nur gewechselt werden, wenn ein sichtbares verfügt über <xref:System.Windows.Window> , die ein Benutzer auswählen kann. Die aktuell ausgewählte <xref:System.Windows.Window> ist die *aktive Fenster* (auch bekannt als die *Vordergrundfenster*) und die <xref:System.Windows.Window> , empfängt Benutzereingaben. Die Anwendung mit dem aktiven Fenster ist die *aktive Anwendung* (oder *Anwendung im Vordergrund*). Eine Anwendung wird unter folgenden Umständen zur aktiven Anwendung:  
  
-   Er wird gestartet und zeigt eine <xref:System.Windows.Window>.  
  
-   Ein Benutzer, die aus einer anderen Anwendung dazu wechselt ein <xref:System.Windows.Window> in der Anwendung.  
  
 Sie können erkennen, wenn eine Anwendung aktiviert, durch behandeln wird der <xref:System.Windows.Application.Activated?displayProperty=nameWithType> Ereignis.  
  
 Auf ähnliche Weise kann eine Anwendung unter folgenden Umständen inaktiv werden:  
  
-   Ein Benutzer wechselt von der aktuellen zu einer anderen Anwendung.  
  
-   Wenn die Anwendung heruntergefahren wird.  
  
 Sie können erkennen, wenn eine Anwendung inaktiv, durch behandeln wird der <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> Ereignis.  
  
 Der folgende Code zeigt, wie behandelt die <xref:System.Windows.Application.Activated> und <xref:System.Windows.Application.Deactivated> Ereignisse, um zu bestimmen, ob eine Anwendung aktiv ist.  
  
 [!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]  
  
 [!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
 [!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]  
  
 Ein <xref:System.Windows.Window> auch aktiviert und deaktiviert werden kann. Weitere Informationen finden Sie unter <xref:System.Windows.Window.Activated?displayProperty=nameWithType> und <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Weder <xref:System.Windows.Application.Activated?displayProperty=nameWithType> noch <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> für ausgelöst [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Application_Shutdown"></a>   
### <a name="application-shutdown"></a>Herunterfahren einer Anwendung  
 Die Lebensdauer einer Anwendung endet mit dem Herunterfahren, das aus folgenden Gründen erfolgen kann:  
  
-   Ein Benutzer schließt jede <xref:System.Windows.Window>.  
  
-   Ein Benutzer schließt den Hauptknoten <xref:System.Windows.Window>.  
  
-   Ein Benutzer beendet die [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] Sitzung durch abmelden oder heruntergefahren.  
  
-   Eine anwendungsspezifische Bedingung wurde erfüllt.  
  
 Zur einfacheren Verwaltung zum Beenden der Anwendung <xref:System.Windows.Application> bietet die <xref:System.Windows.Application.Shutdown%2A> -Methode, die <xref:System.Windows.Application.ShutdownMode%2A> -Eigenschaft, und die <xref:System.Windows.Application.SessionEnding> und <xref:System.Windows.Application.Exit> Ereignisse.  
  
> [!NOTE]
>  <xref:System.Windows.Application.Shutdown%2A>kann nur von Anwendungen, die aufgerufen werden <xref:System.Security.Permissions.UIPermission>. Eigenständige [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen verfügen immer über diese Berechtigung. Allerdings [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] nicht in der Sandbox der Internetzone Sicherheit bei teilweiser Vertrauenswürdigkeit ausgeführt wird.  
  
#### <a name="shutdown-mode"></a>Modus für das Herunterfahren  
 Anwendungen werden in der Regel entweder heruntergefahren, wenn alle Fenster geschlossen werden, oder wenn das Hauptfenster geschlossen wird. Manchmal kann jedoch auch durch andere anwendungsspezifische Bedingungen bestimmt werden, wann eine Anwendung heruntergefahren wird. Sie können angeben, die Bedingungen, unter dem die Anwendung durch Festlegen beendet wird <xref:System.Windows.Application.ShutdownMode%2A> mit einem der folgenden <xref:System.Windows.ShutdownMode> Enumerationswerte:  
  
-   <xref:System.Windows.ShutdownMode.OnLastWindowClose>  
  
-   <xref:System.Windows.ShutdownMode.OnMainWindowClose>  
  
-   <xref:System.Windows.ShutdownMode.OnExplicitShutdown>  
  
 Der Standardwert von <xref:System.Windows.Application.ShutdownMode%2A> ist <xref:System.Windows.ShutdownMode.OnLastWindowClose>, d. h., die eine Anwendung automatisch heruntergefahren wird, wenn das letzte Fenster in der Anwendung vom Benutzer geschlossen wird. Jedoch, wenn die Anwendung heruntergefahren werden soll, wenn das Hauptfenster geschlossen, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] automatisch ausgeführt, wenn Sie festlegen, <xref:System.Windows.Application.ShutdownMode%2A> auf <xref:System.Windows.ShutdownMode.OnMainWindowClose>. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]  
  
 Wenn Sie anwendungsspezifische Herunterfahren-Bedingungen verfügen, legen Sie <xref:System.Windows.Application.ShutdownMode%2A> auf <xref:System.Windows.ShutdownMode.OnExplicitShutdown>. In diesem Fall ist es sicherstellen, dass Sie eine Anwendung heruntergefahren durch explizites Aufrufen der <xref:System.Windows.Application.Shutdown%2A> Methode; andernfalls, Ihre Anwendung weiterhin ausgeführt, selbst wenn alle Fenster geschlossen sind. Beachten Sie, dass <xref:System.Windows.Application.Shutdown%2A> wird implizit aufgerufen, wenn die <xref:System.Windows.Application.ShutdownMode%2A> handelt es sich um <xref:System.Windows.ShutdownMode.OnLastWindowClose> oder <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
> [!NOTE]
>  <xref:System.Windows.Application.ShutdownMode%2A>kann festgelegt werden, aus einer [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], wird aber ignoriert; ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] ist immer heruntergefahren, wenn es weg navigiert wird in einem Browser oder wenn der Browser, hostet die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] geschlossen wird. Weitere Informationen finden Sie unter [Übersicht über die Navigation](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
#### <a name="session-ending"></a>Beenden einer Sitzung  
 Die Shutdown-Bedingungen, die vom beschrieben werden die <xref:System.Windows.Application.ShutdownMode%2A> Eigenschaft für eine Anwendung spezifisch sind. In einigen Fällen kann eine Anwendung aber auch als Ergebnis einer externen Bedingung heruntergefahren werden. Die am häufigsten verwendete externe Bedingung tritt auf, wenn ein Benutzer beendet die [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] ausführen, indem Sie die folgenden Aktionen:  
  
-   Abmelden  
  
-   Herunterfahren  
  
-   Neustarten  
  
-   Wechseln in den Ruhezustand  
  
 Erkennen, wann eine [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] Sitzung endet, können Sie behandeln die <xref:System.Windows.Application.SessionEnding> Ereignis, wie im folgenden Beispiel dargestellt.  
  
 [!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]  
  
 [!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
 [!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]  
  
 In diesem Beispiel überprüft der Code die <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> Eigenschaft, um zu bestimmen, wie die [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] Sitzung wird beendet. Dieser Wert wird verwendet, um dem Benutzer eine Bestätigungsmeldung anzuzeigen. Der Code legt fest, wenn der Benutzer nicht die Sitzung beenden möchten, <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> auf `true` um zu verhindern, dass die [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] Sitzung endet.  
  
> [!NOTE]
>  <xref:System.Windows.Application.SessionEnding>wird nicht ausgelöst, für [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
#### <a name="exit"></a>Schließen  
 Beim Herunterfahren einer Anwendung werden evtl. abschließende Verarbeitungsaufgaben ausgeführt, z. B. Beibehalten des Anwendungszustands. Sie können für diese Situationen behandeln die <xref:System.Windows.Application.Exit> Ereignis.  
  
 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml1)]  
[!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml2)]  
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind1)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind1)]  
[!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind2)]
[!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind2)]  
  
 Das vollständige Beispiel finden Sie unter [Persist und Wiederherstellen Anwendungsbereich Eigenschaften für Anwendungssitzungen](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md).  
  
 <xref:System.Windows.Application.Exit>können behandelt werden, indem sowohl eigenständige Anwendungen und [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Für [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], <xref:System.Windows.Application.Exit> wird unter den folgenden Umständen ausgelöst:  
  
-   Ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Weg von navigiert wird.  
  
-   In [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)], wenn die Registerkarte, die hostet die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] geschlossen wird.  
  
-   Wenn der Browser geschlossen wird.  
  
#### <a name="exit-code"></a>Exitcode  
 Anwendungen werden meistens durch das Betriebssystem als Reaktion auf eine Benutzeranforderung gestartet. Eine Anwendung kann aber auch von einer anderen Anwendung gestartet werden, um eine bestimmte Aufgabe zu übernehmen. Wenn die gestartete Anwendung heruntergefahren wird, muss die startende Anwendung möglicherweise über die Bedingung informiert werden, unter der die gestartete Anwendung heruntergefahren wurde. In diesen Situationen [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] ermöglicht es Anwendungen, Exitcode für die Anwendung beim Herunterfahren zurückgegeben. Standardmäßig [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen einen Wert den Exitcode 0 zurückgegeben werden.  
  
> [!NOTE]
>  Beim Debuggen von [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], Exitcode der Anwendung wird angezeigt, der **Ausgabe** Fenster beim Erstellen die Anwendung in einer Meldung heruntergefahren wird, sieht die folgenden:  
>   
>  `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`  
>   
>  Öffnen Sie die **Ausgabe** Fenster durch Klicken auf **Ausgabe** auf die **Ansicht** Menü.  
  
 Um den Exitcode zu ändern, rufen Sie die <xref:System.Windows.Application.Shutdown%28System.Int32%29> überladen, der ein ganzzahliges Argument den Exitcode werden akzeptiert:  
  
 [!code-csharp[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
 [!code-vb[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]  
  
 Sie können den Wert des Exitcodes ermitteln und ändern, indem die Behandlung der <xref:System.Windows.Application.Exit> Ereignis. Die <xref:System.Windows.Application.Exit> übergebene Ereignishandler eine <xref:System.Windows.ExitEventArgs> stellt den Zugriff auf den Exitcode mit der <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> Eigenschaft. Weitere Informationen finden Sie unter <xref:System.Windows.Application.Exit>.  
  
> [!NOTE]
>  Sie können den Exitcode festlegen, in beiden eigenständige Anwendungen und [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Allerdings wird für der Exitcodewert ignoriert [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Unhandled_Exceptions"></a>   
### <a name="unhandled-exceptions"></a>Nicht behandelte Ausnahmen  
 Es kommt vor, dass eine Anwendung unter nicht ordnungsgemäßen Bedingungen heruntergefahren wird, z. B. wenn eine unerwartete Ausnahme ausgelöst wird. In diesem Fall verfügt die Anwendung möglicherweise nicht über den Code, der zum Erkennen und Verarbeiten der Ausnahme erforderlich ist. Eine solche Ausnahme wird als nicht behandelte Ausnahme bezeichnet. Vor dem Schließen der Anwendung wird eine Meldung angezeigt, die der folgenden ähnelt.  
  
 ![Benachrichtigung über Ausnahmefehler](../../../../docs/framework/wpf/app-development/media/applicationmanagementoverviewfigure2.png "ApplicationManagementOverviewFigure2")  
  
 Für die Benutzererfahrung ist es vorteilhafter, wenn eine Anwendung dieses Standardverhalten vermeidet. Dazu dienen mehrere oder alle der folgenden Aktionen:  
  
-   Anzeigen von benutzerfreundlichen Informationen  
  
-   Versuchen, eine Anwendung weiterhin auszuführen  
  
-   Aufzeichnen von detaillierten, entwicklerfreundlichsten, Ausnahmeinformationen in die [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] Ereignisprotokoll.  
  
 Implementierung dieser Unterstützung hängt wird nicht behandelte Ausnahmen zu erkennen, was die <xref:System.Windows.Application.DispatcherUnhandledException> -Ereignis ausgelöst wird.  
  
 [!code-xaml[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]  
  
 [!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind1)]
 [!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind1)]  
[!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind2)]
[!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind2)]  
  
 Die <xref:System.Windows.Application.DispatcherUnhandledException> übergebene Ereignishandler eine <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> Parameter, die Kontextinformationen der Ausnahmefehler, einschließlich der Ausnahme selbst enthält (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>). Sie können anhand dieser Informationen feststellen, wie die Ausnahme behandelt werden soll.  
  
 Bei der Behandlung <xref:System.Windows.Application.DispatcherUnhandledException>, sollten Sie festlegen der <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> Eigenschaft `true`ist, andernfalls [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] weiterhin betrachtet die Ausnahme nicht behandelt werden, und klicken Sie auf das Standardverhalten, die zuvor beschriebenen zurückgesetzt wird. Wenn eine nicht behandelte Ausnahme ausgelöst wird, und entweder die <xref:System.Windows.Application.DispatcherUnhandledException> Ereignis nicht behandelt wird oder das Ereignis behandelt wird und <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> auf festgelegt ist `false`, die Anwendung sofort heruntergefahren. Darüber hinaus keine weiteren <xref:System.Windows.Application> Ereignisse ausgelöst werden. Folglich müssen Sie behandeln <xref:System.Windows.Application.DispatcherUnhandledException> Wenn Ihre Anwendung über Code, die ausgeführt werden muss verfügt, bevor die Anwendung beendet wird.  
  
 Obwohl eine Anwendung wegen einer nicht behandelten Ausnahme heruntergefahren werden kann, erfolgt das Herunterfahren normalerweise als Reaktion auf eine Benutzeranforderung, wie im nächsten Abschnitt beschrieben.  
  
<a name="Application_Lifetime_Events"></a>   
### <a name="application-lifetime-events"></a>Anwendungslebensdauer-Ereignisse  
 Eigenständige Anwendungen und [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] nicht genau die gleichen Lebensdauer haben. Die folgende Abbildung veranschaulicht die wichtigsten Ereignisse in der Lebensdauer einer eigenständigen Anwendung und die Reihenfolge, in der sie ausgelöst werden.  
  
 ![Eigenständige Anwendung &#45; Anwendungsobjektereignisse](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")  
  
 Ebenso die folgende Abbildung veranschaulicht die wichtigen Ereignissen während der Lebensdauer der ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], und veranschaulicht die Abfolge, in dem sie ausgelöst werden.  
  
 ![XBAP &#45; Anwendungsobjektereignisse](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Application>  
 [Übersicht über WPF-Fenster](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)  
 [Übersicht über die Navigation](../../../../docs/framework/wpf/app-development/navigation-overview.md)  
 [WPF-Anwendungsressource, Inhalts- und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)  
 [Paket-URI in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)  
 [Anwendungsmodell: Gewusst-wie-Themen](http://msdn.microsoft.com/en-us/76771b09-3688-4d1c-8818-9b3f4cf39a30)  
 [Anwendungsentwicklung](../../../../docs/framework/wpf/app-development/index.md)
