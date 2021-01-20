---
title: Bereitstellen von modernen Desktop-Apps
description: Alles, was Sie über die Bereitstellung moderner Desktop Anwendungen wissen müssen.
ms.date: 05/12/2020
ms.openlocfilehash: ba47f09b27adf270734bbfff285fe44dd4175d29
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615853"
---
# <a name="deploying-modern-desktop-applications"></a>Bereitstellen von modernen Desktop-Apps

Wenn Sie Desktop Anwendungen entwickeln, sollten Sie Bedenken, wie Ihre Anwendung verpackt und auf den Computern der Benutzer bereitgestellt wird. Das Problem bei der Paket Erstellung, Bereitstellung und Installation liegt darin, dass es in der Regel unter dem Dach der IT-Experten liegt, die verschiedene Dinge als Entwickler interessieren.

Heutzutage sind wir mit dem devops-Konzept vertraut, bei dem Entwickler und IT-Experten eng daran arbeiten, Anwendungen in Ihre Produktionsumgebungen zu verschieben. Wenn Sie sich jedoch seit mehr als 10 Jahren im Desktop Kampf befinden, haben Sie möglicherweise die folgende Geschichte gesehen. Ein Entwicklerteam arbeitet hart daran, die Projekt Stichtage einzuhalten. Geschäftliche Menschen sind nervös, da Sie das System zum Ausführen des Unternehmens an vielen Computern des Benutzers arbeiten müssen. An "D-Day" prüft der Projektmanager alle Entwickler, dass Ihr Code gut funktioniert und alles in Ordnung ist, sodass Sie ausgeliefert werden können. Das Paket Team erstellt dann das Setup für die APP, verteilt es an jeden Benutzer Computer, und ein Satz von Test Benutzern führt die Anwendung aus. Nun, Sie versuchen, dass die Anwendung vor dem einblenden einer Benutzeroberfläche eine Ausnahme auslöst, die besagt, dass "Methode ~ of Object ~ failed" angezeigt wird. Panik beginnt durch die Luft, und eine kurze Untersuchung zeigt auf einen jungen und müden Entwickler, der ein Drittanbieter-Steuerelement eingeführt hat, das sicherlich auf dem Entwicklungs Computer gearbeitet hat.

Die Installation von Desktop Anwendungen ist aus zwei Hauptgründen ein Albtraum:

- Fehlende enge Zusammenarbeits Kultur zwischen dev-und IT-Teams.
- Fehlende solide Verpackungs-und Bereitstellungs Technologie, auf der wir aufbauen können.

Tatsächlich haben wir mit der Tatsache gearbeitet, dass Sie eine APP aufgrund der folgenden Aktionen installiert haben:

- Am Ende treten einige unerwünschte Nebeneffekte auf dem Computer auf.
- Einige Anwendungen, die zuvor installiert waren, funktionieren nicht mehr.

Darüber hinaus können Sie den ursprünglichen Zustand des Systems nicht einfach wiederherstellen, indem Sie die APP deinstallieren. Wir sind so in der Lage, diese Situation zu leben, da wir Begriffe wie "DLL Hell" oder "winrot" geprägt haben.

In diesem Kapitel sprechen wir über msix. Msix ist die brandneue Technologie von Microsoft, die versucht, das Beste aus früheren Technologien zu erfassen, um eine solide Grundlage für die Verpackungstechnologie der Zukunft zu bieten.

Was hat eine Verpackungstechnologie mit der Modernisierung zu tun? Nun, es stellt sich heraus, dass die Paket Erstellung für das Unternehmen von großer Bedeutung ist. Die Modernisierung bezieht sich nicht nur auf die Verwendung der neuesten Technologien. Es bezieht sich auch auf das Verkürzen der Markteinführungszeit ab dem Zeitpunkt, an dem eine Geschäfts Anforderung definiert ist, bis Ihr Unternehmen das Feature an Ihren Client übergibt.

## <a name="the-modern-application-lifecycle"></a>Der Lebenszyklus der modernen Anwendung

Heute schreiben und erstellen Entwickler den Code für eine APP und übergeben dann die generierten Assets an die IT-Experten. Anschließend konfigurieren die IT-Experten die APP neu und Verpacken Sie, normalerweise in einer MSI-Datei oder in einer höheren Version, in einem App-V-Paket Erstellungs Format. Die APP wird dann über verschiedene Kanäle und Tools bereitgestellt. Eines der Hauptprobleme bei diesem Ansatz wird häufig als "Paketierungs Lähmung" bezeichnet. Das Problem besteht darin, dass dieser Zeitraum jedes Mal wiederholt wird, wenn ein App-Update oder ein Betriebssystem Update vorliegt.

Der Prozess wird in der folgenden Abbildung dargestellt:

![Diagramm mit dem modernen IT-Lebenszyklus](./media/deploy-modern-applications/modern-it-application-lifecycle.png)

Unternehmen benötigen eine Möglichkeit, diesen Verpackungszyklus in drei unabhängige Zyklen zu unterbrechen:

- Betriebssystemupdates
- Anwendungsupdates
- Anpassung

![Diagramm mit dem modernen IT-Tugend Zyklen](./media/deploy-modern-applications/modern-it-virtuous-cycle.png)

Das vorherige Diagramm zeigt, dass Sie Folgendes ausführen können:

- Aktualisieren Sie das zugrunde liegende Betriebssystem, ohne die apps neu Verpacken zu müssen.
- Aktivieren Sie Anpassungen, ohne dass Sie das ursprüngliche Entwickler Paket neu verpacken müssen.

Diese radikale Veränderung führt uns zum neuen und modernen IT-Lebenszyklus, wie in der folgenden Abbildung dargestellt:

![Das Diagramm zeigt den Anwendungslebenszyklus mit Microsoft-Tools.](./media/deploy-modern-applications/microsoft-it-tools.png)

Entwickler erstellen die APP und generieren ein msix-Paket, das IT-Professionals nutzen und konfigurieren können, ohne dass eine erneute Paket Erstellung erforderlich ist. Zusammen mit der msix-Technologie hat Microsoft Tools erstellt, mit denen die Pakete ohne erneutes Verpacken angepasst und konfiguriert werden können.

## <a name="msix-the-next-generation-of-deployment"></a>Msix: die nächste Generation der Bereitstellung

Vor msix gab es mehrere Verpackungstechnologien wie Setup-Assistenten, MSI, ClickOnce, App-V und Skripterstellung. Jede dieser Technologien hat ihre eigenen Stärken, und Microsoft hat sich entschieden, das beste von allen für die Erstellung von msix auszuwählen. Msix basiert auf den Grundlagen dieser vorhandenen Technologien, die das beste der einzelnen Technologien auswählen:

- App-V = \> Containerisierung
- ClickOnce = \> Automatische Aktualisierung
- MSI = \> leicht zu verteilen

Mit msix erhalten Sie eine installertechnologie mit all diesen Features.

![Diagramm mit den verschiedenen Technologien, die sich auf das aufbauen von msix ausgewirkt haben](./media/deploy-modern-applications/msix.png)

### <a name="benefits-of-msix"></a>Vorteile von msix

#### <a name="never-regret-installing-an-app"></a>Installieren einer APP nie bereuen

Msix bietet eine vorhersagbare, zuverlässige und sichere Bereitstellung. Mit der deklarativen Methode, die im Paket Manifest enthalten ist, kann das Betriebssystem alle Assets nachverfolgen, die Ihre Anwendung benötigt. Außerdem bietet es eine echte, saubere Deinstallation ohne Nebeneffekte.

#### <a name="disk-space-optimization"></a>Speicherplatz Optimierung

Msix ist optimiert, um den Speicherplatz zu reduzieren, den eine Anwendung auf dem Computer Speicherplatz des Benutzers hat. Es erstellt einen Einzelinstanzspeicher für Ihre Dateien. Das heißt, wenn Sie über zwei verschiedene Pakete mit derselben DLL verfügen, wird die dll nicht zweimal installiert. Die Plattform kümmert sich um dieses Problem, da Sie alle Dateien kennt, die eine bestimmte App aufgrund ihrer deklarativen Art installiert hat. Außerdem können Sie verschiedene Versionen einer DLL nebeneinander arbeiten.

Durch die Verwendung von Ressourcen Paketen können Sie problemlos mehrsprachige Apps erstellen, und das Betriebssystem kümmert sich um die Installation der verwendeten Anwendungen.

#### <a name="network-optimization"></a>Netzwerkoptimierung

Msix erkennt die Unterschiede zwischen den Dateien auf Byte Blockebene und ermöglicht so eine Funktion mit dem Namen "differenzielle Updates". Dies bedeutet, dass nur die aktualisierten Byte Blöcke für Anwendungs Updates heruntergeladen werden.

![Ein Diagramm, das zeigt, wie msix differenzielle Updates verwaltet](./media/deploy-modern-applications/msix-managing-updates.png)

Mit der streaminginstallation kann der Benutzer schnell mit der Arbeit an Ihrer Anwendung beginnen, während andere Teile der APP im Hintergrund heruntergeladen werden. Diese Funktion trägt zu einer ansprechenden Benutzer Funktionalität bei.

Mit dem Feature "optionale Pakete" erzielen Sie die Kompatibilität Ihrer APP-Bereitstellung, sodass Sie Sie bei Bedarf herunterladen können.

#### <a name="simple-packaging-and-deployment"></a>Einfaches Verpacken und Bereitstellung

Das AppManifest deklariert die Versionsverwaltung, das Ziel des Geräts und identifiziert Sie standardmäßig für jede Anwendung. Es bietet auch eine Möglichkeit zum Signieren Ihrer Assets, die eine solide Sicherheits Grundlage bereitstellt.

#### <a name="os-managed"></a>Betriebssystem verwaltet

Das Betriebssystem verarbeitet alle Prozesse zum Installieren, aktualisieren und Entfernen einer Anwendung. Anwendungen werden pro Benutzer installiert, aber nur einmal heruntergeladen, wodurch der Speicherbedarf minimiert wird. Microsoft arbeitet daran, die msix-Erfahrung auch unter Windows 7 bereitzustellen.

#### <a name="windows-provides-integrity-for-the-app"></a>Windows stellt Integrität für die APP bereit.

Durch die Verwendung digitaler Signaturen können Sie sicherstellen, dass Sie keine Anwendung aus nicht vertrauenswürdigen Quellen installieren. Außerdem verhindert msix Manipulationen, da:

- Er speichert einen Datensatz von Dateihashes.
- Es erkennt, ob eine Datei nach der Installation geändert wurde.

#### <a name="works-for-the-entire-app-catalog"></a>Funktioniert für den gesamten App-Katalog

Eine der besten Aspekte von msix besteht darin, dass Sie für den gesamten Anwendungs Katalog (Windows Forms, WPF, MFC/ATL, Delphi) funktioniert, auch wenn Sie die XCOPY-Bereitstellung, ClickOnce oder den Speicher nutzen möchten, können Sie dasselbe msix-Paket verwenden.

### <a name="tools"></a>Tools

#### <a name="windows-application-packaging-project"></a>Paketerstellungsprojekt für Windows-Anwendungen

Du kannst das **Paketerstellungsprojekt für Windows-Anwendungen** in Visual Studio verwenden, um ein Paket für deine Desktop-App zu generieren. Anschließend können Sie das Paket in der Microsoft Store veröffentlichen oder es auf einem oder mehreren PCs querladen.

#### <a name="msix-packaging-tool"></a>MSIX-Verpackungstool

Mit dem MSIX Packaging Tool können Sie Ihre vorhandenen Win32-Anwendungen in das MSIX-Format umpacken. Sie bietet sowohl eine interaktive Benutzeroberfläche als auch eine Befehlszeile für Konvertierungen und bietet die Möglichkeit, eine Anwendung ohne den Quellcode zu konvertieren.

![MSIX-Verpackungstool](./media/deploy-modern-applications/msix-packaging-tool.png)

#### <a name="package-support-framework"></a>Framework zur Paketunterstützung (Package Support Framework, PSF)

Das Paket Unterstützungs Framework ist ein Open Source-Kit, das Sie beim Anwenden von Korrekturen auf Ihre vorhandene Win32-Anwendung unterstützt, wenn Sie keinen Zugriff auf den Quellcode haben, sodass er in einem msix-Container ausgeführt werden kann. Durch das Package Support Framework können in Ihrer Anwendung die bewährten Methoden moderner Laufzeitumgebungen angewandt werden.

#### <a name="app-installer"></a>App-Installer

Mit dem APP-Installer können Windows 10-Apps durch Doppelklicken auf das App-Paket installiert werden. Dies bedeutet, dass Benutzer nicht PowerShell oder andere Entwicklertools zum Bereitstellen von Windows 10-Apps verwenden müssen. Das App-Installationsprogramm kann auch eine APP aus dem Web, optionale Pakete und zugehörige Sätze installieren.

## <a name="how-to-create-an-msix-package-from-an-existing-win32-desktop-application"></a>Erstellen eines msix-Pakets aus einer vorhandenen Win32-Desktop Anwendung

Wir durchlaufen den Prozess zum Erstellen eines msix-Pakets aus einer vorhandenen Win32-Anwendung. In diesem Beispiel verwenden wir eine Windows Forms-app.

Fügen Sie der Projekt Mappe zunächst ein neues Projekt hinzu, wählen Sie das Paket für die Windows-Anwendungspaket Erstellung aus, und geben Sie ihm einen Namen.

![Hinzufügen eines neuen Windows-Anwendungspaket Projekts](./media/deploy-modern-applications/add-packaging-project.png)

Die Struktur des Paket Erstellungs Projekts wird angezeigt, und es wird ein spezieller Ordner mit dem Namen " *Applications*" angezeigt. In diesem Ordner können Sie angeben, welche Anwendungen Sie in das Paket einschließen möchten. Sie kann mehr als 1 sein.

![Die Struktur des Paket Erstellungs Projekts.](./media/deploy-modern-applications/packaging-project.png)

Klicken Sie mit der rechten Maustaste auf den Ordner *Anwendungen* , und wählen Sie das Windows Forms Projekt aus der Visual Studio-Projekt Mappe aus.

![Hinzufügen des Windows Forms Projekts zum Paket Erstellungs Projekt](./media/deploy-modern-applications/add-winforms-project.png)

An diesem Punkt können Sie das Paket kompilieren und generieren, aber wir untersuchen einige Dinge. Um eine bessere Benutzer Leistung zu erzielen, kann Visual Studio automatisch alle visuellen Objekte generieren, die eine moderne Anwendung benötigt, um Symbole und Kachel Ressourcen für die Kachel Leiste und das Startmenü zu verarbeiten. Öffnen Sie die Datei " *Package. appxmanifest* ", um auf den Manifest-Designer zuzugreifen. Sie können dann alle visuellen Objekte aus einem bestimmten Bild, das in Ihrem Projekt vorhanden ist, generieren, indem Sie einfach auf **Erstellen** klicken.

![Screenshot des Manifest-Designers in Visual Studio](./media/deploy-modern-applications/manifest-designer.png)

Wenn Sie den Code für die Datei " *Package. appxmanifest* " öffnen, können Sie einige interessante Dinge sehen.

Direkt unter `<Package>` gibt es einen- `<Identity>` Knoten. An dieser Stelle erhält Ihre APP-Anwendung ihre Identität, die vom Betriebssystem verwaltet wird.

![Identitäts Knoten](./media/deploy-modern-applications/identity-node.png)

Im `<Capabilities>` Knoten finden Sie alle Anforderungen, die die Anwendung benötigt. Achten Sie besonders auf das, das `<rescap:Capability Name="runFullTrust" \>` dem Betriebssystem mitteilt, dass die APP im Modus mit voller Vertrauenswürdigkeit ausgeführt werden kann, da es sich um eine Win32-Anwendung handelt.

![Knoten "Funktionen"](./media/deploy-modern-applications/capabilities-node.png)

Legen Sie das Paket Erstellungs Projekt als Startprojekt für die Projekt Mappe fest, und wählen Sie *Ausführen* aus. Gehen Sie dazu wie folgt vor:

- Kompilieren Sie die Windows Forms Anwendung.
- Erstellen Sie ein msix-Paket aus den Buildergebnissen.
- Stellen Sie die Pakete bereit.
- Installieren Sie Sie lokal auf dem Entwicklungs Computer.
- Starten Sie die App.

![Unsere installierte Anwendung](./media/deploy-modern-applications/our-installed-application.png)

Dadurch haben Sie die neue Installation und Deinstallation, die msix vollständig in Windows 10 integriert bereitstellt.

In der letzten Phase erfahren Sie, wie Sie das msix-Paket auf einem anderen Computer bereitstellen.

Klicken Sie mit der rechten Maustaste auf das Paket Projekt, wählen Sie das Menü **Speichern** aus, und wählen Sie dann die Option **App-Pakete erstellen** aus.

Anschließend können Sie auswählen, ob Sie ein Paket erstellen möchten, das in den Speicher hochgeladen oder Pakete für das Sideloading erstellt werden soll. In den meisten Modernisierungs Szenarien wählen Sie **Ich möchte Pakete für das Sideload erstellen**.

![Konfigurieren von Paketen](./media/deploy-modern-applications/configuring-packages.png)

Dort können Sie die verschiedenen Architekturen auswählen, auf die Sie abzielen möchten, wenn Sie im selben msix-Paket beliebig viele hinzufügen möchten.

Der letzte Schritt besteht darin, anzugeben, wo Sie die endgültigen Installations Objekte bereitstellen möchten.

![Update Einstellungen konfigurieren](./media/deploy-modern-applications/configure-update-settings.png)

Sie können einen Webserver eines freigegebenen UNC-Pfads auf den Dateiservern Ihres Unternehmens verwenden. Beachten Sie die Einstellungen, um anzugeben, wie Sie Ihre Anwendung aktualisieren möchten. Im nächsten Abschnitt werden Anwendungs Updates behandelt.

Eine ausführliche Schritt-für-Schritt-Anleitung finden [Sie unter Packen einer Desktop-App aus Quellcode mithilfe von Visual Studio](/windows/msix/desktop/desktop-to-uwp-packaging-dot-net).

## <a name="auto-updates-in-msix"></a>Automatische Updates in msix

Der Windows Store verfügt über einen hervorragend Aktualisierungsmechanismus, der Windows Update verwendet. In den meisten Unternehmens Szenarien verwenden Sie den Store nicht zum Verteilen Ihrer Desktop-Apps. Daher benötigen Sie eine ähnliche Methode, um Updates für Ihre Anwendung zu konfigurieren und Sie per Pull an Ihre Benutzer zu überlassen.

Mithilfe einer Kombination aus Windows 10-Features und msix-Paketen können Sie für Ihre Benutzer eine hervorragend Aktualisierungs Funktion bereitstellen. Der Benutzer muss überhaupt nicht technisch sein, aber dennoch von einem nahtlosen Anwendungs Update profitieren.

Sie können Ihre Updates auf zwei verschiedene Arten für die Interaktion mit dem Benutzer konfigurieren:

- Von Benutzern angeforderte Updates: das Betriebssystem zeigt eine automatisch generierte Benutzeroberfläche an, die den Benutzer darüber informiert, dass die Anwendung installiert werden soll. Diese Benutzeroberfläche wird basierend auf den Eigenschaften erstellt, die Sie für die Installationsdateien angeben.

- Automatische Updates im Hintergrund. Mit dieser Option müssen die Benutzer die Updates nicht kennen.

Sie können auch konfigurieren, wann Sie Updates ausführen möchten, wenn die Anwendung oder regelmäßig gestartet wird. Dank der Sideloading-Features können Sie diese Updates auch dann erhalten, wenn die Anwendung ausgeführt wird.

Wenn Sie diese Art der Bereitstellung verwenden, wird eine spezielle Datei mit dem Namen " *. appinstaller*" erstellt. Diese einfache Datei enthält die folgenden Abschnitte:

- Der Speicherort der *appinstaller* -Datei.
- Die wichtigsten msix-Paket Eigenschaften der Anwendung
- Das Aktualisierungs Verhalten

![appinstaller-Datei](./media/deploy-modern-applications/appinstaller-file.png)

In Kombination mit dieser Datei hat Microsoft ein spezielles URL-Protokoll entworfen, um den Installationsvorgang über einen Link zu starten:

```xml
<a href="ms-appinstaller:?source=http://mywebservice.azureedge.net/MyApp.msix">Install app package </a>
```

Dieses Protokoll kann für alle Browser verwendet werden, und der Installationsvorgang wird mit einer hervorragend Benutzer Darstellung auf Windows 10 gestartet. Da das Betriebssystem den Installationsvorgang verwaltet, ist der Speicherort, von dem aus diese Anwendung installiert wurde, bekannt und verfolgt alle vom Prozess betroffenen Dateien.

Msix erstellt eine Benutzeroberfläche für die Installation, die automatisch einige Eigenschaften des Pakets anzeigt. Dies ermöglicht eine gängige Installation für jede APP.

Nachdem Sie das neue msix-Paket generiert und auf den Bereitstellungs Server verschoben haben, müssen Sie nur die *appinstaller* -Datei bearbeiten, um diese Änderungen widerzuspiegeln, hauptsächlich die Version und den Pfad zur neuen msix-Datei. Wenn der Benutzer die Anwendung das nächste Mal öffnet, wird die Änderung von dem System erkannt, und die Dateien für die neue Version werden im Hintergrund heruntergeladen. Wenn dies abgeschlossen ist, wird die Installation auf dem neuen Anwendungsstart transparent für den Benutzer ausgeführt.

>[!div class="step-by-step"]
>[Zurück](example-migration.md)
