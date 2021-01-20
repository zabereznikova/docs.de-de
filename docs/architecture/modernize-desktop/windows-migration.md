---
title: Migration von Windows 10
description: Ausführliche Einblicke in Windows 10-Features, wie z. b. Verpacken und XAML-Inseln.
ms.date: 12/29/2020
ms.openlocfilehash: 139a8f2354803dafeb0178b4dbfb57a95c4ddb34
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615944"
---
# <a name="windows-10-migration"></a>Migration von Windows 10

Beachten Sie die folgende Situation: Sie verfügen über eine funktionierende Desktop Anwendung, die in den Windows 7 Tagen entwickelt wurde. Es verwendet die WPF-Technologie, die zu diesem Zeitpunkt verfügbar ist und einwandfrei funktioniert, aber eine veraltete Benutzeroberfläche und ein Verhalten aufweist, wenn Sie es unter Windows 10 ausführen. Es ist so, als ob Sie sich einen futuristischen Film wie Matrix ansehen und mit dem Nokia 8110-Gerät "Neo" sehen. Der Film funktioniert seit 20 Jahren hervorragend, aber er wäre von einer Geräte Modernisierung aus vorteilhaft.

Seit der Veröffentlichung von Windows 10 hat Microsoft viele Innovationen eingeführt, um Szenarios wie Tablets und Touchscreen zu unterstützen und die Benutzer für ein Microsoft-Betriebssystem eine optimale Benutzerumgebung bereitzustellen. Beispielsweise können Sie folgende Aktionen ausführen:

- Melden Sie sich mit Windows Hello bei ihrer Oberfläche an.
- Verwenden Sie einen Stift, um Text zu zeichnen oder zu schreiben, der automatisch erkannt und digitalisiert wird.
- Ausführen von lokal angepassten Ki-Modellen, die mit winml in der Cloud erstellt wurden.

Alle diese Features sind für Windows-Entwickler über Windows-Runtime (WinRT)-Bibliotheken aktiviert. Sie können diese Features in Ihren vorhandenen Desktop-Apps nutzen, da die Bibliotheken sowohl für den .NET Framework als auch für .net verfügbar gemacht werden. Sie können Ihre Benutzeroberfläche sogar mit der Verwendung von XAML-Inseln modernisieren und die visuellen Elemente und das Verhalten Ihrer apps entsprechend den Zeitpunkten verbessern.

Beachten Sie, dass Sie .NET Framework Technologie nicht verwerfen müssen, um diesem Modernisierungspfad zu folgen. Sie können auf sichere Weise auf dem neuesten Stand bleiben und alle Vorteile von Windows 10 nutzen, ohne den Druck auf .net zu migrieren. So erhalten Sie sowohl die Leistung als auch die Flexibilität, ihren Modernisierungspfad auszuwählen.

## <a name="winrt-apis"></a>WinRT-APIs

WinRT-APIs sind objektorientierte, gut strukturierte Anwendungs Programmierschnittstellen (Application Programming Interfaces, APIs), die Windows 10-Entwicklern den Zugriff auf alles ermöglichen, was das Betriebssystem bietet. Mit WinRT-APIs können Sie Funktionen wie Pushbenachrichtigungen, Geräte-APIs, Microsoft Ink und winml unter anderem in Ihre Desktop-Apps integrieren.

Im Allgemeinen können WinRT-APIs von einer klassischen Desktop-App aus aufgerufen werden. Zwei Hauptbereiche stellen jedoch eine Ausnahme von dieser Regel dar:

* APIs, die eine Paket Identität erfordern.
* APIs, die Visualisierungen wie XAML oder Komposition erfordern.

### <a name="universal-windows-platform-uwp-packages"></a>Universelle Windows-Plattform (UWP)-Pakete

#### <a name="application-package-identity"></a>Identität des Anwendungspakets

UWP-apps verfügen über ein Bereitstellungs System, in dem das Betriebssystem die Installation und die Installation der Anwendung verwaltet. Dies erfordert, dass die Installation deklarativ ist, was bedeutet, dass während der Installation kein Benutzercode ausgeführt wird. Stattdessen wird alles, was die app in das System integrieren möchte, z. b. Protokolle, Dateitypen und Erweiterungen, im Anwendungs Manifest deklariert. Zum Zeitpunkt der Bereitstellung werden diese Integrationspunkte von der Bereitstellungs Pipeline konfiguriert. Die einzige Möglichkeit für das Betriebssystem, diese Funktionalität zu verwalten und zu verfolgen, besteht darin, dass jedes Paket über eine Identität verfügt, ein eindeutiger Bezeichner für die Anwendung.

Einige WinRT-APIs erfordern, dass diese Paket Identität erwartungsgemäß funktioniert. Klassische Desktop-Apps wie native C++ oder .net-apps verwenden jedoch unterschiedliche Bereitstellungs Systeme, die keine Paket Identität erfordern. Wenn Sie diese WinRT-APIs in der Desktop Anwendung verwenden möchten, müssen Sie Ihnen eine Paket Identität bereitstellen.

Eine Möglichkeit zum Fortfahren besteht darin, ein zusätzliches Paket Projekt zu erstellen. Innerhalb des Paket Projekts zeigen Sie auf das ursprüngliche Quell Code Projekt und geben die Identitätsinformationen an, die Sie bereitstellen möchten. Wenn Sie das Paket installieren und die installierte app ausführen, erhält es automatisch eine Identifizierung, die dem Code ermöglicht, alle WinRT-APIs aufzurufen, für die eine Identität erforderlich ist.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Package xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
         xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10">
    <Identity Name="YOUR-APP-GUID "
              Publisher="CN=YOUR COMPANY"
              Version="1.x.x.x" />
</Package>
```

Sie können überprüfen, welche APIs eine gepackte Anwendungs Identität benötigen, indem Sie überprüfen, ob der Typ, der die API enthält, mit dem [dualapipartition](xref:Windows.Foundation.Metadata.DualApiPartitionAttribute) -Attribut markiert ist. Wenn dies der Fall ist, können Sie bei einer nicht gepackten, herkömmlichen Desktop-App den Befehl von abrufen. Andernfalls müssen Sie Ihre klassische Desktop-App mithilfe eines Paket Projekts in eine UWP konvertieren.

<https://docs.microsoft.com/windows/desktop/apiindex/uwp-apis-callable-from-a-classic-desktop-app>

#### <a name="benefits-of-packaging"></a>Vorteile der Paket Erstellung

Neben dem Zugriff auf diese APIs erhalten Sie einige zusätzliche Vorteile, indem Sie ein Windows-App-Paket für Ihre Desktop Anwendung erstellen, einschließlich der folgenden:

* **Optimierte Bereitstellung**. Apps haben eine großartige Bereitstellung, um sicherzustellen, dass Benutzer eine Anwendung zuverlässig installieren und aktualisieren können. Wenn ein Benutzer die APP deinstallieren möchte, wird er vollständig entfernt, ohne dass eine Ablauf Verfolgung übrig bleibt, um das Windows-rot-Problem zu verhindern.

* **Automatische Updates und Lizenzierung**. Ihre Anwendung kann an den integrierten Lizenzierungs-und automatischen Update Funktionen der Microsoft Store teilnehmen. Automatische Updates stellen einen sehr zuverlässigen und effizienten Mechanismus dar, da nur die geänderten Teile von Dateien heruntergeladen werden.

* **Erweiterte Reichweite und vereinfachte Monetarisierung**. Vielleicht nicht in Ihrem Fall, aber wenn Sie Ihre Anwendung über die Microsoft Store verteilen, erreichen Sie Millionen von Windows 10-Benutzern.

* **Hinzufügen von UWP-Features**. Sie können dem Paket Ihrer APP UWP-Features in Ihrem eigenen Tempo hinzufügen.

#### <a name="prepare-for-packaging"></a>Vorbereiten der Paket Erstellung

Bevor Sie mit dem Verpacken der Desktop Anwendung fortfahren, müssen Sie vor dem Starten des Prozesses einige Punkte berücksichtigen. Die Anwendung muss jede der Microsoft Store Regeln und Richtlinien berücksichtigen und im UWP-Anwendungsmodell ausgeführt werden. Beispielsweise muss Sie auf dem .NET Framework 4.6.2 oder höher ausgeführt werden und in die Registrierungs Struktur schreiben, `HKEY_CURRENT_USER` und die AppData-Ordner werden zu einem benutzerspezifischen lokalen app-Speicherort virtualisiert.

Das Entwurfs Ziel für die Paket Erstellung besteht darin, den Anwendungs Zustand vom Systemstatus zu trennen und gleichzeitig die Kompatibilität mit anderen apps aufrechtzuerhalten. Windows 10 erreicht dieses Ziel durch Platzieren der Anwendung in einem UWP-Paket. Es erkennt und leitet einige Änderungen an das Dateisystem und die Registrierung zur Laufzeit um, um die Zusage eines vertrauenswürdigen und sauberen Installations-und Deinstallations Verhaltens einer Anwendung zu erfüllen, die von der Verpackung bereitgestellt wird.

Pakete, die Sie für Ihre Desktop Anwendung erstellen, sind Desktop-only-Anwendungen mit voller Vertrauenswürdigkeit, die nicht in einem Sandkasten vorhanden sind, obwohl eine vereinfachte Virtualisierung auf die APP angewendet wird, um Schreibvorgänge in `HKCU` und auszuführen `AppData` . Diese Virtualisierung ermöglicht es Ihnen, mit anderen apps auf die gleiche Weise wie klassische Desktop Anwendungen zu interagieren.

##### <a name="installation"></a>Installation

App-Pakete werden unter *% Program Files% \\ Windowsapps \\ package_name* installiert, wobei die ausführbare Datei mit dem Titel verwendet wird `app_name.exe` . Jeder Paket Ordner enthält ein Manifest (mit dem Namen `AppxManifest.xml` ), das einen speziellen XML-Namespace für App-Pakete enthält. In der Manifestdatei ist ein `<EntryPoint>`-Element enthalten, das auf die vertrauenswürdige App verweist. Wenn diese Anwendung gestartet wird, wird Sie nicht in einem App-Container ausgeführt, sondern stattdessen als Benutzer ausgeführt.

Nach der Bereitstellung werden Paketdateien als schreibgeschützt markiert und vom Betriebssystem gesperrt. Windows verhindert, dass Apps gestartet werden, wenn diese Dateien manipuliert werden.

##### <a name="file-system"></a>Dateisystem

Das Betriebssystem unterstützt abhängig vom Speicherort des Ordners verschiedene Ebenen von Dateisystem Vorgängen für gepackte Desktop Anwendungen.

Wenn Sie versuchen, auf den *AppData* -Ordner des Benutzers zuzugreifen, erstellt das System einen privaten pro-Benutzer-pro-App-Standort im Hintergrund. Dadurch wird die Illusion erstellt, dass die gepackte Anwendung die echten *AppData* bearbeitet, wenn eine private Kopie tatsächlich geändert wird. Durch eine derartige Umleitung von Schreibvorgängen kann das System alle von der App vorgenommenen Dateiänderungen nachverfolgen. Sie kann dann alle Dateien bereinigen, wenn Sie das Reduzieren des Systems "rot" deinstallieren und einen besseren Anwendungs Entfernungs Vorgang für den Benutzer bereitstellen.

##### <a name="registry"></a>Registrierung

App-Pakete enthalten die Datei "Registry. dat", die als logische Entsprechung von `HKLM\Software` in der tatsächlichen Registrierung fungiert. Zur Laufzeit führt diese virtuelle Registrierung den Inhalt dieser Struktur in der nativen Systemstruktur zusammen, um beide Strukturen in einer Ansicht darzustellen.

Alle Schreibvorgänge werden während des Paket Upgrades aufbewahrt und nur bei der Deinstallation der Anwendung gelöscht.

##### <a name="uninstallation"></a>Deinstallation

Wenn der Benutzer ein Paket deinstalliert, werden alle Dateien und Ordner entfernt, die sich unter befinden, sowie alle `C:\Program Files\WindowsApps\package_name` umgeleiteten Schreibvorgänge in APPDATA oder die Registrierung, die während des Prozesses aufgezeichnet wurden.

Ausführliche Informationen dazu, wie eine Paket Anwendung die Installation, den Dateizugriff, die Registrierung und die Deinstallation übernimmt, finden Sie unter <https://docs.microsoft.com/windows/msix/desktop/desktop-to-uwp-behind-the-scenes> .

Sie können eine komplette Liste der zu über Check enden Elemente erhalten <https://docs.microsoft.com/windows/msix/desktop/desktop-to-uwp-prepare> .

## <a name="how-to-add-winrt-apis-to-your-desktop-project"></a>Vorgehensweise beim Hinzufügen von WinRT-APIs zu Ihrem Desktop Projekt

In diesem Abschnitt finden Sie eine exemplarische Vorgehensweise zum Integrieren von Popup Benachrichtigungen in eine vorhandene WPF-Anwendung. Obwohl es aus der Code Perspektive einfach ist, ist es hilfreich, den gesamten Prozess zu veranschaulichen. Benachrichtigungen sind eine der vielen verfügbaren WinRT-APIs, die Sie in der .net-App verwenden können. In diesem Fall erfordert die API eine Paket Identität. Dieser Prozess ist einfacher, wenn für die APIs keine Paket Identität erforderlich ist.

Nehmen wir nun eine vorhandene WPF-Beispiel-APP, die Dateien liest und ihren Inhalt auf dem Bildschirm anzeigt. Ziel ist es, eine Popup Benachrichtigung anzuzeigen, wenn die Anwendung gestartet wird.

![Screenshot der Beispielanwendung, die ausgeführt wird](./media/windows-migration/sample-application.png)

Überprüfen Sie zunächst den folgenden Link, ob für die Windows 10-API, die Sie verwenden, eine Paket Identität erforderlich ist:

<https://docs.microsoft.com/windows/apps/desktop/modernize/desktop-to-uwp-supported-api>

In unserem Beispiel wird die <xref:Windows.UI.Notifications.Notification?displayProperty=nameWithType> API verwendet, die eine gepackte Identität erfordert:

![Benachrichtigungs Klasse in der Microsoft-Dokumentation](./media/windows-migration/notification-class-documentation.png)

Um auf die WinRT-API zuzugreifen, fügen Sie einen Verweis auf das `Microsoft.Windows.SDK.Contracts` nuget-Paket hinzu, und dieses Paket führt die Magie hinter den Kulissen aus (Weitere Informationen finden Sie unter <https://blogs.windows.com/windowsdeveloper/2019/04/30/calling-windows-10-apis-from-a-desktop-application-just-got-easier/> ).

Sie sind nun bereit, Code hinzuzufügen.

Erstellen Sie eine `ShowToastNotification` Methode, die beim Starten der Anwendung aufgerufen wird. Es erstellt lediglich eine Popup Benachrichtigung aus einem XML-Muster:

```csharp
private void ShowNotification(string title, string content, string image)
{
    string xmlString = $@"<toast><visual><binding template = 'ToastGeneric'><text>{title}</text><text>{content}</text><image src=>'{image}'</image></binding></visual></toast>";
    XmlDocument toastXml = new XmlDocument();
    toastXml.LoadXml(xmlString);
    ToastNotification toast = new ToastNotification(toastXml);
    ToastNotificationManager.CreateToastNotifier().Show(toast);
}
```

Obwohl das Projekt erstellt wird, treten Fehler auf, da die Benachrichtigungs-API eine Paket Identität erfordert, die Sie nicht bereitgestellt haben. Durch das Hinzufügen eines Windows-Paket Erstellungs Projekts zur Projekt Mappe wird das Problem behoben:

![Screenshot des Dialog Felds "Neues Projekt hinzufügen" in Visual Studio](./media/windows-migration/add-packaging-project.png)

Wählen Sie die Windows-Mindestversion aus, die Sie unterstützen möchten, sowie die Version, auf die Sie abzielen Nicht alle WinRT-APIs werden in allen Windows 10-Versionen unterstützt. Mit jedem Windows 10-Update werden neue APIs hinzugefügt, die nur aus dieser Version verfügbar sind. Unterstützung für Unterstützung ist nicht verfügbar.

![Auswählen der minimalen Windows-Version](./media/windows-migration/select-versions.png)

Der nächste Schritt besteht darin, die WPF-Anwendung durch Hinzufügen eines Projekt Verweises zum Windows-Paket Erstellungs Projekt hinzuzufügen:

![Hinzufügen einer WPF-Anwendung zum Windows-Paket Erstellungs Projekt](./media/windows-migration/add-application.png)

![Verweis-Manager](./media/windows-migration/reference-manager.png)

Ein Windows-Paket Erstellungs Projekt kann mehrere apps Verpacken, damit Sie festlegen können, welches der Einstiegspunkt ist:

![Einstiegspunkt wird festgelegt](./media/windows-migration/set-entry-point.png)

Der nächste Schritt besteht darin, das WPF-Projekt als Startprojekt in der Projektmappenkonfiguration festzulegen. Sie können F5 drücken, um die Ergebnisse zu kompilieren und zu erstellen und anzuzeigen.

![Beispielanwendung, die ausgeführt wird und Ergebnisse anzeigt](./media/windows-migration/sample-app-result.png)

Nun generieren wir das Paket, damit Sie die APP installieren können. Klicken **Sie mit der** rechten Maustaste auf App-  >  **Pakete erstellen**.

![Dialogfeld App-Pakete erstellen](./media/windows-migration/create-app-packages.png)

Wählen Sie die Option Sideload aus, um die APP auf Ihrem Computer bereitzustellen:

![Auswählen der Option "Sideload"](./media/windows-migration/select-sideloading-option.png)

Wählen Sie die Anwendungsarchitektur Ihrer APP aus:

![Auswählen der Anwendungsarchitektur](./media/windows-migration/select-app-architecture.png)

Erstellen Sie abschließend das Paket, indem Sie auf **Erstellen** klicken.

## <a name="xaml-islands"></a>XAML Islands

XAML-Inseln sind eine Reihe von Komponenten, mit denen Windows-Desktop Entwickler UWP-XAML-Steuerelemente in Ihren vorhandenen Win32-Anwendungen verwenden können, einschließlich Windows Forms und WPF.

![Struktur der XAML-Inseln](./media/windows-migration/xaml-islands.png)

Sie können Ihre Win32-App mit ihren standardmäßigen Steuerelementen und einer "Insel" der UWP-Benutzeroberfläche, die Steuerelemente aus der modernen Welt enthält, Abbildern. Das Konzept ähnelt dem vorhanden sein eines IFRAMEs innerhalb einer Webseite, das Inhalte aus einem `different page.`

Neben dem Hinzufügen von Funktionen aus den Windows 10-APIs können Sie in ihrer App mithilfe von XAML-Inseln Teile von UWP-XAML hinzufügen.

Windows 10 1903 Update führt eine Reihe von APIs ein, die das Hosting von UWP-XAML-Inhalten in Win32-Fenstern ermöglichen. Nur apps, die unter Windows 10 1903 ausgeführt werden, können XAML-Inseln verwenden.

### <a name="the-road-to-xaml-islands"></a>Der Weg zu XAML-Inseln

Der Weg zu XAML-Inseln wurde in 2012 gestartet, als Microsoft die WinRT-APIs als Rahmen für die Modernisierung der Win32-Apps (Windows Forms, WPF und Native Win32-Apps) eingeführt hat. Die neuen UI-Steuerelemente in WinRT waren jedoch für neue Anwendungen verfügbar, aber nicht für vorhandene.

In 2015 wurde UWP zusammen mit Windows 10 geboren. UWP ermöglicht Ihnen das Erstellen von apps, die auf Windows-Geräten wie Xbox, Mobile und Desktop funktionieren. Ein Jahr später kündigte Microsoft Desktop Bridge (früher als Project Centennial bezeichnet) an. Desktop Bridge ist ein Satz von Tools, mit denen Entwickler ihre vorhandenen Win32-apps in das Microsoft Store bringen konnten. Weitere Funktionen wurden in 2017 hinzugefügt, sodass Entwickler ihre Win32-apps verbessern können, indem Sie einige der neuen Windows 10-APIs nutzen, wie Live-Kacheln und Benachrichtigungen im Aktions Center. Es gibt jedoch noch keine neuen UI-Steuerelemente.

An Build 2018 hat Microsoft eine Möglichkeit für Entwickler angekündigt, die neuen Windows 10-XAML-Steuerelemente in ihren aktuellen Win32-apps zu verwenden, ohne Ihre apps vollständig zu UWP zu migrieren. Es wurde als UWP-XAML-Inseln bezeichnet.

### <a name="how-it-works"></a>Funktionsweise

Das Windows 10 1903-Update führt mehrere XAML-Hosting-APIs ein. Zwei davon sind `WindowsXamlManager` und `DesktopWindowXamlSource` .

Die- `WindowsXamlManager` Klasse behandelt das UWP-XAML-Framework. Die zugehörige- `InitializeForCurrentThread` Methode lädt das UWP-XAML-Framework in den aktuellen Thread der Win32-app.

Der `DesktopWindowXamlSource` ist die Instanz des XAML-Insel Inhalts. Sie verfügt über die `Content` -Eigenschaft, die Sie für die Instanziierung und die-Einstellung verantwortlich sind. Das `DesktopWindowXamlSource` rendert und ruft seine Eingabe von einem HWND ab. Der IT-Bereich muss wissen, welcher andere HWND das Verzeichnis der XAML-Insel anfügt, und Sie sind verantwortlich für die Größenanpassung und Positionierung des HWND des übergeordneten Elements.

WPF-oder Windows Forms Entwickler arbeiten in der Regel nicht mit HWND innerhalb Ihres Codes. Daher kann es schwierig sein, die HWND-Zeiger zu verstehen und zu verarbeiten und die zugrunde liegenden Verdrahtungs Möglichkeiten für die Kommunikation zwischen Win32-und UWP-Welten

#### <a name="the-xaml-islands-net-wrappers"></a>Die .net-Wrapper für XAML-Inseln

Das Windows Community Toolkit verfügt über einen Satz der XAML-Inseln .net-Wrapper für WPF oder Windows Forms, die die Verwendung von XAML-Inseln vereinfachen. Diese Wrapper verwalten u. a. die HWNDs, die Fokus Verwaltung. Windows Forms-und WPF-Entwickler sollten diese Wrapper verwenden.

Das Windows Community Toolkit bietet zwei Arten von Steuerelementen: umschließende Steuerelemente und hostingsteuerelemente.

##### <a name="wrapped-controls"></a>Umschließt Steuerelemente

Diese umschließenden Steuerelemente umschließen einige UWP-Steuerelemente in Windows Forms-oder WPF-Steuerelemente und verbergen UWP-Konzepte für diese Entwickler Diese Steuerelemente lauten wie folgt:

* WebView und webviewcompatible
* InkCanvas und inktoolbar
* MediaPlayerElement
* MapControl

Fügen `Microsoft.Toolkit.Wpf.UI.Controls` Sie das Paket zu Ihrem Projekt hinzu, fügen Sie den Verweis auf den Namespace ein, und beginnen Sie mit der Verwendung.

```xml
<Window
        ...
        xmlns:uwpControls="clr-namespace:Microsoft.Toolkit.Wpf.UI.Controls;assembly=Microsoft.Toolkit.Wpf.UI.Controls">
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="Auto"/>
        <RowDefinition Height="\*"/>
    </Grid.RowDefinitions>
    <uwpControls:InkToolbar TargetInkCanvas="{x:Reference Name=inkCanvas}"/>
    <uwpControls:InkCanvas Grid.Row="1" x:Name="inkCanvas" />
</Grid>
```

##### <a name="hosting-controls"></a>Hosting-Steuerelemente

Die Leistungsfähigkeit von XAML-Inseln erstreckt sich auf die meisten Steuerelemente von Drittanbietern, Steuerelemente von Drittanbietern und benutzerdefinierte Steuerelemente, die für UWP entwickelt wurden, die in Windows Forms und WPF als "Inseln" mit vollständiger funktionaler Benutzeroberfläche integriert werden können. Das `WindowsXamlHost` Steuerelement für WPF und Windows Forms ermöglicht dies.

Um z. b. das- `WindowsXamlHost` Steuerelement in WPF zu verwenden, fügen Sie einen Verweis auf das Paket hinzu, das `Microsoft.Toolkit.Wpf.UI.XamlHost` vom Windows Community Toolkit bereitgestellt wird.

Nachdem Sie Ihren Benutzeroberflächen `WindowsXamlHost` Code eingefügt haben, geben Sie den UWP-Typ an, den Sie laden möchten. Sie können ein umgesetztes Steuerelement wie ein `Button` oder ein komplexeres Steuerelement verwenden, das von mehreren verschiedenen Steuerelementen, einem benutzerdefinierten UWP-Steuerelement, besteht.

Im folgenden Beispiel wird gezeigt, wie eine UWP hinzugefügt wird `Button` :

```xml
<Window
        ...
        xmlns:xamlhost="clr-namespace:Microsoft.Toolkit.Wpf.UI.XamlHost;assembly=Microsoft.Toolkit.Wpf.UI.XamlHost">

<xamlhost:WindowsXamlHost x:Name="myUwpButton"
                          InitialTypeName="Windows.UI.Xaml.Controls.Button" />
```

Es gibt eine klare Empfehlung für diese Vorgehensweise. es ist besser, eine einzige und größere XAML-Insel mit einem benutzerdefinierten zusammengesetzten Steuerelement zu haben, als mehrere Inseln mit jeweils einem Steuerelement aufweisen.

Eines der wichtigsten Features von XAML ist die Bindung und funktioniert zwischen Ihrem Win32-Code und der Insel. Sie können also beispielsweise eine Win32-Verbindung `Textbox` mit einer UWP binden `Textbox` . Ein wichtiger Aspekt ist, dass diese Bindungen unidirektionale Bindungen, von UWP zu Win32, sind. Wenn Sie also das `Textbox` in der XAML-Insel aktualisieren, wird das Win32-Textfeld aktualisiert, aber nicht umgekehrt.

Eine exemplarische Vorgehensweise zur Verwendung von XAML-Inseln finden Sie unter:

<https://docs.microsoft.com/windows/apps/desktop/modernize/host-standard-control-with-xaml-islands>

#### <a name="adding-uwp-xaml-custom-controls"></a>Hinzufügen benutzerdefinierter UWP XAML-Steuerelemente

Ein benutzerdefiniertes XAML-Steuerelement ist ein Steuerelement (oder ein Benutzer Steuerelement), das von Ihnen oder von Dritten (einschließlich WinUI 2. x-Steuerelementen) erstellt wurde Um ein benutzerdefiniertes UWP-Steuerelement in einer Windows Forms-oder WPF-App zu hosten, benötigen Sie Folgendes:

- Um das `WindowsXamlHost` UWP-Steuerelement in Ihrer .net-APP zu verwenden.
- Zum Erstellen eines UWP-App-Projekts, das ein- `XamlApplication` Objekt definiert.

Ihr WPF-oder Windows Forms Projekt muss Zugriff auf eine Instanz der-Klasse haben, die `Microsoft.Toolkit.Win32.UI.XamlHost.XamlApplication` vom Windows Community Toolkit bereitgestellt wird. Dieses Objekt fungiert als Stamm-Metadatenanbieter zum Laden von Metadaten für benutzerdefinierte UWP-XAML-Typen in Assemblys im aktuellen Verzeichnis der Anwendung. Die empfohlene Vorgehensweise besteht darin, ein leeres App-Projekt (Universal Windows) zur gleichen Projekt Mappe wie das WPF-oder Windows Forms Projekt hinzuzufügen und die Standard-App-Klasse in diesem Projekt zu überarbeiten.

Das benutzerdefinierte UWP-XAML-Steuerelement kann in diese UWP-APP oder in ein unabhängiges UWP-Klassen Bibliotheksprojekt eingeschlossen werden, auf das Sie in derselben Projekt Mappe wie das WPF-oder Windows Forms-Projekt verweisen.

Eine ausführliche Schritt-für-Schritt-Prozessbeschreibung finden Sie unter:

<https://docs.microsoft.com/windows/apps/desktop/modernize/host-custom-control-with-xaml-islands>

#### <a name="the-windows-ui-library-winui-2"></a>Die Bibliothek der Windows-Benutzeroberfläche (WinUI 2)

Neben dem Windows 10-Eingangsbox-Steuerelement, das im Betriebssystem verfügbar ist, stellt dasselbe UWP-XAML-Team auch zusätzliche Steuerelemente in der Windows-Benutzeroberflächen Bibliothek (**WinUI 2**) WinUI 2 stellt offizielle Native Microsoft UI-Steuerelemente und-Features für Windows UWP-apps bereit, und diese Steuerelemente können innerhalb von XAML-Inseln verwendet werden.

WinUI 2 ist Open Source, und Sie finden Informationen unter <https://github.com/microsoft/microsoft-ui-xaml> .

Der folgende Artikel veranschaulicht das Hosten eines UWP-XAML-Steuer Elements aus der WinUI 2-Bibliothek: <https://docs.microsoft.com/windows/apps/desktop/modernize/host-custom-control-with-xaml-islands>

### <a name="do-you-need-xaml-islands"></a>Benötigen Sie XAML-Inseln

XAML-Inseln sind für vorhandene Win32-apps gedacht, die Ihre Benutzer Leistung verbessern möchten, indem Sie neue UWP-Steuerelemente und Verhaltensweisen nutzen, ohne dass die APP vollständig umgeschrieben wird. Sie können bereits [Windows 10-APIs nutzen](/windows/uwp/porting/desktop-to-uwp-enhance), aber bis hin zu XAML-Inseln, nur nicht-UI-bezogene APIs.

Wenn Sie eine neue Windows-App entwickeln, ist die [UWP-App](/windows/uwp/get-started/universal-application-platform-guide) wahrscheinlich der richtige Ansatz.

### <a name="the-road-ahead-xaml-islands-winui-30"></a>The Road Ahead XAML Islands: WinUI 3,0

Seit Windows 8 wurde die Windows-Benutzeroberflächen Plattform, einschließlich des XAML-UI-Frameworks, der visuellen Kompositions Schicht und der Eingabe Verarbeitung, als integraler Bestandteil von Windows ausgeliefert. Dies bedeutet, dass Sie ein Upgrade auf die neueste Version der Benutzeroberfläche durchführen müssen, um von den neuesten Verbesserungen an den Benutzeroberflächen Technologien profitieren zu können, um die Innovationsgeschwindigkeit bei der Entwicklung Ihrer apps zu verlangsamen. Um diese beiden Entwicklungszyklen zu entkoppeln und Innovationen zu fördern, arbeitet Microsoft aktiv mit dem WinUI-Projekt.

Ab WinUI 2 in 2018 begann Microsoft, einige neue XAML-UI-Steuerelemente und-Features als separate nuget-Pakete zu versenden, die auf dem UWP SDK aufbauen.

![Struktur von WinUI 2,0](./media/windows-migration/winui2.png)

WinUI 3 befindet sich in der aktiven Entwicklung und erweitert den Bereich von WinUI erheblich um die vollständige UI-Plattform, die vollständig vom UWP SDK entkoppelt wird:

![Struktur von WinUI 3,0](./media/windows-migration/winui3.png)

Das XAML-Framework wird nun auf GitHub entwickelt und als [nuget](/nuget/what-is-nuget) -Pakete out-of-Band ausgeliefert.

Die bestehenden UWP-XAML-APIs, die als Teil des Betriebssystems bereitgestellt werden, erhalten keine neuen Featureupdates mehr. Sie erhalten weiterhin Sicherheitsupdates und wichtige Korrekturen gemäß dem Windows 10-Support-Lebenszyklus.

Der universelle Windows-Plattform enthält mehr als nur das XAML-Framework (z. b. Anwendungs-und Sicherheitsmodell, Medien Pipeline, Xbox-und Windows 10-shellintegrationen, umfassende Geräte Unterstützung) und wird weiterentwickelt. Alle neuen XAML-Funktionen werden einfach entwickelt und als Teil von WinUI ausgeliefert.

#### <a name="winui-3-in-desktop-app-and-winui-xaml-islands"></a>WinUI 3 in Desktop-App und WinUI-XAML-Inseln

Wie Sie sehen können, ist WinUI 3 die Entwicklung von UWP XAML und funktioniert im UWP-App-Modell und allen Anforderungen (msix-Paket-ID, Sandbox, corewindow usw.). Um nur WinUI 3 in einem Win32-App-Modell zu verwenden, sollte der WinUI-Inhalt von einem anderen Benutzeroberflächen Framework (Windows Forms, WPF usw.) mithilfe von **WinUI-XAML-Inseln** gehostet werden. Dies ist der richtige Pfad, wenn Sie Ihre APP-und Mischungs Technologien weiterentwickeln möchten. Wenn Sie jedoch Ihre gesamte alte Benutzeroberfläche für WinUI ersetzen möchten, sollte Ihre APP keine UI-Frameworks für das Hosting von WinUI laden.

WinUI 3 behandelt dieses wichtige Feedback zum Hinzufügen von **WinUI in Desktop-Apps**. Dies ermöglicht, dass Win32-apps WinUI 3 als eigenständiges Benutzeroberflächen-Framework verwenden können. Windows Forms oder WPF muss nicht geladen werden.

In dieser Aggregation ermöglicht WinUI 3 Entwicklern das einfache kombinieren und Abgleichen der richtigen Kombination aus:

* App-Modell: UWP, Win32
* Plattform: .net oder System eigen
* Sprache: .net (C \# , Visual Basic), Standard C++
* Verpacken: msix, AppX für den Microsoft Store, nicht gepackt
* Interop: Verwenden Sie WinUI 3 zum Erweitern vorhandener WPF-, WinForms-und MFC-Apps mithilfe von WinUI-XAML-Inseln.

Wenn Sie weitere Informationen wünschen, gibt Microsoft diese Roadmap in frei <https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md> .

>[!div class="step-by-step"]
>[Zurück](migrate-modern-applications.md)
>[Weiter](example-migration.md)
