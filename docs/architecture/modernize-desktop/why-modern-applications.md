---
title: Gründe für moderne Desktop-Apps
description: Erfahren Sie mehr über Desktop Technologien wie Windows Forms, WPF und UWP in der modernen Welt.
ms.date: 09/16/2019
ms.openlocfilehash: f8b70ba9e0ee97a6e0938e3219ecd0d2324248ae
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "97866486"
---
# <a name="why-modern-desktop-applications"></a>Gründe für moderne Desktop-Apps

## <a name="introduction"></a>Einführung

### <a name="a-story-of-one-company"></a>Eine Story von einem Unternehmen

In den frühen 2000er Jahren begann ein multinationales Unternehmen damit, eine verteilte Desktop Lösung zu entwickeln, mit der Informationen zwischen verschiedenen Verzweigungen des Unternehmens ausgetauscht und optimierte Vorgänge auf zentralisierten Einheiten ausgeführt werden können. Sie haben für Ihre Anwendungsentwicklung ein ganz neues Framework namens Windows Forms (auch als WinForms bezeichnet) ausgewählt. Im Laufe der Jahre hat sich das Projekt in einer ausgereiften, gut getesteten und Zeit erprobten Anwendung mit Hunderttausenden von Codezeilen entwickelt. Die Zeit, die vergangen ist, und .NET Framework 2,0 ist nicht mehr die neue neue Technologie. Die Entwickler, die an dieser Anwendung arbeiten, sind ein Problem. Sie möchten die neuesten Technologien in ihrer Entwicklung verwenden und Ihre Anwendung aussehen und sich als modern ansehen. Gleichzeitig möchten Sie nicht das großartige Produkt, das Sie in 15 Jahren erstellt haben, auslösen und die gesamte Anwendung von Grund auf neu schreiben.

### <a name="your-story"></a>Ihre Story

Sie finden sich möglicherweise auf demselben Boot, in dem Sie ausgereifte Windows Forms oder Windows Presentation Foundation (WPF)-Anwendungen haben, die ihre Zuverlässigkeit im Laufe der Jahre bewiesen haben. Sie möchten diese Anwendungen wahrscheinlich noch viele weitere Jahre verwenden. Da diese Anwendungen schon vor einiger Zeit geschrieben wurden, haben Sie möglicherweise fehlende Funktionen wie modernes Aussehen, Leistung, Integration in neue Geräte und Platt Form Features usw., wodurch Sie sich "alte Technologie" fühlen. Es gibt ein weiteres Problem, das Sie als Entwickler in Frage kommen könnte. Beim Arbeiten an älteren .NET Framework Versionen und bei der Verwaltung von Anwendungen, die vor einiger Zeit geschrieben wurden, können Sie vielleicht wissen, dass Sie keine neuen Technologien erlernen und sich nicht mit der Entwicklung moderner technischer Fähigkeiten beschäftigen. Wenn dies ihre Geschichte ist – ist das Buch für Sie!

## <a name="desktop-applications-nowadays"></a>Heutzutage Desktop Anwendungen

Vor der Erhöhung des Internets waren Desktop Anwendungen der wichtigste Ansatz zum Entwickeln von Softwaresystemen. Entwickler können eine beliebige Programmiersprache auswählen, z. b. COBOL, Fortran, VB6 oder C++. Aber wo Sie kleine Tools oder komplexe verteilte Architekturen entwickelt haben, waren Sie alle Desktop Anwendungen.

Dann begann Internet Technologien, die Entwicklungswelt zu erschüttern und mehr und mehr Technikern mit Vorteilen wie einfacher Bereitstellung und vereinfachten Verteilungs Prozessen zu gewinnen. Die Tatsache, dass bei der Bereitstellung einer Webanwendung für die Produktion alle Benutzer automatische Updates erhalten haben, hat die Flexibilität der Software enorm beeinträchtigt.

Die Internet Infrastruktur, die zugrunde liegenden Protokolle und Standards wie http und HTML wurden jedoch nicht zum entwickeln komplexer Anwendungen entworfen. Tatsächlich war der größte Entwicklungsaufwand darauf zurückzuführen, dass Webanwendungen die gleichen Funktionen wie Desktop Anwendungen bieten, wie z. b. die schnelle Dateneingabe und die Zustands Verwaltung.

Obwohl Web-und Mobile Anwendungen mit einer unglaublichen Geschwindigkeit gewachsen sind, halten Desktop Anwendungen für bestimmte Aufgaben immer noch die Zahl an einer Stelle im Hinblick auf Effizienz und Leistung. Darin wird erläutert, warum Millionen von Entwicklern vorhanden sind, die Ihre Projekte mit WPF und WinForms entwickeln, und die Menge dieser Anwendungen wächst ständig.

Hier sind einige Gründe für die Auswahl von Desktop Anwendungen in ihrer Entwicklung:

- Desktop-apps haben eine bessere Interaktion mit dem PC des Benutzers.
- Die Leistung von Desktop Anwendungen für komplexe Berechnungen ist weitaus höher als die Leistung von Webanwendungen.
- Das Ausführen von benutzerdefinierter Logik auf Clientseite ist zwar möglich, aber mit einer Webanwendung weitaus schwieriger.
- Die Verwendung von Multithreading ist in einer Desktop Anwendung einfacher und effizienter.
- Die Lernkurve für das Entwerfen von Benutzeroberflächen (User Interfaces, UIs) ist nicht steil. Und für WinForms ist es mit Drag & Drop der Windows Forms-Designer vollständig intuitiv.
- Es ist einfach, mit dem Programmieren und Testen Ihrer Algorithmen zu beginnen, ohne eine Serverinfrastruktur einrichten oder Konnektivitätsprobleme, Firewalls und Browserkompatibilität berücksichtigen zu müssen.
- Das Debuggen ist im Vergleich zum webdebugging leistungsstark.
- Der Zugriff auf Hardware Geräte wie Kamera, Bluetooth oder Smartcardleser ist einfach.
- Da die Technologie eine Weile vergangen ist, gibt es viele Experten und eine Wissensdatenbank, die für die Entwicklung von Desktop Anwendungen verfügbar ist.

Wie Sie sehen können, eignet sich die Entwicklung für Desktop aus vielen Gründen hervorragend. Die Technologie ist ausgereift und Zeit getestet, der Entwicklungszeitraum ist schnell, das Debugging ist leistungsfähig, und die Verwendung von Desktop-Apps ist weniger komplex und einfacher zu beginnen.

Microsoft hat im Laufe der Jahre viele UI-Desktop Technologien von Win32 angeboten, die in 1995 bis universelle Windows-Plattform (UWP) in 2016 eingeführt wurden.

![Microsoft Desktop-Technologien](./media/why-modern-applications/microsoft-desktop-technologies.png)

Gemäß einer Umfrage, die von Telerik am 2016. April veröffentlicht wurde, sind die beliebtesten Technologien für das Entwickeln von Windows-Desktop-Apps Windows Forms, WPF und UWP.

![Telerik Survey zeigt Windows Forms, WPF und UWP als beliebteste Desktop Technologien an](./media/why-modern-applications/telerik-survey.png)

Sie können in jedem von Ihnen mit c# und Visual Basic entwickeln, aber sehen wir uns das genauer an.

### <a name="windows-forms"></a>Windows Forms

Windows Forms erstmals in 2002 veröffentlicht, ist ein verwaltetes Framework und ist die älteste, am häufigsten verwendete Desktop Technologie, die auf der Windows Graphics Device Interface (GDI)-Engine basiert. Sie bietet eine reibungslose Drag & Drop-Benutzeroberfläche für die Entwicklung von Benutzeroberflächen in Visual Studio.  Gleichzeitig ist Windows Forms auf den Visual Studio-Designer als Hauptweg zum Entwickeln Ihrer Benutzeroberfläche angewiesen. das Erstellen von visuellen Komponenten aus Code ist daher nicht trivial.

In der folgenden Liste sind die Hauptmerkmale von Windows Forms zusammengefasst:

- Ausgereifte Technologie mit vielen Codebeispielen und Dokumentationen.
- Leistungsfähiger und produktiver Designer. Es ist nicht so praktisch, die Benutzeroberfläche "aus Code" zu entwerfen.
- Dank der Drag-and-Drop-Funktion des Designers sind Sie einfach und intuitiv zu erlernen.
- Unterstützt unter allen Windows-Versionen.
- Wird unter .net Core 3,0 und höheren Versionen unterstützt.

### <a name="wpf"></a>WPF

Basierend auf der XAML-Sprachspezifikation begünstigt WPF eine klare Trennung zwischen Benutzeroberfläche und Code. XAML bietet Funktionen wie Vorlagen, Formatierung und Bindung, die zum Erstellen von großen Anwendungen geeignet sind. Wie Windows Forms ist es ein verwaltetes Framework, aber der Entwurf ist modular und wiederverwendbar.

Im folgenden finden Sie die wichtigsten Features von WPF:

- Ausgereifte Technologie.
- Designer ist verfügbar, aber Entwickler bevorzugen es in der Regel, den Entwurf mithilfe von deklarativem XAML aus dem Code zu erstellen.
- Die Lernkurve ist steilere als Windows Forms.
- Unterstützt unter allen Windows-Versionen.
- Wird unter .net Core 3,0 und höheren Versionen unterstützt.

### <a name="uwp"></a>UWP

UWP ist nicht nur ein Präsentations Framework wie WPF und Windows Forms, sondern auch eine Plattform selbst. Diese Plattform hat Folgendes:

- Ein eigener API-Satz (die Windows-Runtime-API).
- Ein neues Bereitstellungs System (msix)
- Ein modernes Anwendungslebenszyklus-Modell (für geringen Akku Verbrauch).
- Ein neues Ressourcen Verwaltungs System (basierend auf PRI-Dateien).

Die Plattform wurde erstellt, um alle Arten von Eingabe Systemen (z. b. Ink, Toucheingabe, Gamepad, Maus, Tastatur, Blick usw.) in allen Formfaktoren zu unterstützen, die sich auf die Leistung und den niedrigen Akku Verbrauch stützen. Aus diesen Gründen verwendet die Shell des Windows 10-Betriebssystems Teile der UWP-Plattform.

![UWP-Struktur](./media/why-modern-applications/uwp-structure.png)

UWP enthält ein XAML-basiertes Präsentations Framework, wie z. b. WPF. es gibt jedoch einige wichtige Unterschiede, wie z. b.:

- Anwendungen werden in App-Containern ausgeführt. App-Container steuern, auf welche Ressourcen eine UWP-App zugreifen kann.
- Wird nur unter Windows 10 unterstützt.
- Apps können über Microsoft Store bereitgestellt werden, um die Bereitstellung zu vereinfachen.
- Entwickelt als Teil der Windows-Runtime-API.
- Enthält einen umfangreichen Satz integrierter Steuerelemente und zusätzliche Steuerelemente, die über die nuget-Pakete der Microsoft UI-Bibliothek (WinUI-Bibliothek) bereitgestellt werden, die alle paar Monate aktualisiert wurden.

## <a name="a-tale-of-two-platforms"></a>Eine Geschichte von zwei Plattformen

In den letzten 20 Jahren entwickelte sich während der Entwicklung von UI-Desktop Technologien und der Verwendung des Pfads von Windows Forms zu UWP die Hardware auch von hohen Gewichtungs-PC-Einheiten mit kleinen CRT-Monitoren bis hin zu High-dpi-Monitoren und Lightweight-Tablets und Smartphones mit unterschiedlichen Dateneingabe Techniken wie Fingereingabe und Handschrift. Diese Änderungen führten dazu, zwei verschiedene Konzepte zu erstellen: eine Desktop Anwendung und eine moderne Anwendung. Eine moderne Anwendung ist eine Anwendung, die verschiedene Geräte Formfaktoren, verschiedene Eingabe-und Ausgabemethoden und moderne Desktop Features bei der Ausführung auf einem Sandkasten Ausführungs Modell berücksichtigt. Die (herkömmliche) Desktop Anwendung hingegen ist eine Anwendung, die eine solide Benutzeroberfläche mit hoher Dichte von Steuerelementen benötigt, die am besten mit einer Maus und einer Tastatur betrieben werden.

In der folgenden Tabelle werden die Unterschiede zwischen den beiden Konzepten beschrieben:

|   | Moderne Anwendung | Desktop Anwendung |
| --- | --- | --- |
| Sicherheit | Die Ausführung ist &amp; hervorragend. Entwickelt von Grund auf, um den Datenschutz der Benutzer zu berücksichtigen, die Akku Lebensdauer zu verwalten und den Schwerpunkt auf die Sicherheit des Geräts zu halten.  | Benutzer &amp; Administratorebene der Sicherheit. Sie haben systemeigenen Zugriff auf die Registrierungs-und Festplatten Ordner. |
| Bereitstellung | Installation und Updates werden von der Plattform verwaltet.   | MSI, Custom Installer &amp; Updates. In der Regel eine Quelle von Kopfschmerzen für Entwickler und IT-Manager.  |
| Distribution | Signierte Pakete mit vertrauenswürdiger Verteilung &amp; . Die Verteilung erfolgt über eine vertrauenswürdige Quelle und nie über das Web.  | Web, benutzerdefinierte SCCM- &amp; Verteilung. Sie können nicht steuern, was installiert ist, sondern den gesamten Computer beeinträchtigen.   |
| Benutzeroberfläche | Moderne Benutzeroberfläche. Verschiedene Eingabe Mechanismen, frei Hand Eingaben, Touchpad, Tastatur, Maus usw.  | Windows Forms, WPF, MFC. Entwickelt für die Maus und Tastatur für eine Dichte Benutzeroberfläche und zum erzielen der Produktivität vom Desktop.  |
| Daten | Cloud First-Daten mit Erkenntnissen. Die Quelle der Wahrheit in der Cloud. Erkenntnisse, um zu erfahren, was mit Ihrer APP geschieht und wie Sie funktioniert.  | Lokale Daten. Herkömmliche Desktop Anwendungen benötigen normalerweise einige lokale Daten.  |
| Entwurf | Zur Wiederverwendung vorgesehen. Verwenden Sie die unterschiedlichen Plattformen, das Front-End und das Back-End, um Ressourcen an vielen Stellen wie möglich zu verwenden.  | Nur für Windows Desktop konzipiert  |

Als Teil der Verpflichtung, Entwicklern die besten Tools zum Erstellen von Anwendungen bereitzustellen, hat Microsoft großartige Anstrengungen unternommen, um diese Konzepte zu bringen, oder wir können sogar Plattformen Ansagen, um Entwicklern das Beste aus beiden Welten zu ermöglichen. Zu diesem Zweck hat Microsoft einen bidirektionalen Aufwand zwischen den beiden Plattformen durchgeführt.

![Bidirektionaler Aufwand zwischen modernen Anwendungen und Desktop Anwendungen](./media/why-modern-applications/bidirectional-effort.png)

1. Verschieben Sie Desktop Anwendungsszenarien in eine moderne Anwendungsplattform. Die herkömmliche Desktop Entwicklung ist weiterhin beliebt, da Sie bestimmte Szenarios gut adressiert. Es ist sinnvoll, diese gängigen Desktop Szenarien zu nutzen und Sie auf die moderne Desktop Plattform zu bringen, damit die Plattform vollständig fähig ist.

    ![Verschieben von Desktop Anwendungsszenarien in eine moderne Anwendungsplattform](./media/why-modern-applications/desktop-to-modern.png)

1. Verschieben Sie moderne Anwendungs Features in Desktop Anwendungen. Für vorhandene Desktop-Apps, die eine Möglichkeit benötigen, moderne Funktionen zu nutzen, ohne von Grund auf neu zu schreiben, werden Features von der modernen Anwendungsplattform in die Desktop Anwendung übermittelt.

    ![Verschieben von modernen Anwendungs Features in Desktop Anwendungen](./media/why-modern-applications/modern-to-desktop.png)

In diesem Buch konzentrieren wir uns auf den zweiten Teil und zeigen Ihnen, wie Sie Ihre vorhandenen Desktop Anwendungen modernisieren können.

## <a name="paths-to-modernization"></a>Pfade zur Modernisierung

Die Struktur dieses Handbuchs enthält drei verschiedene Achsen, um die Modernisierung zu erreichen: moderne Features, Bereitstellung und Installation.

### <a name="modern-features"></a>Moderne Features

Nehmen wir an, Sie verfügen über eine funktionierende Windows Forms Anwendung, die ein Vertriebsmitarbeiter Ihres Unternehmens zum Ausfüllen eines Kundenauftrags verwendet. Es kommt zu einer neuen Anforderung, damit der Kunde die Bestellung mit einem Tablettstift Signieren kann. Das Inking ist in den heutigen Betriebssystemen und Technologien System eigen, aber es war nicht verfügbar, als die APP entwickelt wurde.

Dieser Pfad zeigt Ihnen, wie Sie moderne Desktop Features in Ihrer vorhandenen Desktop Entwicklung nutzen können.

### <a name="deployment"></a>Bereitstellung

Moderne Entwicklungszyklen haben hervorgehoben, um Agilität zu bieten, wie neue Versionen von Anwendungen für jeden einzelnen Benutzer bereitgestellt werden. Da Windows Forms-und WPF-Anwendungen auf einer bestimmten Version des .NET Framework basieren, die auf dem Computer vorhanden sein muss, können die neuen Features der .NET Framework-Version nicht genutzt werden, ohne dass die IT-Mitarbeiter eine Nebenwirkung für andere apps haben, die auf demselben Computer ausgeführt werden. Sie hat die Innovationsgeschwindigkeit für Entwickler beschränkt, die Sie zwingen, auf veralteten Versionen des .NET Framework zu bleiben.

Seit dem Start von .net Core 3,0 können Sie einen neuen Ansatz für die parallele Bereitstellung mehrerer Versionen von .net Core nutzen und angeben, auf welche Version von .net Core jede Anwendung abzielen soll. Auf diese Weise können Sie die neuesten Features in einer Anwendung verwenden, während Sie sicher sind, dass Sie keine anderen Anwendungen unterbrechen werden.

### <a name="installation"></a>Installation

Desktop Anwendungen verlassen sich immer auf einen Installationsvorgang, bevor der Benutzer Sie verwenden kann. Diese Tatsache hat eine Reihe von Technologien, von MSI und ClickOnce bis hin zu benutzerdefinierten Installationsprogrammen oder sogar von der XCOPY-Bereitstellung, ins Spiel gebracht. Jede dieser Methoden behandelt empfindliche Probleme, da Anwendungen eine Möglichkeit benötigen, auf freigegebene Ressourcen auf dem Computer zuzugreifen. Manchmal muss die Installation auf die Registrierung zugreifen, um neue Schlüsselwerte einzufügen oder zu aktualisieren, manchmal zum Aktualisieren von freigegebenen DLLs, auf die von der Hauptanwendung verwiesen wird. Dies führt zu einer kontinuierlichen kopfansicht für Benutzer, die diesen Eindruck erzeugt, dass der Computer nach der Installation einer Anwendung nie identisch ist, auch wenn Sie ihn später deinstallieren.

In diesem Buch werden wir eine neue Methode zum Installieren von Anwendungen mit msix vorstellen, die das zuvor beschriebene Problem löst. Sie erfahren, wie Sie problemlos ein verpacken, eine Installation und Updates für Ihre Anwendung einrichten können.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](whats-new-dotnet-core.md)
