---
title: Bereitstellen von vorhandenen .NET apps wie Windows-Container
description: .NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Bereitstellen von vorhandenen .NET apps wie Windows-Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6c70e30c10674c086e6ad880b97151ae1918ed87
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>Bereitstellen von vorhandenen .NET apps wie Windows-Container

Bereitstellungen, die auf Windows-Containern basieren gelten für Cloud-optimierte Anwendungen, systemeigenen Cloud-Anwendungen und DevOps Cloudfähige Anwendungen zur Verfügung.

Der Schwerpunkt in diesem Handbuch und in den folgenden Abschnitten ist mithilfe von Windows-Container für *DevOps Cloudfähige* Anwendungen, wenn Sie heben und verschieben vorhandene Anwendungen für .NET.

## <a name="what-are-containers-linux-or-windows"></a>Was sind Container? (Linux- oder Windows)

Container sind eine Möglichkeit, eine Anwendung in einem eigenen isolierten Paket zu umschließen. In einem Container wird die Anwendung nicht beeinflusst, Anwendungen oder Prozesse, die außerhalb der Container vorhanden sind. Alles, was die Anwendung richtet sich bei der Ausführung erfolgreich wie ein Prozess innerhalb des Containers ist. Immer, wenn der Container verschoben werden kann, die Anforderungen der Anwendung werden immer erfüllt sein, im Hinblick auf direkte Abhängigkeiten, da sie alles, was gebündelt ist, die zum Ausführen von (Bibliotheksverzeichnisse, Laufzeiten, usw.) benötigt.

Die wichtigsten Merkmal eines Containers ist, dass der Umgebung die gleiche über verschiedene Bereitstellungen vereinfacht, da alle Abhängigkeiten der Container selbst Klassentreiber benötigten. Dies bedeutet, dass der Anwendung auf dem Computer debuggen, und klicken Sie dann auf einen anderen Computer, mit der gleichen Umgebung garantiert bereitstellen.

Ein Container ist eine Instanz eines containerimages. Ein Container-Abbild ist eine Möglichkeit, verpackt wird, eine app oder ein Dienst (z. B. eine Momentaufnahme), und klicken Sie dann auf eine Weise zuverlässige und reproduzierbare bereitgestellt. Sie konnten sagen, dass Docker nicht, dass nur eine Technologie-It auch eine Philosophie und ein Prozess des.

Sobald Container täglich eher üblich sind, werden sie branchenweiten "Bereitstellungseinheit." immer.

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>Vorteile von Containern (Docker-Modul unter Linux oder Windows)

Erstellen von Anwendungen mit Containern, wodurch auch möglicherweise definiert als einfache Bausteine-Angebote beträchtlich zunehmen in Flexibilität zum Erstellen, Protokollversand und jede Anwendung verfügt über Infrastruktur ausgeführt.

Mit Containern können Sie jede app von der Entwicklung bis hin zur Produktion mit wenig oder keine Änderung des Codes, Dank der Integration von Docker in Microsoft-Entwicklertools, Betriebssysteme und Cloud nutzen.

Wenn Sie nur virtuelle Computer bereitstellen, haben Sie wahrscheinlich bereits eine Methode für das Bereitstellen von ASP.NET-Apps für Ihre virtuellen Computer eingerichtet. Es ist jedoch, dass die Methode über ein Bereitstellungstool wie Puppet oder ein ähnliches Tool mehrere manuelle Schritte oder komplexe automatisierte Prozesse umfasst wahrscheinlich. Möglicherweise müssen zum Ausführen von Aufgaben wie das Ändern von Konfigurationselementen, zum Kopieren von Anwendungsinhalt zwischen Servern und zum interaktiven Setup-Programme, die basierend auf MSI-Setups, gefolgt von Tests ausführen. Alle diese Schritte in der Bereitstellung hinzufügen Zeit und dem Risiko ab, für die Bereitstellung. Fehler erhalten, wenn eine Abhängigkeit nicht in der zielumgebung vorhanden ist.

In Windows-Containern ist der Prozess von Anwendungspaketen vollständig automatisiert. Windows-Containern basiert auf der Docker-Plattform, die automatische Updates und Rollbacks für containerbereitstellungen bietet. Die wichtigsten Verbesserung, die aus dem Einsatz des Docker-Moduls ist, Bilder, die wie von Momentaufnahmen der Anwendung sind, mit allen seinen Abhängigkeiten zu erstellen. Die Bilder werden Docker-Images (in diesem Fall eine Windows-containerimage). Die Bilder, Ausführen von ASP.NET-Anwendungen in Containern, ohne kehren zum Quellcode. Die Container-Momentaufnahme wird die Entwicklungseinheit dar.

Eine große Anzahl von Organisationen werden vorhandene monolithische Anwendungen aus den folgenden Gründen containerizing:

-   **Release Flexibilität durch verbesserte Bereitstellung**. Container bieten einen konsistente Bereitstellung Vertrag zwischen Entwicklungs- und Vorgänge. Wenn Sie Container verwendet werden, hören Sie keinen Entwickler sagen, "Funktionsweise auf meinem Computer Warum nicht in der Produktion?" Sie können einfach z. B. "Als Container ausführen, damit sie in der produktionsumgebung ausgeführt werden soll." Die verpackte Anwendung, mit seinen Abhängigkeiten kann in jeder Container basierenden Umgebung ausgeführt werden. Es wird wie beabsichtigt war, führen Sie alle Bereitstellungsziele verwenden (Dev, QA, staging, Produktion) ausgeführt. Container zu den meisten Frictions vermeiden, wenn sie von einer Phase auf das nächste wird die Bereitstellung erheblich verbessert verschieben, und Sie können schneller anzubieten.

-   **Reduzierung der Kosten**. Container führen senkt die Kosten, entweder durch die Konsolidierung und Entfernen von vorhandener Hardware oder Anwendungen auf eine höhere Dichte pro Einheit der Hardware ausgeführt wird.

-   **Portabilität**. Container sind modulare und portable. Docker-Containern werden auf jedem Server-Betriebssystem (Linux und Windows) in (Microsoft Azure, AWS Amazon, Google, IBM), alle wichtigen öffentlichen Cloud und lokal und private oder Hybrid Cloud-Umgebungen unterstützt.

-   **Steuerelement**. Container bieten eine flexible und sichere Umgebung, die auf Containerebene gesteuert wird. Container kann gesichert, isoliert werden, und durch das Festlegen der Ausführung Einschränkung Richtlinien für den Container selbst beschränkt. Wie im Abschnitt zur Windows-Container bieten Windows Server 2016 und Hyper-V-Container zusätzliche Enterprise Support-Optionen.

Erhebliche Verbesserungen in Flexibilität und Portabilität Steuerelement führen zu einer erheblichen Reduzierung letztendlich bei Verwendung von Containern zum Entwickeln und Verwalten von Anwendungen.

## <a name="what-is-docker"></a>Was ist Docker?

[Docker](https://www.docker.com/) ist ein [Open Source-Projekts](https://github.com/docker/docker) , die automatisiert der Bereitstellung von Anwendungen als portable, eigenständiger Container, die in der Cloud oder lokal ausgeführt werden kann. Docker ist auch eine [Unternehmen](https://www.docker.com/) , stuft und diese Technologie weiterentwickelt. Das Unternehmen arbeitet in Zusammenarbeit mit der Cloud, Linux und Windows-Herstellern, einschließlich Microsoft.

![](./media/image6.png)

> **Abbildung 4 bis 6.** Docker stellt Container auf allen Ebenen der hybriden Cloud bereit

An eine Person mit virtuellen Computern vertraut Container scheinen außerordentlich ähnlich sein. Ein Container ein Betriebssystem ausgeführt wird, verfügt über ein Dateisystem und kann über ein Netzwerk, wie eine physische oder virtuelle Computersystem zugegriffen werden. Allerdings unterscheiden sich die Technologie und Konzepte hinter Container völlig von virtuellen Computern. Aus Sicht des ein Entwickler muss ein Container mehr wie ein einzelner Prozess behandelt werden. Tatsächlich ist ein Container einen einzigen Einstiegspunkt für einen Prozess.

Docker-Containern (aus Gründen der Einfachheit, *Container*) können dann nativ unter Linux und Windows ausführen. Wenn reguläre Container ausgeführt wird, können Windows-Container nur auf Windows-Hosts (einem Hostserver oder einen virtuellen Computer) ausgeführt, und Linux-Container können nur auf Linux-Hosts ausgeführt. Allerdings kann in den neuesten Versionen von Windows Server- und Hyper-V-Container ein Linux-Container auch systemintern ausführen unter Windows Server mithilfe der Hyper-V-Isolation-Technologie, die zurzeit nur in Windows Server-Container verfügbar ist.

In der nahen Zukunft werden gemischte Umgebungen, die Linux- und Windows-Container verfügen über möglich und sogar allgemeine.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>Vorteile der Windows-Container für Ihre vorhandenen .NET-Anwendungen

Die Vorteile der Verwendung von Windows-Container sind im Grunde die gleichen Vorteile, die Sie im Allgemeinen aus Container erhalten. Mithilfe von Windows-Container ist über die Flexibilität, die Portabilität und Steuerelement erheblich verbessern.

Wenn wir den vorhandenen .NET Applications erörtern, gemeint größtenteils herkömmliche Anwendungen, die mithilfe von .NET Framework erstellt wurden. Angenommen, sie sind möglicherweise herkömmlichen ASP.NET-Webanwendungen,-verwenden Sie .NET Core, die neuer ist und plattformübergreifende führt keine sie unter Linux, Windows und Mac OS.

Die wichtigsten Abhängigkeit in .NET Framework ist Windows. Zudem ist eine sekundäre Abhängigkeiten, wie IIS und System.Web in herkömmlichen ASP.NET.

Zeitraum muss .NET Framework-Anwendung unter Windows ausgeführt. Wenn vorhandene .NET Framework-Anwendungen containerize werden sollen; Sie können weder möchte, dass nicht in einer Migration zu .NET Core investieren zu müssen ("Wenn sie ordnungsgemäß funktioniert, nicht migrieren sie"), die einzige Option für Container verfügen Windows-Containern verwendet wird.

Damit einer der Hauptvorteile von Windows-Containern ist, dass Sie bieten eine Möglichkeit, Ihre vorhandenen .NET Framework-Anwendungen zu aktualisieren, die auf Windows-through Containerization ausgeführt werden. Windows-Containern ruft letztlich die Vorteile, die Sie suchen mithilfe von Containern Agilität, Portabilität und eine bessere Kontrolle.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>Wählen Sie ein Betriebssystem mit ein. NET-basierte Container

Angesichts die Vielfalt der Betriebssysteme, die durch Docker als auch die Unterschiede zwischen .NET Framework und .NET Core unterstützt werden, sollten Sie die einem bestimmten Betriebssystem und bestimmte Versionen, die basierend auf dem verwendeten Framework abzielen.

Für Windows können Sie Windows Server Core oder Windows Nano Server verwenden. Diese Windows-Versionen bieten unterschiedliche Eigenschaften (z. B. IIS im Vergleich zu einem selbst gehosteten Webserver wie Kestrel), die möglicherweise von .NET Framework oder .NET Core-Anwendungen benötigt werden.

Für Linux sind mehrere Distributionen (z.B. Debian) verfügbar und werden in offiziellen .NET Docker-Images unterstützt.

Abbildung 4-7 zeigt die Versionen des Betriebssystems, die abhängig von der app-Version von .NET Framework ausgerichtet werden können.

![](./media/image7.png)

> **Abbildung 4-7.** Ziel, basierend auf .NET Framework-Version-Betriebssysteme

In Migrationsszenarien für vorhandene oder eine ältere Anwendungen, die auf .NET Framework-Anwendungen basieren, befinden sich die wichtigsten Abhängigkeiten auf Windows und IIS. Ihre einzige Option ist die Verwendung von Docker-Images, die basierend auf Windows Server Core und .NET Framework.

Wenn Sie die Dockerfile-Datei den Namen des Abbilds hinzugefügt haben, können Sie ein Tag, wie in den folgenden Beispielen für .NET Framework-basierten Windows-containerimages mit dem Betriebssystem und Version auswählen:

> | **Tag** | **System- und version** |
> |---|---|
> | **microsoft/dotnet-framework:4.x-windowsservercore** | .NET Framework 4.x unter Windows Server Core |
> | **microsoft/aspnet:4.x-windowsservercore** | .NET Framework 4.x mit zusätzlichen ASP.NET Anpassung unter Windows Server Core |

Für .NET Core (plattformübergreifende für Linux und Windows) würde die Tags wie folgt aussehen:

> | **Tag** | **System- und version**
> |---|---|
> | **microsoft/dotnet:2.0.0-runtime** | .NET Core 2.0 nur das Laufzeitmodul unter Linux |
> | **Microsoft/dotnet:2.0.0-Runtime-nanoserver** | .NET Core 2.0 nur das Laufzeitmodul unter Windows Nano Server |

### <a name="multi-arch-images"></a>Mit mehreren arch Bilder

Mid 2017 ab, außerdem können Sie ein neues Feature in Docker aufgerufen [mit mehreren Arch](https://github.com/moby/moby/issues/15866) Bilder. .NET Core Docker-Images können mit mehreren arch Tags. Ihr Dockerfile-Dateien nicht mehr erforderlich, das Betriebssystem zu definieren, das das Ziel. Die Funktion mit mehreren arch kann ein einzelnes Tag in der gesamten Konfigurationen für mehrere Computer verwendet werden. Für die Instanz, mit mehreren Arch können Sie einen allgemeinen Transponder: **microsoft/dotnet:2.0.0-runtime**. Wenn Sie das Tag in einer Linux-Container-Umgebung abrufen, erhalten Sie die Debian-basiertes Image. Wenn Sie dieses Tags aus einer Windows-Container-Umgebung abrufen, erhalten Sie das Nano Server-basierte Abbild an.

Da herkömmliche .NET Framework nur Windows unterstützt, können nicht Sie für .NET Framework-Images die mit mehreren arch-Funktion verwenden.

## <a name="windows-container-types"></a>Windows-Containertypen

Wie Linux-Container sind Windows Server-Container mit Docker-Modul verwaltet. Im Gegensatz zu den Linux-Container Windows-Container enthalten zwei verschiedene Containertypen oder Zeiten Windows Server-Containern und Hyper-V-Isolation ausgeführt.

**Windows Server-Container**: Anwendungsisolation mittels einer isolationstechnologie für Prozesse und Namespaces enthält. Ein Windows Server-Container teilt sich einen Kernel mit dem containerhost und allen Container, die auf dem Host ausgeführt werden. Diese Container bieten keine Sicherheitsgrenze feindlichen und sollte nicht verwendet werden, um nicht vertrauenswürdigem Code zu isolieren. Aufgrund des Platzes gemeinsamen Kernel erfordern diese Container die gleiche Kernelversion und Konfiguration.

**Hyper-V-Isolation**: erweitert die Isolation von Windows Server-Container bereitgestellt werden, indem jeder Container auf einem hochgradig optimierten virtuellen Computer ausgeführt wird. In dieser Konfiguration wird der Kernel des containerhosts nicht gemeinsam mit anderen Containern auf demselben Host. Diese Container dienen zum feindlichen mehrinstanzenfähigen hosten, mit den gleichen Sicherheit zusicherungen eines virtuellen Computers. Da diese Container Kernel mit dem Host oder andere Container, auf dem Host gemeinsam nicht, können mit verschiedenen Versionen und Konfigurationen (mit unterstützten Versionen) Kernels ausgeführt werden. Beispielsweise verwenden alle Windows-Container unter Windows 10 Hyper-V-Isolation die Kernel-Version von Windows Server und die Konfiguration zu nutzen.

Einen Container unter Windows ausgeführt wird, mit oder ohne Hyper-V-Isolation ist eine Entscheidung zur Laufzeit. Sie können wählen Sie zum Erstellen des Containers mit der Hyper-V-Isolation anfänglich und zur Laufzeit wird stattdessen als Windows Server-Container ausgeführt.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Dokumentation zu Windows-Containern**

    [https://docs.microsoft.com/virtualization/windowscontainers/](https://docs.microsoft.com/virtualization/windowscontainers/)

-   **Grundlagen von Windows-Containern**

    [https://docs.microsoft.com/virtualization/windowscontainers/about/](https://docs.microsoft.com/virtualization/windowscontainers/about/)

-   **INFOGRAFIK: Microsoft und Container**

    [https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf](https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf)

>[!div class="step-by-step"]
[Zurück](how-to-deploy-existing-net-apps-to-azure-app-service.md)
[Weiter](when-not-to-deploy-to-windows-containers.md)
