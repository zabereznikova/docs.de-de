---
title: Neuerungen bei .NET Core für Desktopumgebungen
description: Erfahren Sie mehr über .net Core, Unterschiede zwischen .net Core und .NET Framework und den neuen Features, die hinzugefügt wurden.
ms.date: 05/12/2020
ms.openlocfilehash: 796facaf8cd4f0d23fbcd04b90cb78fb28ebc465
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "97866536"
---
# <a name="whats-new-with-net-core-for-desktop"></a>Neuerungen bei .NET Core für Desktopumgebungen

Ab .net Core 3,0 unterstützt .net Core Windows Forms und WPF. Nun haben Sie die Wahl zwischen .NET Framework und .net Core für Ihre Desktop Anwendungen. In diesem Kapitel wird beschrieben, was .net Core ist und welche Vorteile für Desktop Anwendungen bestehen.

## <a name="the-motivation-behind-net-core"></a>Die Motivation hinter .net Core

Seit seiner Einführung in 2002 hat sich .NET Framework im Laufe der Jahre entwickelt, um viele Technologien wie Windows Forms, ASP.net, Entity Framework, Windows Store und viele andere Technologien zu unterstützen. Alle unterscheiden sich in der Art. Aus diesem Grund hat Microsoft diese Entwicklung fast erreicht, indem Teile der .NET Framework übernommen und ein anderer Anwendungs Stapel für jede Technologie erstellt wurde. Auf diese Weise können Entwicklungsfunktionen an die Anforderungen des jeweiligen Stapels angepasst werden, wodurch das Potenzial der einzelnen Plattformen maximiert wird. Dies führt zu einer Fragmentierung der Versionen der .NET Framework, die von verschiedenen unabhängigen Teams verwaltet werden. Alle diese Stapel haben eine gemeinsame Struktur, die ein App-Modell, ein Framework und eine Laufzeit enthält. Sie unterscheiden sich jedoch in der Implementierung der einzelnen Teile.

Wenn Sie nur eine dieser Plattformen als Ziel verwenden, können Sie dieses Modell verwenden. In vielen Fällen benötigen Sie jedoch möglicherweise mehr als eine Zielplattform in derselben Projekt Mappe. Beispielsweise kann Ihre Anwendung über einen Desktop Administrator Teil verfügen, eine kundenorientierte Website, auf der die Back-End-Logik auf einem Server und sogar ein mobiler Client verwendet wird. In diesem Fall benötigen Sie ein einheitliches Codierungsverfahren, das alle diese .net-Verticals umfassen kann.

Zum Zeitpunkt der Veröffentlichung von Windows 8 wurde das Konzept der portablen Klassenbibliotheken (pcls) entstanden. Ursprünglich wurde die .NET Framework so entworfen, dass Sie immer als eine Einheit bereitgestellt wird, daher war das [Factoring](https://wikipedia.org/wiki/Decomposition_(computer_science)) nicht von Bedeutung. Um dem Problem der Code Freigabe zwischen Verticals zu begegnen, lag die treibende Kraft in der Umgestaltung des Frameworks. Die Idee von Verträgen besteht darin, eine gut gestaltete API-Oberfläche bereitzustellen. Verträge sind einfach Assemblys, die Sie für kompilieren, und sind mit dem richtigen Aspekt entworfen, um die Abhängigkeiten zwischen Ihnen zu berücksichtigen.

Dies führt dazu, dass die API-Unterschiede zwischen den arbeitet auf Assemblyebene in Bezug auf die API-Unterschiede auf Assemblyebene nachgewiesen werden. Dieser Aspekt ermöglichte eine Klassen Bibliotheks Darstellung, die mehrere Verticals als Ziel haben kann, auch als Portable Klassenbibliotheken bezeichnet.

![Releaseverlauf der .NET Framework](./media/whats-new-dotnet-core/release-history.png)

Bei der PCL ist die Entwicklungs Entwicklung basierend auf der API-Form auf arbeitet vereinheitlicht. Und die größte Notwendigkeit zum Erstellen von Bibliotheken, die auf unterschiedlichen arbeitet ausgeführt werden, werden ebenfalls behandelt. Es gibt jedoch eine große Herausforderung: APIs sind nur portabel, wenn die Implementierung über alle Verticals hinweg verschoben wird.

Ein besserer Ansatz besteht darin, die Implementierungen überarbeitet hinweg zu vereinheitlichen, indem eine gut factorte Implementierung anstelle einer gut factoryansicht bereitgestellt wird. Es ist viel einfacher, jedes Team zu Fragen, das eine bestimmte Komponente besitzt, um sich über die Funktionsweise ihrer APIs in allen arbeitet Gedanken zu machen, als wenn Sie versuchen, einen konsistenten API-Stapel zu erstellen. An dieser Stelle kommt .NET Standard ins Spiel. Weitere Informationen finden Sie im nächsten Abschnitt.

Eine weitere große Herausforderung besteht darin, wie die .NET Framework bereitgestellt wird. Der .NET Framework ist ein Computer weites Framework. Alle daran vorgenommenen Änderungen wirken sich auf alle Anwendungen aus, die eine Abhängigkeit davon haben. Obwohl dieses Bereitstellungs Modell viele Vorteile bietet, z. b. die Verringerung des Speicherplatzes und des zentralisierten Zugriffs auf Dienste, werden einige Fehler angezeigt.

Zunächst einmal ist es für Anwendungsentwickler schwierig, eine Abhängigkeit von einem kürzlich veröffentlichten Framework zu treffen. Sie müssen entweder eine Abhängigkeit vom aktuellen Betriebssystem oder ein Anwendungsinstallations Programm bereitstellen, das die .NET Framework zusammen mit der Anwendung installiert. Wenn Sie ein Webentwickler sind, haben Sie diese Option möglicherweise nicht einmal, da die IT-Abteilung die vom Server unterstützte Version festlegt.

Auch wenn Sie bereit sind, ein Installationsprogramm bereitzustellen, das die .NET Framework-Installation verketten soll, können Sie feststellen, dass das Upgrade des .NET Framework andere Anwendungen unterbrechen kann.

Trotz der Bemühungen, abwärts kompatible Versionen des Frameworks bereitzustellen, gibt es kompatible Änderungen, die Anwendungen unterbrechen können. Wenn Sie z. b. eine Schnittstelle zu einem vorhandenen Typ hinzufügen, können Sie ändern, wie dieser Typ serialisiert wird, und je nach vorhandenem Code unterbrechende Probleme verursachen. Da die Basis von .NET Framework installiert ist, wird die Geschwindigkeit der Innovationen innerhalb der .NET Framework durch die Bekämpfung dieser Szenarien verlangsamt.

Um alle diese Probleme zu lösen, hat Microsoft .net Core entwickelt, um die Entwicklung der .NET-Plattform anzugehen.

## <a name="introduction-to-net-core"></a>Einführung in .NET Core

.Net Core ist die Entwicklung der .NET-Technologie von Microsoft in eine modulare, plattformübergreifende Open-Source-und cloudfähige Plattform. Sie kann unter Windows, macOS und Linux ausgeführt werden und kann auch auf ARM-basierten Architekturen wie Android und IOT ausgeführt werden.

Der Zweck von .net Core besteht darin, eine einheitliche Plattform für alle Arten von Anwendungen bereitzustellen, darunter Windows, plattformübergreifende und Mobile Anwendungen. [.NET Standard](../../standard/net-standard.md) ermöglicht dies durch die Bereitstellung von freigegebenen Basis-APIs, die jedes Anwendungsmodell benötigt, und durch das Ausschließen einer beliebigen Anwendungsmodell spezifischen API.

Dieses Framework bietet Anwendungen viele Vorteile hinsichtlich der Effizienz und Leistung und vereinfacht die Paket Erstellung und Bereitstellung auf den verschiedenen unterstützten Plattformen.

Die Vorteile von .net Core stammen aus den folgenden drei Merkmalen:

- Platt **Form übergreifend:** Sie ermöglicht die Ausführung der Anwendung auf verschiedenen Plattformen (Windows, macOS und Linux).
- **Open Source:** die .net Core-Plattform ist Open Source und ist über GitHub verfügbar und fördert Transparenz und Community-Beiträge.
- **Unterstützt:** Microsoft unterstützt offiziell .net Core.

Ab .net Core 3,0 gibt es neben der vorhandenen Unterstützung für Web und Cloud auch Unterstützung für Desktop-, IOT-und Ki-Domänen. Das Ziel dieses Frameworks ist beeindruckend: für jede Art von .net-Entwicklung, die vorhanden und für die Zukunft steht, als Ziel. Microsoft plant, diese Vision mit .net 5 am Ende von 2020 abzuschließen. Der Name "Core" wurde entfernt, um die Eindeutigkeit in der .NET-Welt zu verstärken.

![Alle Domänen von .net 5](./media/whats-new-dotnet-core/all-domains-of-dotnet5.png)

## <a name="net-framework-vs-net-core"></a>.NET Framework im Vergleich zu .net Core

Nachdem Sie nun die Relevanz von .net Core in der Microsoft-Strategie für .net verstanden haben, Fragen Sie sich vielleicht, was mit .NET Framework passiert. Sie könnten z. b. Fragen wie: müssen Sie diese verwerfen? Wird es verschwinden? Welche Optionen stehen für die Modernisierung der Anwendungen zur Verfügung, die ich .NET Framework habe?

In 2019 wurde die letzte Version von **.NET Framework-4,8** freigegeben. Es umfasste drei wesentliche Verbesserungen für Desktop Anwendungen:

- **Moderne Browser-und mediensteuer Elemente**: heute verwenden .net-Desktop Anwendungen Internet Explorer und Windows-Media Player, um HTML-Dateien und die Wiedergabe von Mediendateien anzuzeigen. Da diese Legacy Steuerelemente nicht den neuesten HTML-Code anzeigen oder die neuesten Mediendateien wiedergeben, wurden neue Steuerelemente hinzugefügt, die Microsoft Edge und neuere Media-Player nutzen, die die neuesten Standards unterstützen.
- **Zugriff auf UWP**-Steuerelemente: UWP enthält neue Steuerelemente, die die neuesten Windows-Features und die Fingereingabe Anzeige nutzen. Sie müssen Ihre Anwendungen nicht neu schreiben, um diese neuen Features und Steuerelemente zu verwenden, sodass Sie diese neuen Features in Ihrem vorhandenen WPF-oder Windows Forms Code verwenden können.
- **Verbesserungen bei hoher dpi-** Auflösung: die Auflösung von anzeigen erhöht sich auf eine Auflösung von 4K und 8K. .NET Framework 4,8 fügt also neue hdpi-Verbesserungen hinzu, um sicherzustellen, dass Ihre vorhandenen Windows Forms und WPF-Anwendungen in den neuen anzeigen hervorragend aussehen können.

Da .NET Framework auf Millionen von Computern installiert ist, wird es von Microsoft weiterhin unterstützt, es werden jedoch keine neuen Features hinzugefügt.

.Net Core ist die Open Source-, plattformübergreifende und schnell verschiebenden Version von .net. Aufgrund der parallelen Art und Weise können Änderungen vorgenommen werden, ohne dass eine Anwendung unterbrochen werden muss. Dies bedeutet, dass .net Core im Laufe der Zeit neue APIs und sprach Features erhält, die .NET Framework nicht. Außerdem verfügt **.net Core** bereits über Features, die für .NET Framework unmöglich waren, z. b.:

- Parallele **Versionen von .net, die Windows Forms und WPF unterstützen**: Dadurch wird das Problem von Nebeneffekten beim Aktualisieren der Frameworkversion des Computers gelöst. Es können mehrere Versionen von .net Core auf dem gleichen Computer installiert werden, und jede Anwendung gibt an, welche Version von .net Core Sie verwenden soll. Noch mehr können Sie nun Windows Forms und WPF auf .net Core entwickeln und ausführen.
- **.Net Core direkt in eine Anwendung einbetten**: Sie können .net Core als Teil des Anwendungspakets bereitstellen. Auf diese Weise können Sie die neuesten Versionen, Features und APIs nutzen, ohne auf eine bestimmte Version warten zu müssen, die auf dem Computer installiert ist.
- **Profitieren Sie von den Vorteilen der .net Core-Funktionen**: .net Core ist die schnell bewegliche Open Source-Version von .net. Seine parallele Natur ermöglicht eine schnelle Einführung neuer innovativer APIs und der Verbesserungen der Basisklassen Bibliotheken (BCL), ohne dass das Risiko einer Unterbrechung der Kompatibilität besteht. Nun können Windows Forms-und WPF-Anwendungen die neuesten .net Core-Funktionen nutzen, die auch grundlegende Korrekturen für die Laufzeitleistung, Unterstützung für hohe dpi-Werte usw. enthalten.

Ein wesentlicher Bestandteil der Roadmap für Microsoft bestand darin, Entwicklern das Verschieben von Anwendungen zu .net Core und in Zukunft in .net 5 zu erleichtern. Wenn Sie jedoch .NET Framework Anwendungen haben, sollten Sie sich nicht auf .net Core umstellen. .NET Framework wird vollständig unterstützt und ist immer Teil von Windows. Wenn Sie jedoch in Zukunft die neuesten sprach Features und APIs verwenden möchten, müssen Sie Ihre Anwendungen in .net Core verschieben.

Für Ihre ganz neuen Desktop Anwendungen empfiehlt es sich, direkt mit .net Core zu beginnen. Es ist einfach und plattformübergreifend, wird parallel ausgeführt, bietet hohe Leistung und eignet sich perfekt für Container und microservicearchitekturen.

![Sie können Ihre .NET Framework Anwendungen mit der neuesten .NET Framework Version aktualisieren oder Ihre Anwendungen auf .net Core portieren.](./media/whats-new-dotnet-core/framework-vs-core.png)

## <a name="net-standard-vs-pcl"></a>.NET Standard im Vergleich zu PCL

[.NET Standard](../../standard/net-standard.md) ist eine formale Spezifikation von .NET-APIs, die für alle .NET-Implementierungen verfügbar sein sollen. Die Motivation hinter .NET Standard ist das Herstellen einer umfassenderen Einheitlichkeit im .NET-Ökosystem. .NET Standard ist eine Spezifikation von .NET-APIs, die eine einheitliche Gruppe von Verträgen bilden, für die der Code kompiliert werden soll. Diese Verträge werden in jeder .NET-Konfiguration implementiert, sodass die Portabilität über verschiedene .net-Implementierungen hinweg ermöglicht wird.

.NET Standard ermöglicht im Wesentlichen die folgenden Szenarien:

- Definiert einen einheitlichen Satz von Basisklassen Bibliotheken-APIs für alle .net-Implementierungen, die unabhängig von der Arbeitsauslastung implementiert werden.
- Sie ermöglicht Entwicklern die Erstellung portabler Bibliotheken, die anhand desselben Satzes von APIs in .NET-Implementierungen eingesetzt werden können.

.NET Standard ist die Entwicklung von pcls, und die folgende Liste zeigt die grundlegenden Unterschiede zwischen .NET Standard und pcls:

- .NET Standard ist ein Satz von APIs, die von Microsoft ausgewählt wurden. Pcls ist nicht.
- Die APIs, die eine PCL enthält, sind von den Plattformen abhängig, die Sie als Ziel auswählen, wenn Sie Sie erstellen. Dadurch kann eine PCL nur für die von Ihnen gewählten Ziele freigegeben werden.
- .NET Standard ist plattformunabhängig und kann überall, unter Windows, macOS, Linux usw. ausgeführt werden.
- Pcls können auch plattformübergreifend ausgeführt werden, haben jedoch eine eingeschränkte Reichweite. Pcls können nur auf eine begrenzte Anzahl von Plattformen ausgerichtet werden.

## <a name="new-desktop-features-in-net-core"></a>Neue Desktop Features in .net Core

### <a name="support-for-windows-forms-and-wpf"></a>Unterstützung für Windows Forms und WPF

Windows Forms und WPF sind seit Version 3,0 Teil von .net Core. Beide Präsentations-Frameworks sind nur für Windows vorgesehen, sodass Sie nicht plattformübergreifend sind. Sie können sich WPF als umfassende Schicht über DirectX vorstellen und als eine schlankere Schicht über GDI+ Windows Forms. WPF und Windows Forms können einen Großteil der Funktionen der Desktop Anwendung in Windows bereitstellen und ausführen. Daher sind Windows Forms und WPF für .net Core und .NET Framework verfügbar. Nun können Sie Ihre neuen Desktop Anwendungen mit .net Core starten und vorhandene von .NET Framework zu .net Core migrieren.

Eine neue Version von .NET Standard, Version 2,1, wurde zur gleichen Zeit wie .net Core 3,0 veröffentlicht. Erwartungsgemäß unterstützen .net Core 3. x-Versionen .NET Standard 2,1 und frühere Versionen.

Außerdem ist es wichtig zu beachten, dass sowohl Windows Forms-als auch WPF-Implementierungen für .net Core Open Source sind.

### <a name="xaml-islands"></a>XAML Islands

[XAML-Inseln](/windows/apps/desktop/modernize/xaml-islands) sind eine Reihe von Komponenten, mit denen Entwickler die neuen Windows 10-Steuerelemente (UWP-XAML-Steuerelemente) in ihren aktuellen WPF-, Windows Forms-und nativen Win32-Apps (wie MFC) verwenden können. Sie können Ihre "Inseln" der UWP-XAML-Steuerelemente überall in ihren Win32-apps steuern.

Diese XAML-Inseln sind möglich, da in Windows 10, Version 1903, ein Satz von APIs eingeführt wird, die das Hosten von UWP-XAML-Inhalten in Win32-Fenstern mit Windows-Handlern (HWNDs) ermöglichen Beachten Sie, dass nur apps, die unter Windows 10 1903 und höher ausgeführt werden, XAML-Inseln verwenden können.

Um das Erstellen von XAML-Inseln für Windows Forms-und WPF-Entwickler zu vereinfachen, führt das Windows Community Toolkit eine Reihe von .net-Wrapper in mehreren nuget-Paketen ein. Diese Wrapper sind die umschließenden und hostingsteuerelemente:

- Die umschließenden Steuerelemente [WebView](/windows/communitytoolkit/controls/wpf-winforms/webview), [webviewcompatible](/windows/communitytoolkit/controls/wpf-winforms/webviewcompatible), [InkCanvas](/windows/communitytoolkit/controls/wpf-winforms/inkcanvas), [mediaplayerelement](/windows/communitytoolkit/controls/wpf-winforms/mediaplayerelement)und [mapcontrol](/windows/communitytoolkit/controls/wpf-winforms/mapcontrol) umschließen einige UWP-XAML-Steuerelemente in Windows Forms-oder WPF-Steuerelemente, um UWP-Konzepte für diese Entwickler zu verbergen.
- Das [windowsxamlhost](/windows/communitytoolkit/controls/wpf-winforms/windowsxamlhost) -Steuerelement für Windows Forms und WPF gestattet andere nicht umschließende UWP-XAML-Steuerelemente und benutzerdefinierte Steuerelemente können in eine XAML-Insel geladen werden.

### <a name="access-to-all-windows-10-apis"></a>Zugriff auf alle Windows 10-APIs

Windows 10 verfügt über eine große Menge an APIs, mit denen Entwickler arbeiten können. Diese APIs haben Zugriff auf eine Vielzahl von Funktionen wie Authentifizierung, Bluetooth, Termine und Kontakte. Diese APIs werden nun über .net Core verfügbar gemacht und bieten Windows-Entwicklern die Möglichkeit, leistungsstarke Desktops-apps zu erstellen, die die in Windows 10 vorhandenen Funktionen nutzen.

### <a name="side-by-side-support-and-self-contained-exes"></a>Parallele Unterstützung und eigenständige exe-Datei

Das .net Core-Bereitstellungs Modell ist einer der größten Vorteile, die Windows-Desktop Entwickler bei .net Core haben werden. Die Möglichkeit, .net Core Global zu installieren, bietet viele der gleichen zentralen Installations-und Wartungsvorteile wie .NET Framework, ohne dass direkte Updates erforderlich sind.

Wenn eine neue .net Core-Version veröffentlicht wird, können Sie jede APP auf einem Computer nach Bedarf aktualisieren, ohne dass sich dies auf andere Anwendungen auswirkt. Neue .net Core-Versionen werden in ihren eigenen Verzeichnissen installiert und sind nebeneinander nebeneinander vorhanden.

Wenn Sie die Bereitstellung mit Isolation durchsetzen müssen, können Sie .net Core mit Ihrer Anwendung bereitstellen. .Net Core bündelt ihre APP mit der .net Core-Laufzeit wie in einer einzelnen ausführbaren Datei.

Diese Bereitstellungs Optionen wurden seit längerer Zeit von Entwicklern angefordert, waren aber mit .NET Framework schwer zu erreichen. Die modulare Architektur von .net Core macht diese flexiblen Bereitstellungs Optionen möglich.

### <a name="performance"></a>Leistung

Seit dem Start der Web-und Cloud-Workloads hat .net Core eine Leistung in seine DNA eingebunden. Der Server seitige Code muss leistungsfähig genug sein, um Szenarios mit hoher Parallelität und .net Core-Bewertungen heute als beste leistungsweb Plattform auf dem Markt zu erfüllen.

Sie können diese Leistungsverbesserungen nutzen, wenn Sie .net Core verwenden, um Ihre nächste Generation von Desktop Anwendungen zu erstellen.

## <a name="benefits-of-open-source"></a>Vorteile von Open Source

Es gibt nur einige Worte zu .net Core, die Open Source sind. Das Entwickeln eines plattformübergreifenden Stapels ist etwas kompliziert, das die Interaktion von spezialisierten Teams auf den einzelnen Zielplattformen erfordert. Dieser Aufwand erfordert sehr viel Zusammenarbeit von innerhalb und außerhalb von Microsoft. Wenn Sie es Open Source machen und somit für die öffentliche Zusammenarbeit offen sind, erhalten Sie den ultimativen flexiblen Entwicklungsstil, der die Qualitäts Leiste erhöht, da Probleme von einer großen und aktiven Community von Entwicklern erkannt werden.

Dies ist ein wichtiger Erfolgsfaktor von .net Core, der die zuvor erwähnte Roadmap weiter beschleunigt: die einzige .NET-Plattform, die jeder Entwickler je benötigt, um Anwendungen zu erstellen.

>[!div class="step-by-step"]
>[Zurück](why-modern-applications.md)
>[Weiter](migrate-modern-applications.md)
