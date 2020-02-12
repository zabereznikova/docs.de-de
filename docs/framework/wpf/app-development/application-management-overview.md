---
title: Übersicht über die Anwendungsverwaltung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: dbc5bd9f699415fb47f21c6a45b1c58cfcff0f33
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124519"
---
# <a name="application-management-overview"></a>Übersicht über die Anwendungsverwaltung

Alle Anwendungen nutzen in der Regel einen gemeinsamen Satz von Funktionen, der für die Implementierung und Verwaltung der Anwendung gilt. Dieses Thema enthält eine Übersicht über die Funktionen in der <xref:System.Windows.Application>-Klasse zum Erstellen und Verwalten von Anwendungen.

## <a name="the-application-class"></a>Die Application-Klasse

In WPF werden allgemeine Funktionen für Anwendungsbereiche in der <xref:System.Windows.Application>-Klasse gekapselt. Die <xref:System.Windows.Application>-Klasse umfasst die folgenden Funktionen:

- Lebensdauer der Anwendung nachverfolgen und mit ihr interagieren

- Abrufen und Verarbeiten von Befehlszeilenparametern

- Nicht behandelte Ausnahmen erkennen und darauf reagieren

- Anwendungsspezifische Eigenschaften und Ressourcen teilen

- Verwalten von Fenstern in eigenständigen Anwendungen

- Navigation nachverfolgen und verwalten

<a name="The_Application_Class"></a>

## <a name="how-to-perform-common-tasks-using-the-application-class"></a>Ausführen allgemeiner Aufgaben mithilfe der Application-Klasse

Wenn Sie nicht an allen Details der <xref:System.Windows.Application>-Klasse interessiert sind, werden in der folgenden Tabelle einige der allgemeinen Aufgaben für <xref:System.Windows.Application> und deren erreichen aufgeführt. Weitere Informationen und entsprechenden Beispielcode finden Sie über die zugehörigen APIs und Themen.

|Aufgabe|Vorgehensweise|
|----------|--------------|
|Ein Objekt abrufen, das die aktuelle Anwendung darstellt.|Verwenden Sie die <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>-Eigenschaft.|
|Einen Startbildschirm zu einer Anwendung hinzufügen.|Siehe [Hinzufügen eines Begrüßungs Bildschirms zu einer WPF-Anwendung](how-to-add-a-splash-screen-to-a-wpf-application.md).|
|Eine Anwendung starten.|Verwenden Sie die <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType>-Methode.|
|Eine Anwendung beenden.|Verwenden Sie die <xref:System.Windows.Application.Shutdown%2A>-Methode des <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>-Objekts.|
|Argumente über die Befehlszeile abrufen.|Behandeln Sie das <xref:System.Windows.Application.Startup?displayProperty=nameWithType>-Ereignis, und verwenden Sie die <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType>-Eigenschaft. Ein Beispiel finden Sie unter dem <xref:System.Windows.Application.Startup?displayProperty=nameWithType>-Ereignis.|
|Exitcode der Anwendung abrufen und festlegen.|Legen Sie die <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType>-Eigenschaft im <xref:System.Windows.Application.Exit?displayProperty=nameWithType>-Ereignishandler fest, oder nennen Sie die <xref:System.Windows.Application.Shutdown%2A>-Methode, und übergeben Sie eine ganze Zahl.|
|Nicht behandelte Ausnahmen erkennen und darauf reagieren.|Behandeln Sie das <xref:System.Windows.Application.DispatcherUnhandledException>-Ereignis.|
|Anwendungsspezifische Ressourcen abrufen und festlegen.|Verwenden Sie die <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>-Eigenschaft.|
|Ein anwendungsspezifisches Ressourcenverzeichnis verwenden.|Siehe [Verwenden eines Ressourcen Wörterbuchs für den Anwendungsbereich](how-to-use-an-application-scope-resource-dictionary.md).|
|Anwendungsspezifische Eigenschaften abrufen und festlegen.|Verwenden Sie die <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType>-Eigenschaft.|
|Den Zustand einer Anwendung abrufen und speichern.|Weitere Informationen finden Sie unter beibehalten [und Wiederherstellen von Anwendungsbereichs Eigenschaften über Anwendungs Sitzungen hinweg](persist-and-restore-application-scope-properties.md).|
|Datendateien ohne Code verwalten, einschließlich Ressourcendateien, Inhalts- und Ursprungssitedateien.|Weitere Informationen finden Sie [unter WPF-Anwendungs Ressource, Inhalts-und Datendateien](wpf-application-resource-content-and-data-files.md).|
|Fenster in eigenständigen Anwendungen verwalten.|Weitere Informationen finden Sie unter [Übersicht über WPF-Fenster](wpf-windows-overview.md).|
|Navigation überwachen und verwalten.|Siehe [Navigations Übersicht](navigation-overview.md).|

<a name="The_Application_Definition"></a>

## <a name="the-application-definition"></a>Die Anwendungsdefinition

Um die Funktionalität der <xref:System.Windows.Application>-Klasse zu nutzen, müssen Sie eine Anwendungs Definition implementieren. Eine WPF-Anwendungs Definition ist eine Klasse, die von <xref:System.Windows.Application> abgeleitet ist und mit einer speziellen MSBuild-Einstellung konfiguriert ist.

### <a name="implementing-an-application-definition"></a>Implementieren einer Anwendungsdefinition

Eine typische WPF-Anwendungs Definition wird sowohl mit Markup als auch mit Code Behind implementiert. Dadurch können Sie Anwendungseigenschaften und Ressourcen deklarativ mithilfe des Markups festlegen und Ereignisse registrieren, während mit CodeBehind Ereignisse behandelt und anwendungsspezifisches Verhalten implementiert wird.

Das folgende Beispiel veranschaulicht die Implementierung einer Anwendungsdefinition mithilfe von Markup und CodeBehind:

[!code-xaml[ApplicationSnippets#ApplicationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]

[!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
[!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]

Damit eine Markup- und eine CodeBehind-Datei zusammenarbeiten können, ist Folgendes erforderlich:

- Im Markup muss das `Application`-Element das `x:Class`-Attribut enthalten. Wenn die Anwendung erstellt wird, bewirkt das vorhanden sein von `x:Class` in der Markup Datei, dass MSBuild eine `partial` Klasse erstellt, die von <xref:System.Windows.Application> abgeleitet ist und über den Namen verfügt, der durch das `x:Class`-Attribut angegeben wird. Dies erfordert das Hinzufügen einer XML-Namespace Deklaration für das XAML-Schema (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`).

- Bei Code-Behind muss die Klasse eine `partial` Klasse mit demselben Namen sein, der im Markup durch das `x:Class`-Attribut angegeben wird und von <xref:System.Windows.Application>abgeleitet werden muss. Dadurch kann die Code-Behind-Datei mit der `partial`-Klasse verknüpft werden, die beim Erstellen der Anwendung für die Markup Datei generiert wird (siehe [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md)).

> [!NOTE]
> Wenn Sie ein neues WPF-Anwendungsprojekt oder ein WPF-Browser Anwendungsprojekt mithilfe von Visual Studio erstellen, ist standardmäßig eine Anwendungs Definition enthalten, die sowohl mit Markup als auch mit Code-Behind definiert wird.

Dieser Code ist die Mindestanforderung zum Implementieren einer Anwendungsdefinition. Vor dem Erstellen und Ausführen der Anwendung muss jedoch eine zusätzliche MSBuild-Konfiguration an der Anwendungs Definition vorgenommen werden.

### <a name="configuring-the-application-definition-for-msbuild"></a>Konfigurieren der Anwendungsdefinition für MSBuild

Eigenständige Anwendungen und XAML-Browser Anwendungen (XBAPs) erfordern die Implementierung einer bestimmten Infrastruktur Ebene, bevor Sie ausgeführt werden können. Der wichtigste Teil dieser Infrastruktur ist der Einstiegspunkt. Wenn eine Anwendung von einem Benutzer gestartet wird, ruft das Betriebssystem den Einstiegspunkt auf, der eine bekannte Funktion zum Starten von Anwendungen ist.

In der Vergangenheit mussten Entwickler je nach Technologie einen Teil oder sämtlichen Code selbst verfassen. WPF generiert diesen Code jedoch für Sie, wenn die Markup Datei Ihrer Anwendungs Definition als MSBuild-`ApplicationDefinition` Element konfiguriert ist, wie in der folgenden MSBuild-Projektdatei gezeigt:

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

Da die Code-Behind-Datei Code enthält, wird Sie als MSBuild-`Compile` Element gekennzeichnet, wie es normal ist.

Die Anwendung dieser MSBuild-Konfigurationen auf die Markup-und Code Behind-Dateien einer Anwendungs Definition bewirkt, dass MSBuild Code wie den folgenden generiert:

[!code-csharp[auto-generated-code](~/samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs)]
[!code-vb[auto-generated-code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb)]

Der resultierende Code erweitert die Anwendungs Definition mit zusätzlichem Infrastruktur Code, der die `Main`für die Einstiegspunkt Methode einschließt. Das <xref:System.STAThreadAttribute>-Attribut wird auf die `Main`-Methode angewendet, um anzugeben, dass der Hauptbenutzer Oberflächen-Thread für die WPF-Anwendung ein STA-Thread ist, der für WPF-Anwendungen erforderlich ist. Beim Aufruf erstellt `Main` eine neue Instanz von `App`, bevor die `InitializeComponent`-Methode aufgerufen wird, um die Ereignisse zu registrieren und die im Markup implementierten Eigenschaften festzulegen. Da `InitializeComponent` für Sie generiert wird, müssen Sie `InitializeComponent` nicht explizit aus einer Anwendungs Definition aufzurufen, wie dies für <xref:System.Windows.Controls.Page>-und <xref:System.Windows.Window>-Implementierungen der Fall ist. Zum Schluss wird die <xref:System.Windows.Application.Run%2A>-Methode aufgerufen, um die Anwendung zu starten.

<a name="Getting_the_Current_Application"></a>

## <a name="getting-the-current-application"></a>Abrufen der aktuellen Anwendungsdomäne

Da die Funktionalität der <xref:System.Windows.Application>-Klasse für eine Anwendung freigegeben wird, kann pro <xref:System.AppDomain>nur eine Instanz der <xref:System.Windows.Application>-Klasse vorhanden sein. Um dies zu erzwingen, wird die <xref:System.Windows.Application>-Klasse als Singleton-Klasse implementiert (siehe [Implementieren von C#Singleton in ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650316(v=pandp.10))), mit der eine einzelne Instanz von sich selbst erstellt wird und mit der `static`<xref:System.Windows.Application.Current%2A>-Eigenschaft gemeinsamer Zugriff darauf ermöglicht wird.

Der folgende Code zeigt, wie Sie einen Verweis auf das <xref:System.Windows.Application>-Objekt für die aktuelle <xref:System.AppDomain>abrufen.

[!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
[!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]

<xref:System.Windows.Application.Current%2A> gibt einen Verweis auf eine Instanz der <xref:System.Windows.Application>-Klasse zurück. Wenn Sie einen Verweis auf Ihre <xref:System.Windows.Application> abgeleitete Klasse wünschen, müssen Sie den Wert der Eigenschaft <xref:System.Windows.Application.Current%2A> umwandeln, wie im folgenden Beispiel gezeigt.

[!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
[!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]

Sie können den Wert von <xref:System.Windows.Application.Current%2A> jederzeit in der Lebensdauer eines <xref:System.Windows.Application> Objekts überprüfen. Sie sollten dabei jedoch vorsichtig sein. Nachdem die <xref:System.Windows.Application> Klasse instanziiert wurde, gibt es einen Zeitraum, in dem der Status des <xref:System.Windows.Application> Objekts inkonsistent ist. Während dieses Zeitraums führt <xref:System.Windows.Application> die verschiedenen Initialisierungs Aufgaben aus, die von Ihrem Code für die Ausführung erforderlich sind, einschließlich dem Einrichten der Anwendungs Infrastruktur, dem Festlegen von Eigenschaften und dem Registrieren von Ereignissen. Wenn Sie versuchen, das <xref:System.Windows.Application>-Objekt während dieses Zeitraums zu verwenden, kann der Code unerwartete Ergebnisse aufweisen, insbesondere, wenn er von den verschiedenen <xref:System.Windows.Application> Eigenschaften abhängig ist, die festgelegt werden.

Wenn die Initialisierungs Arbeit <xref:System.Windows.Application> abgeschlossen ist, beginnt die Lebensdauer tatsächlich.

<a name="Application_Lifetime"></a>

## <a name="application-lifetime"></a>Anwendungslebensdauer

Die Lebensdauer einer WPF-Anwendung wird durch mehrere Ereignisse gekennzeichnet, die von <xref:System.Windows.Application> ausgelöst werden, um Sie zu informieren, wann die Anwendung gestartet wurde, aktiviert und deaktiviert wurde und heruntergefahren wurde.

<a name="Splash_Screen"></a>

### <a name="splash-screen"></a>Begrüßungsbildschirm

Ab der .NET Framework 3,5 SP1 können Sie ein Bild angeben, das in einem Startfenster oder einem Begrüßungs *Bildschirm*verwendet werden soll. Die <xref:System.Windows.SplashScreen>-Klasse vereinfacht das Anzeigen eines Start Fensters, während die Anwendung geladen wird. Das Fenster <xref:System.Windows.SplashScreen> wird erstellt und angezeigt, bevor <xref:System.Windows.Application.Run%2A> aufgerufen wird. Weitere Informationen finden Sie unter [Startzeit der Anwendung](../advanced/application-startup-time.md) und [Hinzufügen eines Begrüßungs Bildschirms zu einer WPF-Anwendung](how-to-add-a-splash-screen-to-a-wpf-application.md).

<a name="Starting_an_Application"></a>

### <a name="starting-an-application"></a>Starten einer Anwendung

Nachdem <xref:System.Windows.Application.Run%2A> aufgerufen und die Anwendung initialisiert wurde, ist die Anwendung zur Ausführung bereit. Dieser Moment ist gekennzeichnet, wenn das <xref:System.Windows.Application.Startup>-Ereignis ausgelöst wird:

[!code-csharp[Startup-event](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs?range=3-11,31-33)]
[!code-vb[Startup-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb?range=5-11,30-32)]

An diesem Punkt in der Lebensdauer einer Anwendung ist es am häufigsten, eine Benutzeroberfläche anzuzeigen.

<a name="Showing_a_User_Interface"></a>

### <a name="showing-a-user-interface"></a>Anzeigen einer Benutzeroberfläche

Die meisten eigenständigen Windows-Anwendungen öffnen eine <xref:System.Windows.Window>, wenn Sie mit der Ausführung beginnen. Der <xref:System.Windows.Application.Startup> Ereignishandler ist ein Speicherort, von dem aus Sie dies tun können, wie im folgenden Code veranschaulicht.

[!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]

[!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
[!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]

> [!NOTE]
> Der erste <xref:System.Windows.Window>, der in einer eigenständigen Anwendung instanziiert werden soll, wird standardmäßig zum Hauptanwendungsfenster. Auf dieses <xref:System.Windows.Window> Objekt wird von der <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>-Eigenschaft verwiesen. Der Wert der <xref:System.Windows.Application.MainWindow%2A>-Eigenschaft kann Programm gesteuert geändert werden, wenn ein anderes Fenster als das erste instanziierte <xref:System.Windows.Window> das Hauptfenster sein sollte.

Wenn eine XBAP zum ersten Mal gestartet wird, navigiert Sie höchstwahrscheinlich zu einem <xref:System.Windows.Controls.Page>. Dies wird im folgenden Code dargestellt.

[!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]

[!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
[!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]

Wenn Sie <xref:System.Windows.Application.Startup> nur eine <xref:System.Windows.Window> öffnen oder zu einem <xref:System.Windows.Controls.Page>navigieren, können Sie stattdessen das `StartupUri`-Attribut im Markup festlegen.

Im folgenden Beispiel wird gezeigt, wie das <xref:System.Windows.Application.StartupUri%2A> aus einer eigenständigen Anwendung verwendet wird, um eine <xref:System.Windows.Window>zu öffnen.

[!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]

Im folgenden Beispiel wird gezeigt, wie <xref:System.Windows.Application.StartupUri%2A> aus einer XBAP verwendet wird, um zu einer <xref:System.Windows.Controls.Page>zu navigieren.

[!code-xaml[PageSnippets#XBAPStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]

Dieses Markup hat denselben Effekt wie der vorherige Code zum Öffnen eines Fensters.

> [!NOTE]
> Weitere Informationen zur Navigation finden Sie unter [Übersicht](navigation-overview.md)über die Navigation.

Sie müssen das <xref:System.Windows.Application.Startup>-Ereignis behandeln, um eine <xref:System.Windows.Window> zu öffnen, wenn Sie Sie mit einem nicht parameterlosen Konstruktor instanziieren müssen, oder Sie müssen die Eigenschaften festlegen oder die zugehörigen Ereignisse abonnieren, bevor Sie angezeigt werden, oder Sie müssen alle Befehlszeilenargumente verarbeiten, die beim Starten der Anwendung bereitgestellt wurden.

<a name="Processing_Command_Line_Arguments"></a>

### <a name="processing-command-line-arguments"></a>Verarbeiten von Befehlszeilenargumenten

In Windows können eigenständige Anwendungen entweder über eine Eingabeaufforderung oder über den Desktop gestartet werden. In beiden Fällen können Befehlszeilenargumente an die Anwendung übergeben werden. Im folgenden Beispiel sehen Sie eine Anwendung, die mit nur einem Befehlszeilenargument („/StartMinimized“) gestartet wird:

`wpfapplication.exe /StartMinimized`

Während der Anwendungs Initialisierung ruft WPF die Befehlszeilenargumente aus dem Betriebssystem ab und übergibt sie über die <xref:System.Windows.StartupEventArgs.Args%2A>-Eigenschaft des <xref:System.Windows.StartupEventArgs>-Parameters an den <xref:System.Windows.Application.Startup>-Ereignishandler. Mit Code wie dem folgenden können Sie Befehlszeilenargumente abrufen und speichern.

[!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]

[!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
[!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]

Der Code behandelt <xref:System.Windows.Application.Startup>, um zu überprüfen, ob das **/StartMinimized** -Befehlszeilenargument bereitgestellt wurde. Wenn dies der Fall ist, wird das Hauptfenster mit einer <xref:System.Windows.WindowState> <xref:System.Windows.WindowState.Minimized>geöffnet. Beachten Sie, dass die <xref:System.Windows.Window.WindowState%2A>-Eigenschaft Programm gesteuert festgelegt werden muss, da der Haupt <xref:System.Windows.Window> explizit im Code geöffnet werden muss.

XBAPs können Befehlszeilenargumente nicht abrufen und verarbeiten, da Sie mithilfe der ClickOnce-Bereitstellung gestartet werden (siehe bereitstellen [einer WPF-Anwendung](deploying-a-wpf-application-wpf.md)). Von den zum Starten verwendeten URLs können jedoch Abfragezeichenfolgenparameter abgerufen und verarbeitet werden.

<a name="Application_Activation_and_Deactivation"></a>

### <a name="application-activation-and-deactivation"></a>Aktivieren und Deaktivieren von Anwendungen

Windows ermöglicht es Benutzern, zwischen Anwendungen zu wechseln. Meistens wird dazu die Tastenkombination ALT+TAB verwendet. Eine Anwendung kann nur dann auf gewechselt werden, wenn Sie über ein sichtbares <xref:System.Windows.Window> verfügt, das ein Benutzer auswählen kann. Der aktuell ausgewählte <xref:System.Windows.Window> ist das *aktive Fenster* (auch als *Vordergrund Fenster*bezeichnet) und ist der <xref:System.Windows.Window>, der Benutzereingaben empfängt. Die Anwendung mit dem aktiven Fenster ist die *aktive Anwendung* (oder *Vordergrund Anwendung*). Eine Anwendung wird unter folgenden Umständen zur aktiven Anwendung:

- Es wird gestartet und zeigt eine <xref:System.Windows.Window>an.

- Ein Benutzer wechselt von einer anderen Anwendung, indem er eine <xref:System.Windows.Window> in der Anwendung auswählt.

Sie können erkennen, wenn eine Anwendung aktiv wird, indem Sie das <xref:System.Windows.Application.Activated?displayProperty=nameWithType>-Ereignis behandeln.

Auf ähnliche Weise kann eine Anwendung unter folgenden Umständen inaktiv werden:

- Ein Benutzer wechselt von der aktuellen zu einer anderen Anwendung.

- Wenn die Anwendung heruntergefahren wird.

Sie können erkennen, wenn eine Anwendung inaktiv wird, indem Sie das <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType>-Ereignis behandeln.

Der folgende Code zeigt, wie die <xref:System.Windows.Application.Activated> und <xref:System.Windows.Application.Deactivated> Ereignisse behandelt werden, um zu bestimmen, ob eine Anwendung aktiv ist.

[!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]

[!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
[!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]

Eine <xref:System.Windows.Window> kann auch aktiviert und deaktiviert werden. Weitere Informationen finden Sie unter <xref:System.Windows.Window.Activated?displayProperty=nameWithType> und <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>.

> [!NOTE]
> Weder <xref:System.Windows.Application.Activated?displayProperty=nameWithType> noch <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> werden für XBAPs ausgelöst.

<a name="Application_Shutdown"></a>

### <a name="application-shutdown"></a>Herunterfahren einer Anwendung

Die Lebensdauer einer Anwendung endet mit dem Herunterfahren, das aus folgenden Gründen erfolgen kann:

- Ein Benutzer schließt alle <xref:System.Windows.Window>.

- Ein Benutzer schließt das Haupt <xref:System.Windows.Window>.

- Ein Benutzer beendet die Windows-Sitzung, indem er sich abmeldet oder herunterfährt.

- Eine anwendungsspezifische Bedingung wurde erfüllt.

Zur Unterstützung beim Herunterfahren der Anwendung können <xref:System.Windows.Application> die <xref:System.Windows.Application.Shutdown%2A>-Methode, die <xref:System.Windows.Application.ShutdownMode%2A>-Eigenschaft sowie die <xref:System.Windows.Application.SessionEnding>-und <xref:System.Windows.Application.Exit>-Ereignisse bereitstellen.

> [!NOTE]
> <xref:System.Windows.Application.Shutdown%2A> können nur von Anwendungen aufgerufen werden, die über <xref:System.Security.Permissions.UIPermission>verfügen. Eigenständige WPF-Anwendungen verfügen immer über diese Berechtigung. XBAPs, die in der Sicherheits Sandbox mit teilweiser Vertrauenswürdigkeit der Internet Zone ausgeführt werden, ist jedoch nicht.

#### <a name="shutdown-mode"></a>Modus für das Herunterfahren

Anwendungen werden in der Regel entweder heruntergefahren, wenn alle Fenster geschlossen werden, oder wenn das Hauptfenster geschlossen wird. Manchmal kann jedoch auch durch andere anwendungsspezifische Bedingungen bestimmt werden, wann eine Anwendung heruntergefahren wird. Sie können die Bedingungen angeben, unter denen die Anwendung heruntergefahren wird, indem Sie <xref:System.Windows.Application.ShutdownMode%2A> mit einem der folgenden <xref:System.Windows.ShutdownMode> Enumerationswerte festlegen:

- <xref:System.Windows.ShutdownMode.OnLastWindowClose>

- <xref:System.Windows.ShutdownMode.OnMainWindowClose>

- <xref:System.Windows.ShutdownMode.OnExplicitShutdown>

Der Standardwert <xref:System.Windows.Application.ShutdownMode%2A> ist <xref:System.Windows.ShutdownMode.OnLastWindowClose>. Dies bedeutet, dass eine Anwendung automatisch heruntergefahren wird, wenn das letzte Fenster in der Anwendung vom Benutzer geschlossen wird. Wenn die Anwendung jedoch heruntergefahren werden soll, wenn das Hauptfenster geschlossen wird, führt WPF dies automatisch aus, wenn Sie <xref:System.Windows.Application.ShutdownMode%2A> auf <xref:System.Windows.ShutdownMode.OnMainWindowClose>festlegen. Dies wird im folgenden Beispiel gezeigt.

[!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]

Wenn Sie anwendungsspezifische Bedingungen für das Herunterfahren festgelegt haben, legen Sie <xref:System.Windows.Application.ShutdownMode%2A> auf <xref:System.Windows.ShutdownMode.OnExplicitShutdown>fest. In diesem Fall müssen Sie eine Anwendung Herunterfahren, indem Sie explizit die <xref:System.Windows.Application.Shutdown%2A>-Methode aufrufen. Andernfalls wird die Anwendung weiterhin ausgeführt, auch wenn alle Fenster geschlossen sind. Beachten Sie, dass <xref:System.Windows.Application.Shutdown%2A> implizit aufgerufen wird, wenn der <xref:System.Windows.Application.ShutdownMode%2A> entweder <xref:System.Windows.ShutdownMode.OnLastWindowClose> oder <xref:System.Windows.ShutdownMode.OnMainWindowClose>ist.

> [!NOTE]
> <xref:System.Windows.Application.ShutdownMode%2A> kann von einer XBAP aus festgelegt werden, wird jedoch ignoriert. eine XBAP wird immer heruntergefahren, wenn Sie von einem Browser entfernt wird oder wenn der Browser, der die XBAP hostet, geschlossen ist. Weitere Informationen finden Sie unter [Übersicht über die Navigation](navigation-overview.md).

#### <a name="session-ending"></a>Beenden einer Sitzung

Die von der <xref:System.Windows.Application.ShutdownMode%2A>-Eigenschaft beschriebenen Beendigungs Bedingungen gelten für eine Anwendung. In einigen Fällen kann eine Anwendung aber auch als Ergebnis einer externen Bedingung heruntergefahren werden. Die häufigste externe Bedingung tritt auf, wenn ein Benutzer die Windows-Sitzung mit den folgenden Aktionen beendet:

- Abmelden

- Herunterfahren

- Neustarten

- Wechseln in den Ruhezustand

Um zu erkennen, wann eine Windows-Sitzung beendet wird, können Sie das <xref:System.Windows.Application.SessionEnding>-Ereignis behandeln, wie im folgenden Beispiel veranschaulicht.

[!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]

[!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
[!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]

In diesem Beispiel überprüft der Code die <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A>-Eigenschaft, um zu bestimmen, wie die Windows-Sitzung beendet wird. Dieser Wert wird verwendet, um dem Benutzer eine Bestätigungsmeldung anzuzeigen. Wenn der Benutzer die Sitzung nicht beenden möchte, legt der Code <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> auf `true` fest, um zu verhindern, dass die Windows-Sitzung beendet wird.

> [!NOTE]
> <xref:System.Windows.Application.SessionEnding> wird für XBAPs nicht ausgelöst.

#### <a name="exit"></a>Beenden

Beim Herunterfahren einer Anwendung werden evtl. abschließende Verarbeitungsaufgaben ausgeführt, z. B. Beibehalten des Anwendungszustands. In diesen Situationen können Sie das <xref:System.Windows.Application.Exit>-Ereignis behandeln, wie der `App_Exit`-Ereignishandler im folgenden Beispiel bewirkt. Sie wird als Ereignishandler in der Datei " *app. XAML* " definiert. Die Implementierung wird in den Dateien *app.XAML.cs* und *Application. XAML. vb* hervorgehoben.

[!code-xaml[Defining-the-Exit-event-handler](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]

[!code-csharp[Handling-the-Exit-event](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=42-55)]
[!code-vb[Handling-the-Exit-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=34-45)]

Das komplette Beispiel finden Sie unter beibehalten [und Wiederherstellen von Anwendungsbereichs Eigenschaften über Anwendungs Sitzungen hinweg](persist-and-restore-application-scope-properties.md).

<xref:System.Windows.Application.Exit> können sowohl von eigenständigen Anwendungen als auch von XBAPs verarbeitet werden. Bei XBAPs wird <xref:System.Windows.Application.Exit> in den folgenden Situationen ausgelöst:

- Eine XBAP wird von der navigiert.

- In Internet Explorer, wenn die Registerkarte, auf der die XBAP gehostet wird, geschlossen wird.

- Wenn der Browser geschlossen wird.

#### <a name="exit-code"></a>Exitcode

Anwendungen werden meistens durch das Betriebssystem als Reaktion auf eine Benutzeranforderung gestartet. Eine Anwendung kann aber auch von einer anderen Anwendung gestartet werden, um eine bestimmte Aufgabe zu übernehmen. Wenn die gestartete Anwendung heruntergefahren wird, muss die startende Anwendung möglicherweise über die Bedingung informiert werden, unter der die gestartete Anwendung heruntergefahren wurde. In diesen Situationen ermöglicht Windows Anwendungen, beim Herunterfahren einen Anwendungsexitcode zurückzugeben. Standardmäßig geben WPF-Anwendungen einen Exitcodewert von 0 zurück.

> [!NOTE]
> Wenn Sie in Visual Studio debuggen, wird der Anwendungsexitcode im Fenster **Ausgabe** angezeigt, wenn die Anwendung heruntergefahren wird, und zwar in einer Meldung, die wie folgt aussieht:
>
> `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`
>
> Öffnen Sie das **Ausgabe** Fenster, indem Sie im Menü **Ansicht** auf **Ausgabe** klicken.

Um den Exitcode zu ändern, können Sie die <xref:System.Windows.Application.Shutdown%28System.Int32%29>-Überladung aufrufen, die ein ganzzahliges Argument als Exitcode akzeptiert:

[!code-csharp[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
[!code-vb[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]

Sie können den Wert des Exitcodes erkennen und ändern, indem Sie das <xref:System.Windows.Application.Exit>-Ereignis behandeln. Dem <xref:System.Windows.Application.Exit>-Ereignishandler wird ein <xref:System.Windows.ExitEventArgs> übermittelt, der den Zugriff auf den Exitcode mit der <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A>-Eigenschaft ermöglicht. Weitere Informationen finden Sie unter <xref:System.Windows.Application.Exit>.

> [!NOTE]
> Sie können den Exitcode sowohl in eigenständigen Anwendungen als auch in XBAPs festlegen. Der Exitcodewert wird für XBAPs jedoch ignoriert.

<a name="Unhandled_Exceptions"></a>

### <a name="unhandled-exceptions"></a>Nicht behandelte Ausnahmen

Es kommt vor, dass eine Anwendung unter nicht ordnungsgemäßen Bedingungen heruntergefahren wird, z. B. wenn eine unerwartete Ausnahme ausgelöst wird. In diesem Fall verfügt die Anwendung möglicherweise nicht über den Code, der zum Erkennen und Verarbeiten der Ausnahme erforderlich ist. Eine solche Ausnahme wird als nicht behandelte Ausnahme bezeichnet. Vor dem Schließen der Anwendung wird eine Meldung angezeigt, die der folgenden ähnelt.

![Screenshot mit einer nicht behandelten Ausnahme Benachrichtigung.](./media/application-management-overview/unhandled-exception-notification.png)

Für die Benutzererfahrung ist es vorteilhafter, wenn eine Anwendung dieses Standardverhalten vermeidet. Dazu dienen mehrere oder alle der folgenden Aktionen:

- Anzeigen von benutzerfreundlichen Informationen

- Versuchen, eine Anwendung weiterhin auszuführen

- Aufzeichnen detaillierter, Entwickler freundlicher Ausnahme Informationen im Windows-Ereignisprotokoll.

Die Implementierung dieser Unterstützung ist davon abhängig, dass nicht behandelte Ausnahmen erkannt werden können. Dies ist das, wofür das <xref:System.Windows.Application.DispatcherUnhandledException> Ereignis ausgelöst wird.

[!code-xaml[detecting-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]

[!code-csharp[code-to-detect-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs)]
[!code-vb[code-to-detect-unhandled-exceptions](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb)]

Dem <xref:System.Windows.Application.DispatcherUnhandledException>-Ereignishandler wird ein <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> Parameter übergeben, der Kontextinformationen bezüglich der nicht behandelten Ausnahme enthält, einschließlich der Ausnahme selbst (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>). Sie können anhand dieser Informationen feststellen, wie die Ausnahme behandelt werden soll.

Wenn Sie <xref:System.Windows.Application.DispatcherUnhandledException>behandeln, sollten Sie die <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType>-Eigenschaft auf `true`festlegen. Andernfalls wird die Ausnahme von WPF weiterhin als nicht behandelt betrachtet, und das zuvor beschriebene Standardverhalten wird wieder hergestellt. Wenn eine nicht behandelte Ausnahme ausgelöst wird und entweder das <xref:System.Windows.Application.DispatcherUnhandledException>-Ereignis nicht behandelt wird oder das Ereignis behandelt wird und <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> auf `false`festgelegt ist, wird die Anwendung sofort heruntergefahren. Darüber hinaus werden keine anderen <xref:System.Windows.Application> Ereignisse ausgelöst. Folglich müssen Sie <xref:System.Windows.Application.DispatcherUnhandledException> behandeln, wenn Ihre Anwendung über Code verfügt, der ausgeführt werden muss, bevor die Anwendung heruntergefahren wird.

Obwohl eine Anwendung wegen einer nicht behandelten Ausnahme heruntergefahren werden kann, erfolgt das Herunterfahren normalerweise als Reaktion auf eine Benutzeranforderung, wie im nächsten Abschnitt beschrieben.

<a name="Application_Lifetime_Events"></a>

### <a name="application-lifetime-events"></a>Anwendungslebensdauer-Ereignisse

Eigenständige Anwendungen und XBAPs haben nicht genau die gleiche Lebensdauer. Die folgende Abbildung veranschaulicht die wichtigsten Ereignisse in der Lebensdauer einer eigenständigen Anwendung und die Reihenfolge, in der sie ausgelöst werden.

![Ereignisse für &#45; eigenständige Anwendungs Objekte](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")

Die folgende Abbildung veranschaulicht die wichtigsten Ereignisse in der Lebensdauer einer XBAP und zeigt die Reihenfolge an, in der Sie ausgelöst werden.

![Ereignisse für &#45; XBAP-Anwendungs Objekt](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Application>
- [Übersicht über WPF-Fenster](wpf-windows-overview.md)
- [Übersicht über die Navigation](navigation-overview.md)
- [WPF-Anwendungsressource, Inhalts- und Datendateien](wpf-application-resource-content-and-data-files.md)
- [Paket-URI in WPF](pack-uris-in-wpf.md)
- [Anwendungsmodell: Themen zur Vorgehensweise](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))
- [Anwendungsentwicklung](index.md)
