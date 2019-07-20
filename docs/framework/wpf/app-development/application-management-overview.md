---
title: Übersicht über die Anwendungsverwaltung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: d8e26ff197e22ffa18b4acdd020b80879023c0f7
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364090"
---
# <a name="application-management-overview"></a>Übersicht über die Anwendungsverwaltung
Alle Anwendungen nutzen in der Regel einen gemeinsamen Satz von Funktionen, der für die Implementierung und Verwaltung der Anwendung gilt. Dieses Thema enthält eine Übersicht über die Funktionen <xref:System.Windows.Application> der-Klasse zum Erstellen und Verwalten von-Anwendungen.  

## <a name="the-application-class"></a>Die Application-Klasse  
 In WPF werden allgemeine Funktionen für Anwendungsbereiche in der <xref:System.Windows.Application> -Klasse gekapselt. Die <xref:System.Windows.Application> -Klasse umfasst die folgenden Funktionen:  
  
- Lebensdauer der Anwendung nachverfolgen und mit ihr interagieren  
  
- Befehlszeilenparameter abrufen und verarbeiten  
  
- Nicht behandelte Ausnahmen erkennen und darauf reagieren  
  
- Anwendungsspezifische Eigenschaften und Ressourcen teilen  
  
- Fenster in eigenständigen Anwendungen verwalten  
  
- Navigation nachverfolgen und verwalten  
  
<a name="The_Application_Class"></a>   
## <a name="how-to-perform-common-tasks-using-the-application-class"></a>Ausführen allgemeiner Aufgaben mithilfe der Application-Klasse  
 Wenn Sie nicht an allen Details der <xref:System.Windows.Application> -Klasse interessiert sind, finden Sie in der folgenden Tabelle einige allgemeine Aufgaben für <xref:System.Windows.Application> und deren Ausführung. Weitere Informationen und entsprechenden Beispielcode finden Sie über die zugehörigen APIs und Themen.  
  
|Aufgabe|Ansatz|  
|----------|--------------|  
|Ein Objekt abrufen, das die aktuelle Anwendung darstellt.|Verwenden Sie die <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>-Eigenschaft.|  
|Einen Startbildschirm zu einer Anwendung hinzufügen.|Siehe [Hinzufügen eines Begrüßungs Bildschirms zu einer WPF-Anwendung](how-to-add-a-splash-screen-to-a-wpf-application.md).|  
|Eine Anwendung starten.|Verwenden Sie die <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType>-Methode.|  
|Eine Anwendung beenden.|Verwenden Sie <xref:System.Windows.Application.Shutdown%2A> die-Methode <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> des-Objekts.|  
|Argumente über die Befehlszeile abrufen.|Behandeln Sie <xref:System.Windows.Application.Startup?displayProperty=nameWithType> das Ereignis, und <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> verwenden Sie die-Eigenschaft. Ein Beispiel finden Sie unter dem <xref:System.Windows.Application.Startup?displayProperty=nameWithType> -Ereignis.|  
|Exitcode der Anwendung abrufen und festlegen.|Legen Sie <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> die-Eigenschaft <xref:System.Windows.Application.Exit?displayProperty=nameWithType> im Ereignishandler fest, <xref:System.Windows.Application.Shutdown%2A> oder geben Sie die-Methode an, und übergeben Sie eine ganze Zahl|  
|Nicht behandelte Ausnahmen erkennen und darauf reagieren.|Behandeln Sie <xref:System.Windows.Application.DispatcherUnhandledException> das-Ereignis.|  
|Anwendungsspezifische Ressourcen abrufen und festlegen.|Verwenden Sie die <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>-Eigenschaft.|  
|Ein anwendungsspezifisches Ressourcenverzeichnis verwenden.|Siehe [Verwenden eines Ressourcen Wörterbuchs für den Anwendungsbereich](how-to-use-an-application-scope-resource-dictionary.md).|  
|Anwendungsspezifische Eigenschaften abrufen und festlegen.|Verwenden Sie die <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType>-Eigenschaft.|  
|Den Zustand einer Anwendung abrufen und speichern.|Weitere Informationen finden Sie unter beibehalten [und Wiederherstellen von Anwendungsbereichs Eigenschaften über Anwendungs Sitzungen hinweg](persist-and-restore-application-scope-properties.md).|  
|Datendateien ohne Code verwalten, einschließlich Ressourcendateien, Inhalts- und Ursprungssitedateien.|Weitere Informationen finden Sie [unter WPF-Anwendungs Ressource, Inhalts-und Datendateien](wpf-application-resource-content-and-data-files.md).|  
|Fenster in eigenständigen Anwendungen verwalten.|Weitere Informationen finden Sie unter [Übersicht über WPF-Fenster](wpf-windows-overview.md).|  
|Navigation überwachen und verwalten.|Siehe [Navigations Übersicht](navigation-overview.md).|  
  
<a name="The_Application_Definition"></a>   
## <a name="the-application-definition"></a>Die Anwendungsdefinition  
 Um die Funktionalität <xref:System.Windows.Application> der-Klasse verwenden zu können, müssen Sie eine Anwendungs Definition implementieren. Eine WPF-Anwendungs Definition ist eine Klasse, die <xref:System.Windows.Application> von abgeleitet wird und mit einer speziellen MSBuild-Einstellung konfiguriert wird.  

### <a name="implementing-an-application-definition"></a>Implementieren einer Anwendungsdefinition  
 Eine typische WPF-Anwendungs Definition wird sowohl mit Markup als auch mit Code Behind implementiert. Dadurch können Sie Anwendungseigenschaften und Ressourcen deklarativ mithilfe des Markups festlegen und Ereignisse registrieren, während mit CodeBehind Ereignisse behandelt und anwendungsspezifisches Verhalten implementiert wird.  
  
 Das folgende Beispiel veranschaulicht die Implementierung einer Anwendungsdefinition mithilfe von Markup und CodeBehind:  
  
 [!code-xaml[ApplicationSnippets#ApplicationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]  
  
 [!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
 [!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]  
  
 Damit eine Markup- und eine CodeBehind-Datei zusammenarbeiten können, ist Folgendes erforderlich:  
  
- Im Markup muss das `Application` -Element das `x:Class` -Attribut enthalten. Wenn die Anwendung erstellt wird, bewirkt das vorhanden `x:Class` sein von in der Markup Datei, dass MSBuild `partial` eine Klasse erstellt, <xref:System.Windows.Application> die von abgeleitet wird und den Namen `x:Class` hat, der vom-Attribut angegeben wird. Dies erfordert das Hinzufügen einer XML-Namespace Deklaration für das XAML`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`-Schema ().
  
- Bei Code-Behind muss die Klasse eine `partial` Klasse mit demselben Namen sein, der im Markup durch das `x:Class` -Attribut angegeben wird und von <xref:System.Windows.Application>abgeleitet werden muss. Dadurch kann die Code-Behind-Datei mit der `partial` -Klasse verknüpft werden, die beim Erstellen der Anwendung für die Markup Datei generiert wird (siehe [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md)).  
  
> [!NOTE]
>  Wenn Sie ein neues WPF-Anwendungsprojekt oder ein WPF-Browser Anwendungsprojekt mithilfe von Visual Studio erstellen, ist standardmäßig eine Anwendungs Definition enthalten, die sowohl mit Markup als auch mit Code-Behind definiert wird.  
  
 Dieser Code ist die Mindestanforderung zum Implementieren einer Anwendungsdefinition. Vor dem Erstellen und Ausführen der Anwendung muss jedoch eine zusätzliche MSBuild-Konfiguration an der Anwendungs Definition vorgenommen werden.  
  
### <a name="configuring-the-application-definition-for-msbuild"></a>Konfigurieren der Anwendungsdefinition für MSBuild  
 Eigenständige Anwendungen und XAML-Browser Anwendungen (XBAPs) erfordern die Implementierung einer bestimmten Infrastruktur Ebene, bevor Sie ausgeführt werden können. Der wichtigste Teil dieser Infrastruktur ist der Einstiegspunkt. Wenn eine Anwendung von einem Benutzer gestartet wird, ruft das Betriebssystem den Einstiegspunkt auf, der eine bekannte Funktion zum Starten von Anwendungen ist.  
  
 In der Vergangenheit mussten Entwickler je nach Technologie einen Teil oder sämtlichen Code selbst verfassen. WPF generiert diesen Code jedoch für Sie, wenn die Markup Datei Ihrer Anwendungs Definition als MSBuild `ApplicationDefinition` -Element konfiguriert ist, wie in der folgenden MSBuild-Projektdatei dargestellt:  
  
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
  
 Da die Code-Behind-Datei Code enthält, wird Sie als MSBuild `Compile` -Element markiert, wie es normal ist.  
  
 Die Anwendung dieser MSBuild-Konfigurationen auf die Markup-und Code Behind-Dateien einer Anwendungs Definition bewirkt, dass MSBuild Code wie den folgenden generiert:  
  
 [!code-csharp[auto-generated-code](~/samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs)]
 [!code-vb[auto-generated-code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb)]  
  
 Der resultierende Code erweitert die Anwendungs Definition mit zusätzlichem Infrastruktur Code, der die Einstiegspunkt Methode `Main`einschließt. Das <xref:System.STAThreadAttribute> -Attribut wird auf die `Main` -Methode angewendet, um anzugeben, dass der Hauptbenutzer Oberflächen-Thread für die WPF-Anwendung ein STA-Thread ist, der für WPF-Anwendungen erforderlich ist. Beim Aufruf von `Main` wird eine neue Instanz von `App` erstellt, bevor `InitializeComponent` die-Methode aufgerufen wird, um die Ereignisse zu registrieren und die im Markup implementierten Eigenschaften festzulegen. Da `InitializeComponent` für Sie generiert wird, müssen Sie nicht explizit aus einer `InitializeComponent` Anwendungs Definition aufzurufen, wie dies bei <xref:System.Windows.Controls.Page> - <xref:System.Windows.Window> und-Implementierungen der Fall ist. Zum Schluss wird <xref:System.Windows.Application.Run%2A> die-Methode aufgerufen, um die Anwendung zu starten.  
  
<a name="Getting_the_Current_Application"></a>   
## <a name="getting-the-current-application"></a>Abrufen der aktuellen Anwendungsdomäne  
 Da die Funktionalität der- <xref:System.Windows.Application> Klasse für eine Anwendung freigegeben wird, kann pro <xref:System.AppDomain>nur eine Instanz <xref:System.Windows.Application> der-Klasse vorhanden sein. Um dies zu erzwingen, <xref:System.Windows.Application> wird die-Klasse als Singleton-Klasse implementiert (siehe [Implementieren von C#Singleton in ](https://go.microsoft.com/fwlink/?LinkId=100567)), mit der eine einzelne Instanz von sich selbst erstellt wird und mit `static` der <xref:System.Windows.Application.Current%2A> -Eigenschaft gemeinsamer Zugriff darauf ermöglicht wird.  
  
 Der folgende Code zeigt, wie Sie einen Verweis auf das <xref:System.Windows.Application> -Objekt für das <xref:System.AppDomain>aktuelle-Objekt abrufen.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]  
  
 <xref:System.Windows.Application.Current%2A>Gibt einen Verweis auf eine Instanz der <xref:System.Windows.Application> -Klasse zurück. Wenn Sie einen Verweis auf <xref:System.Windows.Application> die abgeleitete Klasse wünschen, müssen Sie den Wert <xref:System.Windows.Application.Current%2A> der-Eigenschaft umwandeln, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]  
  
 Sie können den Wert von <xref:System.Windows.Application.Current%2A> zu einem beliebigen Zeitpunkt während der Lebensdauer <xref:System.Windows.Application> eines Objekts überprüfen. Sie sollten dabei jedoch vorsichtig sein. Nachdem die <xref:System.Windows.Application> Klasse instanziiert wurde, gibt es einen Zeitraum, in dem der Status <xref:System.Windows.Application> des Objekts inkonsistent ist. Während dieses Zeitraums <xref:System.Windows.Application> führt die verschiedenen Initialisierungs Aufgaben aus, die von Ihrem Code für die Ausführung erforderlich sind, einschließlich dem Einrichten der Anwendungs Infrastruktur, dem Festlegen von Eigenschaften und dem Registrieren von Ereignissen. Wenn Sie versuchen, das- <xref:System.Windows.Application> Objekt während dieses Zeitraums zu verwenden, kann der Code unerwartete Ergebnisse aufweisen, insbesondere dann, wenn er <xref:System.Windows.Application> von den verschiedenen festgelegten Eigenschaften abhängig ist.  
  
 Wenn <xref:System.Windows.Application> die Initialisierungs Arbeit abgeschlossen ist, beginnt die Lebensdauer tatsächlich.  
  
<a name="Application_Lifetime"></a>   
## <a name="application-lifetime"></a>Anwendungslebensdauer  
 Die Lebensdauer einer WPF-Anwendung wird durch mehrere Ereignisse gekennzeichnet, die von <xref:System.Windows.Application> ausgelöst werden, um Sie zu informieren, wenn Ihre Anwendung gestartet wurde, aktiviert und deaktiviert wurde und heruntergefahren wurde.  

<a name="Splash_Screen"></a>   
### <a name="splash-screen"></a>Begrüßungsbildschirm  
 Ab der .NET Framework 3,5 SP1 können Sie ein Bild angeben, das in einem Startfenster oder einem Begrüßungs *Bildschirm*verwendet werden soll. Mit <xref:System.Windows.SplashScreen> der-Klasse können Sie problemlos ein Startfenster anzeigen, während die Anwendung geladen wird. Das <xref:System.Windows.SplashScreen> Fenster wird erstellt und angezeigt, <xref:System.Windows.Application.Run%2A> bevor aufgerufen wird. Weitere Informationen finden Sie unter [Startzeit der Anwendung](../advanced/application-startup-time.md) und [Hinzufügen eines Begrüßungs Bildschirms zu einer WPF-Anwendung](how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
<a name="Starting_an_Application"></a>   
### <a name="starting-an-application"></a>Starten einer Anwendung  
 Nachdem <xref:System.Windows.Application.Run%2A> aufgerufen und die Anwendung initialisiert wurde, ist die Anwendung zur Ausführung bereit. Dieser Moment ist gekennzeichnet, wenn das <xref:System.Windows.Application.Startup> -Ereignis ausgelöst wird:  
  
[!code-csharp[Startup-event](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs?range=3-11,31-33)]
[!code-vb[Startup-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb?range=5-11,30-32)]
  
 An diesem Punkt in der Lebensdauer einer Anwendung ist es am häufigsten, eine Benutzeroberfläche anzuzeigen.  
  
<a name="Showing_a_User_Interface"></a>
### <a name="showing-a-user-interface"></a>Anzeigen einer Benutzeroberfläche  
 Die meisten eigenständigen Windows- <xref:System.Windows.Window> Anwendungen öffnen eine, wenn Sie gestartet werden. Der <xref:System.Windows.Application.Startup> Ereignishandler ist ein Speicherort, von dem aus Sie dies tun können, wie im folgenden Code veranschaulicht.  
  
 [!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]  
  
 [!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
 [!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]  
  
> [!NOTE]
>  Der erste <xref:System.Windows.Window> , der in einer eigenständigen Anwendung instanziiert werden soll, wird standardmäßig zum Hauptanwendungsfenster. Auf <xref:System.Windows.Window> dieses Objekt wird von der <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> -Eigenschaft verwiesen. Der Wert der <xref:System.Windows.Application.MainWindow%2A> Eigenschaft kann Programm gesteuert geändert werden, wenn ein anderes Fenster als das erste instanziierte <xref:System.Windows.Window> das Hauptfenster sein sollte.  
  
 Wenn eine XBAP zum ersten Mal gestartet wird, navigiert Sie wahrscheinlich <xref:System.Windows.Controls.Page>zu einer. Dies wird im folgenden Code veranschaulicht.  
  
 [!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]  
  
 [!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
 [!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]  
  
 Wenn Sie behandeln <xref:System.Windows.Application.Startup> , um nur eine <xref:System.Windows.Window> zu öffnen oder zu <xref:System.Windows.Controls.Page>einer zu navigieren, können `StartupUri` Sie stattdessen das-Attribut im Markup festlegen.  
  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Application.StartupUri%2A> aus einer eigenständigen Anwendung verwendet wird <xref:System.Windows.Window>, um eine zu öffnen.  
  
 [!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]  
  
 Im folgenden Beispiel wird gezeigt, <xref:System.Windows.Application.StartupUri%2A> wie Sie von einer XBAP aus zu navigieren. <xref:System.Windows.Controls.Page>  
  
 [!code-xaml[PageSnippets#XBAPStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]  
  
 Dieses Markup hat denselben Effekt wie der vorherige Code zum Öffnen eines Fensters.  
  
> [!NOTE]
>  Weitere Informationen zur Navigation finden Sie unter [Übersicht](navigation-overview.md)über die Navigation.  
  
 Sie müssen das-Ereignis <xref:System.Windows.Application.Startup> behandeln, um eine <xref:System.Windows.Window> zu öffnen, wenn Sie Sie mit einem nicht parameterlosen Konstruktor instanziieren müssen, oder Sie müssen die Eigenschaften festlegen oder die zugehörigen Ereignisse abonnieren, bevor Sie Sie darstellen, oder Sie müssen alle Befehlszeilenargumente verarbeiten. die beim Starten der Anwendung bereitgestellt wurden.  
  
<a name="Processing_Command_Line_Arguments"></a>   
### <a name="processing-command-line-arguments"></a>Verarbeiten von Befehlszeilenargumenten  
 In Windows können eigenständige Anwendungen entweder über eine Eingabeaufforderung oder über den Desktop gestartet werden. In beiden Fällen können Befehlszeilenargumente an die Anwendung übergeben werden. Im folgenden Beispiel sehen Sie eine Anwendung, die mit nur einem Befehlszeilenargument („/StartMinimized“) gestartet wird:  
  
 `wpfapplication.exe /StartMinimized`  
  
 Während der Anwendungs Initialisierung ruft WPF die Befehlszeilenargumente aus dem Betriebssystem ab und übergibt sie über die <xref:System.Windows.Application.Startup> <xref:System.Windows.StartupEventArgs.Args%2A> -Eigenschaft des <xref:System.Windows.StartupEventArgs> -Parameters an den-Ereignishandler. Mit Code wie dem folgenden können Sie Befehlszeilenargumente abrufen und speichern.  
  
 [!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]  
  
 [!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
 [!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]  
  
 Der Code Handles <xref:System.Windows.Application.Startup> , um zu überprüfen, ob das **/StartMinimized** -Befehlszeilenargument bereitgestellt wurde. wenn dies der Fall ist <xref:System.Windows.WindowState> , <xref:System.Windows.WindowState.Minimized>wird das Hauptfenster mit einem von geöffnet. Beachten Sie, dass <xref:System.Windows.Window.WindowState%2A> <xref:System.Windows.Window> die-Eigenschaft im Code explizit geöffnet werden muss, da die-Eigenschaft Programm gesteuert festgelegt werden muss.  
  
 XBAPs können Befehlszeilenargumente nicht abrufen und verarbeiten, da Sie mithilfe der ClickOnce-Bereitstellung gestartet werden (siehe bereitstellen [einer WPF-Anwendung](deploying-a-wpf-application-wpf.md)). Von den zum Starten verwendeten URLs können jedoch Abfragezeichenfolgenparameter abgerufen und verarbeitet werden.  
  
<a name="Application_Activation_and_Deactivation"></a>   
### <a name="application-activation-and-deactivation"></a>Aktivieren und Deaktivieren von Anwendungen  
 Windows ermöglicht es Benutzern, zwischen Anwendungen zu wechseln. Meistens wird dazu die Tastenkombination ALT+TAB verwendet. Eine Anwendung kann nur dann auf gewechselt werden, wenn Sie über <xref:System.Windows.Window> ein sichtbares verfügt, das ein Benutzer auswählen kann. Das aktuell ausgewählte <xref:System.Windows.Window> ist das *aktive Fenster* (auch als *Vordergrund Fenster*bezeichnet) und das <xref:System.Windows.Window> , das Benutzereingaben empfängt. Die Anwendung mit dem aktiven Fenster ist die *aktive Anwendung* (oder *Vordergrund Anwendung*). Eine Anwendung wird unter folgenden Umständen zur aktiven Anwendung:  
  
- Sie wird gestartet und zeigt eine <xref:System.Windows.Window>.  
  
- Ein Benutzer wechselt von einer anderen Anwendung, indem <xref:System.Windows.Window> er eine in der Anwendung auswählt.  
  
 Sie können erkennen, wann eine Anwendung aktiv wird, indem <xref:System.Windows.Application.Activated?displayProperty=nameWithType> Sie das-Ereignis behandeln.  
  
 Auf ähnliche Weise kann eine Anwendung unter folgenden Umständen inaktiv werden:  
  
- Ein Benutzer wechselt von der aktuellen zu einer anderen Anwendung.  
  
- Wenn die Anwendung heruntergefahren wird.  
  
 Sie können erkennen, wenn eine Anwendung inaktiv wird, <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> indem Sie das-Ereignis behandeln.  
  
 Der folgende Code zeigt, wie die <xref:System.Windows.Application.Activated> -und- <xref:System.Windows.Application.Deactivated> Ereignisse behandelt werden, um zu bestimmen, ob eine Anwendung aktiv ist.  
  
 [!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]  
  
 [!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
 [!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]  
  
 Ein <xref:System.Windows.Window> kann auch aktiviert und deaktiviert werden. Weitere Informationen finden Sie unter <xref:System.Windows.Window.Activated?displayProperty=nameWithType> und <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Weder <xref:System.Windows.Application.Activated?displayProperty=nameWithType> noch<xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> wird für XBAPs ausgelöst.  
  
<a name="Application_Shutdown"></a>   
### <a name="application-shutdown"></a>Herunterfahren einer Anwendung  
 Die Lebensdauer einer Anwendung endet mit dem Herunterfahren, das aus folgenden Gründen erfolgen kann:  
  
- Ein Benutzer schließt alle <xref:System.Windows.Window>.  
  
- Ein Benutzer schließt den Haupt <xref:System.Windows.Window>Benutzer.  
  
- Ein Benutzer beendet die Windows-Sitzung, indem er sich abmeldet oder herunterfährt.  
  
- Eine anwendungsspezifische Bedingung wurde erfüllt.  
  
 Zur Unterstützung beim Herunterfahren der <xref:System.Windows.Application> Anwendung werden <xref:System.Windows.Application.Shutdown%2A> von die- <xref:System.Windows.Application.ShutdownMode%2A> Methode, die- <xref:System.Windows.Application.SessionEnding> Eigenschaft <xref:System.Windows.Application.Exit> sowie die-und-Ereignisse bereitstellt.  
  
> [!NOTE]
>  <xref:System.Windows.Application.Shutdown%2A>kann nur von Anwendungen aufgerufen werden, die <xref:System.Security.Permissions.UIPermission>über verfügen. Eigenständige WPF-Anwendungen verfügen immer über diese Berechtigung. XBAPs, die in der Sicherheits Sandbox mit teilweiser Vertrauenswürdigkeit der Internet Zone ausgeführt werden, ist jedoch nicht.  
  
#### <a name="shutdown-mode"></a>Modus für das Herunterfahren  
 Anwendungen werden in der Regel entweder heruntergefahren, wenn alle Fenster geschlossen werden, oder wenn das Hauptfenster geschlossen wird. Manchmal kann jedoch auch durch andere anwendungsspezifische Bedingungen bestimmt werden, wann eine Anwendung heruntergefahren wird. Sie können die Bedingungen angeben, unter denen die Anwendung heruntergefahren wird, <xref:System.Windows.Application.ShutdownMode%2A> indem Sie mit einem der <xref:System.Windows.ShutdownMode> folgenden Enumerationswerte festlegen:  
  
- <xref:System.Windows.ShutdownMode.OnLastWindowClose>  
  
- <xref:System.Windows.ShutdownMode.OnMainWindowClose>  
  
- <xref:System.Windows.ShutdownMode.OnExplicitShutdown>  
  
 Der Standardwert von <xref:System.Windows.Application.ShutdownMode%2A> ist <xref:System.Windows.ShutdownMode.OnLastWindowClose>. Dies bedeutet, dass eine Anwendung automatisch heruntergefahren wird, wenn das letzte Fenster in der Anwendung vom Benutzer geschlossen wird. Wenn die Anwendung jedoch heruntergefahren werden soll, wenn das Hauptfenster geschlossen wird, führt WPF dies automatisch aus, wenn <xref:System.Windows.Application.ShutdownMode%2A> Sie <xref:System.Windows.ShutdownMode.OnMainWindowClose>auf festlegen. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]  
  
 Wenn Sie anwendungsspezifische Bedingungen für das Herunterfahren haben, <xref:System.Windows.Application.ShutdownMode%2A> legen <xref:System.Windows.ShutdownMode.OnExplicitShutdown>Sie auf fest. In diesem Fall liegt es in ihrer Verantwortung, eine Anwendung durch explizites Aufrufen der <xref:System.Windows.Application.Shutdown%2A> -Methode zu beenden. andernfalls wird die Anwendung weiterhin ausgeführt, auch wenn alle Fenster geschlossen sind. Beachten Sie <xref:System.Windows.Application.Shutdown%2A> , dass implizit aufgerufen wird <xref:System.Windows.Application.ShutdownMode%2A> , wenn <xref:System.Windows.ShutdownMode.OnLastWindowClose> entweder <xref:System.Windows.ShutdownMode.OnMainWindowClose>oder ist.  
  
> [!NOTE]
>  <xref:System.Windows.Application.ShutdownMode%2A>kann aus einer XBAP festgelegt werden, wird jedoch ignoriert. eine XBAP wird immer heruntergefahren, wenn Sie von einem Browser entfernt wird oder wenn der Browser, der die XBAP hostet, geschlossen ist. Weitere Informationen finden Sie unter [Übersicht über die Navigation](navigation-overview.md).  
  
#### <a name="session-ending"></a>Beenden einer Sitzung  
 Die von der <xref:System.Windows.Application.ShutdownMode%2A> -Eigenschaft beschriebenen Shutdown-Bedingungen gelten für eine Anwendung. In einigen Fällen kann eine Anwendung aber auch als Ergebnis einer externen Bedingung heruntergefahren werden. Die häufigste externe Bedingung tritt auf, wenn ein Benutzer die Windows-Sitzung mit den folgenden Aktionen beendet:  
  
- Abmelden  
  
- Herunterfahren  
  
- Neustarten  
  
- Wechseln in den Ruhezustand  
  
 Um zu erkennen, wann eine Windows-Sitzung beendet wird, <xref:System.Windows.Application.SessionEnding> können Sie das-Ereignis behandeln, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]  
  
 [!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
 [!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]  
  
 In diesem Beispiel überprüft der Code die <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> -Eigenschaft, um zu bestimmen, wie die Windows-Sitzung beendet wird. Dieser Wert wird verwendet, um dem Benutzer eine Bestätigungsmeldung anzuzeigen. Wenn der Benutzer die Sitzung nicht beenden möchte, legt <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> der Code auf `true` fest, um zu verhindern, dass die Windows-Sitzung beendet wird.  
  
> [!NOTE]
>  <xref:System.Windows.Application.SessionEnding>wird für XBAPs nicht ausgelöst.

#### <a name="exit"></a>Schließen  
 Beim Herunterfahren einer Anwendung werden evtl. abschließende Verarbeitungsaufgaben ausgeführt, z. B. Beibehalten des Anwendungszustands. In diesen Fällen können Sie das <xref:System.Windows.Application.Exit> -Ereignis behandeln, wie dies im folgenden Beispiel der `App_Exit` Fall ist. Sie wird als Ereignishandler in der Datei " *app. XAML* " definiert. Die Implementierung wird in den Dateien *app.XAML.cs* und *Application. XAML. vb* hervorgehoben.
  
[!code-xaml[Defining-the-Exit-event-handler](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]  
  
 [!code-csharp[Handling-the-Exit-event](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=42-55)]
 [!code-vb[Handling-the-Exit-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=34-45)]  
  
 Das komplette Beispiel finden Sie unter beibehalten [und Wiederherstellen von Anwendungsbereichs Eigenschaften über Anwendungs Sitzungen hinweg](persist-and-restore-application-scope-properties.md).  
  
 <xref:System.Windows.Application.Exit>kann sowohl von eigenständigen Anwendungen als auch von XBAPs verarbeitet werden. Für XBAPs <xref:System.Windows.Application.Exit> wird in den folgenden Situationen ausgelöst:  
  
- Eine XBAP wird von der navigiert.  
  
- In [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)], wenn die Registerkarte, auf der die XBAP gehostet wird, geschlossen wird.  
  
- Wenn der Browser geschlossen wird.  
  
#### <a name="exit-code"></a>Exitcode  
 Anwendungen werden meistens durch das Betriebssystem als Reaktion auf eine Benutzeranforderung gestartet. Eine Anwendung kann aber auch von einer anderen Anwendung gestartet werden, um eine bestimmte Aufgabe zu übernehmen. Wenn die gestartete Anwendung heruntergefahren wird, muss die startende Anwendung möglicherweise über die Bedingung informiert werden, unter der die gestartete Anwendung heruntergefahren wurde. In diesen Situationen ermöglicht Windows Anwendungen, beim Herunterfahren einen Anwendungsexitcode zurückzugeben. Standardmäßig geben WPF-Anwendungen einen Exitcodewert von 0 zurück.  
  
> [!NOTE]
>  Wenn Sie in Visual Studio debuggen, wird der Anwendungsexitcode im Fenster **Ausgabe** angezeigt, wenn die Anwendung heruntergefahren wird, und zwar in einer Meldung, die wie folgt aussieht:  
>   
>  `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`  
>   
>  Öffnen Sie das **Ausgabe** Fenster, indem Sie im Menü **Ansicht** auf **Ausgabe** klicken.  
  
 Um den Exitcode zu ändern, können Sie <xref:System.Windows.Application.Shutdown%28System.Int32%29> die-Überladung aufrufen, die als Exitcode ein ganzzahliges Argument akzeptiert:  
  
 [!code-csharp[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
 [!code-vb[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]  
  
 Sie können den Wert des Exitcodes erkennen und ändern, indem Sie das <xref:System.Windows.Application.Exit> -Ereignis behandeln. An <xref:System.Windows.Application.Exit> den Ereignishandler wird ein <xref:System.Windows.ExitEventArgs> übermittelt, der den Zugriff auf den Exitcode mit der <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> -Eigenschaft ermöglicht. Weitere Informationen finden Sie unter <xref:System.Windows.Application.Exit>.  
  
> [!NOTE]
>  Sie können den Exitcode sowohl in eigenständigen Anwendungen als auch in XBAPs festlegen. Der Exitcodewert wird für XBAPs jedoch ignoriert.  
  
<a name="Unhandled_Exceptions"></a>   
### <a name="unhandled-exceptions"></a>Nicht behandelte Ausnahmen  
 Es kommt vor, dass eine Anwendung unter nicht ordnungsgemäßen Bedingungen heruntergefahren wird, z. B. wenn eine unerwartete Ausnahme ausgelöst wird. In diesem Fall verfügt die Anwendung möglicherweise nicht über den Code, der zum Erkennen und Verarbeiten der Ausnahme erforderlich ist. Eine solche Ausnahme wird als nicht behandelte Ausnahme bezeichnet. Vor dem Schließen der Anwendung wird eine Meldung angezeigt, die der folgenden ähnelt.  
  
 ![Screenshot mit einer nicht behandelten Ausnahme Benachrichtigung.](./media/application-management-overview/unhandled-exception-notification.png)  
  
 Für die Benutzererfahrung ist es vorteilhafter, wenn eine Anwendung dieses Standardverhalten vermeidet. Dazu dienen mehrere oder alle der folgenden Aktionen:  
  
- Anzeigen von benutzerfreundlichen Informationen  
  
- Versuchen, eine Anwendung weiterhin auszuführen  
  
- Aufzeichnen detaillierter, Entwickler freundlicher Ausnahme Informationen im Windows-Ereignisprotokoll.  
  
 Die Implementierung dieser Unterstützung ist davon abhängig, dass nicht behandelte Ausnahmen erkannt werden können. <xref:System.Windows.Application.DispatcherUnhandledException> Dies ist das, wofür das Ereignis ausgelöst wird.  
  
[!code-xaml[detecting-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]  
  
[!code-csharp[code-to-detect-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs)]
[!code-vb[code-to-detect-unhandled-exceptions](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb)]  
  
 Dem <xref:System.Windows.Application.DispatcherUnhandledException> Ereignishandler wird ein <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> Parameter übergeben, der Kontextinformationen bezüglich der nicht behandelten Ausnahme enthält, einschließlich der Ausnahme selbst<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>(). Sie können anhand dieser Informationen feststellen, wie die Ausnahme behandelt werden soll.  
  
 Wenn Sie behandeln <xref:System.Windows.Application.DispatcherUnhandledException>, sollten Sie die <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> -Eigenschaft auf `true`festlegen. andernfalls wird die Ausnahme von WPF weiterhin als nicht behandelt betrachtet, und das zuvor beschriebene Standardverhalten wird wieder hergestellt. Wenn eine nicht behandelte Ausnahme ausgelöst wird und entweder das <xref:System.Windows.Application.DispatcherUnhandledException> -Ereignis nicht behandelt wird, oder wenn das-Ereignis <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> behandelt wird und `false`auf festgelegt ist, wird die Anwendung sofort heruntergefahren. Außerdem werden keine anderen <xref:System.Windows.Application> Ereignisse ausgelöst. Folglich müssen Sie behandeln <xref:System.Windows.Application.DispatcherUnhandledException> , wenn Ihre Anwendung über Code verfügt, der ausgeführt werden muss, bevor die Anwendung heruntergefahren wird.  
  
 Obwohl eine Anwendung wegen einer nicht behandelten Ausnahme heruntergefahren werden kann, erfolgt das Herunterfahren normalerweise als Reaktion auf eine Benutzeranforderung, wie im nächsten Abschnitt beschrieben.  
  
<a name="Application_Lifetime_Events"></a>   
### <a name="application-lifetime-events"></a>Anwendungslebensdauer-Ereignisse  
 Eigenständige Anwendungen und XBAPs haben nicht genau die gleiche Lebensdauer. Die folgende Abbildung veranschaulicht die wichtigsten Ereignisse in der Lebensdauer einer eigenständigen Anwendung und die Reihenfolge, in der sie ausgelöst werden.  
  
 ![Eigenständige Anwendung &#45; Anwendungsobjektereignisse](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")  
  
 Die folgende Abbildung veranschaulicht die wichtigsten Ereignisse in der Lebensdauer einer XBAP und zeigt die Reihenfolge an, in der Sie ausgelöst werden.  
  
 ![XBAP &#45; Anwendungsobjektereignisse](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Application>
- [Übersicht über WPF-Fenster](wpf-windows-overview.md)
- [Übersicht über die Navigation](navigation-overview.md)
- [WPF-Anwendungsressource, Inhalts- und Datendateien](wpf-application-resource-content-and-data-files.md)
- [Paket-URI in WPF](pack-uris-in-wpf.md)
- [Anwendungsmodell: Themen zur Vorgehensweise](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))
- [Anwendungsentwicklung](index.md)
