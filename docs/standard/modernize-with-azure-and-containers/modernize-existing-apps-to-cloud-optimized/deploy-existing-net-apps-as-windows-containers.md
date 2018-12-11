---
title: Bereitstellen Sie vorhandener .NET-Apps als Windows-Container
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Bereitstellen Sie vorhandener .NET-Apps als Windows-Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 646acc6fd14c1ff85593dbf6074f0d03d86f04bd
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143746"
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>Bereitstellen Sie vorhandener .NET-Apps als Windows-Container

Bereitstellungen, die auf Windows-Containern basieren, sind dies gilt für Cloudoptimierte Anwendungen und Native Cloudanwendungen.

Allerdings in diesem Handbuch und insbesondere in den folgenden Abschnitten, vor allem der Schwerpunkt liegt auf mithilfe von Windows-Containern für *Cloudoptimierte* Anwendungen, in dem Sie Ihre Anwendung überarbeiten müssen.

## <a name="what-are-containers-linux-or-windows"></a>Was sind Container? (Linux oder Windows)

Container sind eine Möglichkeit, eine Anwendung in einen eigenen isolierten Paket umschließen. In einem Container ist die Anwendung nicht betroffen von Anwendungen oder Prozesse, die außerhalb des Containers vorhanden sind. Alles, was die Anwendung richtet sich an die Ausführung erfolgreich ein Prozess innerhalb des Containers unverändert. Wenn der Container verschoben werden kann, die Anforderungen der Anwendung immer erfüllt, in Bezug auf die direkten Abhängigkeiten, da sie alles, was im Paket enthalten ist, die (bibliotheksabhängigkeiten, Laufzeiten und So weiter) ausgeführt werden muss.

Das wesentliche Merkmal eines Containers ist, dass sie der Umgebung dasselbe in verschiedene Bereitstellungen ist, da der Container selbst mit allen Abhängigkeiten stammen, die es benötigt. Sie können das Debuggen der Anwendung auf Ihrem Computer und klicken Sie dann auf einen anderen Computer, die dieselbe Umgebung gewährleistet bereitstellen.

Ein Container ist eine Instanz eines containerimages. Ein Container-Abbild ist eine Möglichkeit zum Verpacken einer app oder einem Dienst (z. B. eine Momentaufnahme), und klicken Sie dann auf eine zuverlässige und reproduzierbare Weise bereitstellen. Also Docker ist nicht, dass nur a-Technologie – es auch eine Philosophie und ein Prozess ist.

Als Container täglich immer häufiger eingesetzt werden, werden sie ein branchenweites "Bereitstellungseinheit." immer.

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>Vorteile der Container (Docker-Engine unter Linux oder Windows)

Erstellen von Anwendungen mit Containern – wodurch auch möglicherweise als einfache Bausteine-Angebote eine erhebliche Leistungssteigerung bei der Agilität für erstellen, versenden und Ausführen von jeder Anwendung, über eine Infrastruktur definiert.

Mit Containern können Sie jede app von der Entwicklung zur Produktion mit nur wenig oder keine Änderung des Codes, Dank der Integration von Docker über Microsoft-Entwicklertools, Betriebssystemen und Cloud nutzen.

Wenn Sie mit einfachen virtuellen Computern bereitstellen, haben Sie wahrscheinlich bereits eine Methode vorhanden, für die Bereitstellung von ASP.NET-Apps für Ihre virtuellen Computer an. Es ist jedoch wahrscheinlich, Ihre Methode mehrere manuelle Schritte oder komplexe automatisierte Prozesse erforderlich, ein Bereitstellungstool wie Puppet oder in ein ähnliches Tool. Sie müssen möglicherweise Aufgaben wie das Ändern von Konfigurationselementen, kopieren die Anwendungsinhalte zwischen Servern und Ausführen von interaktiven Setup-Programme, die basierend auf den MSI-Setups, gefolgt von Tests ausführen. Alle diese Schritte in der Bereitstellung werden Zeit und das Risiko für Bereitstellungen hinzufügen. Sie erhalten Fehler, wenn eine Abhängigkeit nicht in der zielumgebung vorhanden ist.

In Windows-Containern wird der Prozess der Verpacken von Anwendungen vollständig automatisiert. Windows-Container basiert auf der Docker-Plattform automatische Aktualisierungen und Rollbacks für containerbereitstellungen bietet. Die wichtigste Verbesserung, die aus der Verwendung der Docker-Engine ist die Erstellung von Images, die wie Momentaufnahmen Ihrer Anwendung sind, mit allen Abhängigkeiten. Die Images sind Docker-Images (in diesem Fall eine Windows-containerimage). Die Bilder werden ASP.NET-Apps, die in Containern, nicht wieder auf den Quellcode. Die Container-Momentaufnahme ist die Bereitstellungseinheit.

Viele Organisationen werden bestehende monolithische Anwendungen aus den folgenden Gründen containerisieren von:

-   **Freigeben von Agilität durch verbesserte Bereitstellung**. Container bieten einen konsistenter bereitstellungvertrag zwischen Entwicklung und Betrieb. Wenn Sie Container verwenden, hören Sie keinen Entwickler sagen, "Es auf meinem Computer funktioniert, warum also nicht in der Produktion?" Sie können z. B. "Es als Container ausgeführt wird, damit sie in der Produktion ausgeführt werden soll." Die gepackte Anwendung mit allen Abhängigkeiten, kann in jeder Container basierende Umgebung ausgeführt werden. Es wird die Methode ausgeführt, die sie in alle Bereitstellungsziele verwenden (Entwicklung, Qualitätssicherung eigentlich, staging und Produktion) ausgeführt. Die meisten Reibungsverluste Container entfernt werden, wenn sie von einer Phase zur nächsten, verschieben Sie die Bereitstellung erheblich verbessert, und Sie schneller liefern können.

-   **Reduzierung der Kosten**. Container führen, geringere Kosten, entweder durch die Konsolidierung und Entfernung der vorhandenen Hardware oder das Ausführen von Anwendungen auf eine höhere Dichte pro Einheit der Hardware.

-   **Portabilität**. Container sind modular und portable. Docker-Container werden auf alle Server-Betriebssystem (Linux und Windows) in jeder wichtigen öffentlichen Cloud (Microsoft Azure, Amazon AWS, Google, IBM) und in lokalen und privaten oder hybridcloudumgebungen unterstützt.

-   **Steuerelement**. Container bieten eine flexible und sichere Umgebung, die auf Container-Ebene gesteuert wird. Ein Container kann gesichert, isoliert und sogar beschränkt, indem Sie Ausführung Einschränkung-Richtlinien für den Container festlegen. Ausführliche Informationen finden Sie im Abschnitt zu Windows-Containern bieten Windows Server 2016 und Hyper-V-Container zusätzliche Enterprise Support-Optionen.

Bedeutende Verbesserungen in Agilität, Portabilität und Kontrolle werden letztlich zu erheblichen kosteneinsparungen führen, bei Verwendung von Containern entwickeln und Verwalten von Anwendungen.

## <a name="what-is-docker"></a>Was ist Docker?

[Docker](https://www.docker.com/) ist ein [Open Source-Projekt](https://github.com/docker/docker) zur Automatisierung der Bereitstellung von Anwendungen als Mobile, eigenständige Container, die in der Cloud oder lokal ausgeführt werden kann. Docker ist außerdem ein [Unternehmen](https://www.docker.com/), das diese Technologie weiterentwickelt. Das Unternehmen arbeitet mit Cloud-, Linux- und Windows-Herstellern einschließlich Microsoft.

![](./media/image6.png)

> **Abbildung 4 bis 6.** Docker stellt Container auf allen Ebenen der hybriden Cloud bereit

An eine Person mit virtuellen Computern vertraut Container scheinen bemerkenswert ähnlich sein werden. Ein Container ein Betriebssystem ausgeführt wird, verfügt über ein Dateisystem und kann über ein Netzwerk, wie ein physischer oder virtueller Computer-System zugegriffen werden. Allerdings unterscheiden sich die Technologie und Konzepte hinter Container erheblich von virtuellen Computern. Aus Sicht des ein Entwickler muss ein Container mehr wie ein einzelner Prozess behandelt werden. In der Tat verfügt über ein Container auf einen einzigen Einstiegspunkt für einen Prozess aus.

Docker-Container (der Einfachheit halber *Container*) nativ unter Linux und Windows ausführen können. Bei regulären Container ausgeführt wird, können nur auf Windows-Hosts (einem Hostserver oder einen virtuellen Computer) Windows-Containern ausgeführt, und Linux-Container können nur auf Linux-Hosts ausgeführt. Allerdings kann in früheren Versionen von Windows Server und Hyper-V-Container, ein Linux-Container auch nativ ausgeführt unter Windows Server mithilfe der Hyper-V-Isolation-Technologie, die derzeit nur in Windows Server-Container zur Verfügung steht.

Gemischten Umgebungen, in denen sowohl Linux- und Windows-Container werden in naher Zukunft möglich und sogar häufig.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>Die Vorteile der Windows-Containern für Ihre vorhandenen Anwendungen für .NET

Die Vorteile der Verwendung von Windows-Containern sind im Grunde die gleichen Vorteile, die Sie in der Regel aus Container abrufen. Mithilfe von Windows-Containern, geht davon ab, was eine deutlich höhere Flexibilität, Portabilität und Steuerelement.

Vorhandene .NET-Anwendungen verwenden können, finden Sie in diesen Anwendungen, die mithilfe von .NET Framework erstellt wurden. Z. B. möglicherweise herkömmliche ASP.NET-Webanwendungen – sie verwenden nicht .NET Core, die neuer ist und ausgeführt wird – plattformübergreifend unter Linux, Windows und MacOS.

Die wichtigsten Abhängigkeit in .NET Framework ist Windows. Es umfasst auch sekundäre Abhängigkeiten, wie IIS und "System.Web" die herkömmliche ASP.NET-Version.

Eine .NET Framework-Anwendung muss auf Windows, der Zeitraum ausgeführt. Wenn Sie packen Sie vorhandene .NET Framework-Anwendungen in Container und nicht oder nicht in einer Migration zu .NET Core investieren möchten ("Wenn es ordnungsgemäß funktioniert, nicht migrieren sie"), die einzige Wahl für Container ist Windows-Container verwendet werden.

Also einer der Hauptvorteile der Windows-Container ist, dass sie Sie bieten eine Möglichkeit, Ihre vorhandenen .NET Framework-Anwendungen modernisieren, die auf Windows-through-containerisierung ausgeführt werden. Windows-Container erhalten Sie letztlich die Vorteile, die Sie suchen mithilfe von Container-Agilität, Portabilität und eine bessere Kontrolle.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>Wählen Sie ein Betriebssystem mit ein. NET-basierte Container

Angesichts die Vielfalt der Betriebssysteme, die von Docker als auch die Unterschiede zwischen .NET Framework und .NET Core unterstützt werden, sollten Sie ein bestimmtes Betriebssystem und bestimmte Versionen, die basierend auf verwendetem Framework abzielen.

Für Windows können Sie Windows Server Core oder Windows Nano Server verwenden. Diese Windows-Versionen bieten unterschiedliche Eigenschaften (z. B. IIS im Vergleich zu einem selbstgehosteten Webserver wie Kestrel), die möglicherweise von .NET Framework oder .NET Core-Anwendungen benötigt wird.

Für Linux sind mehrere Distributionen (z.B. Debian) verfügbar und werden in offiziellen .NET Docker-Images unterstützt.

Abbildung 4-7 zeigt Betriebssystemversionen, die abhängig von der app-Version von .NET Framework ausgerichtet werden kann.

![](./media/image7.png)

> **Abbildung 4 bis 7.** Betriebssysteme Ziel basierend auf .NET Framework-version

In Migrationsszenarien für vorhandenen Webanwendungen oder legacy-Anwendungen, die auf .NET Framework-Anwendungen basieren, werden die wichtigsten Abhängigkeiten unter Windows und IIS. Ihre einzige Option ist die Verwendung von Docker-Images, die basierend auf Windows Server Core und .NET Framework.

Wenn Sie den Namen des Abbilds zu Ihrer Dockerfile-Datei hinzufügen, können Sie das Betriebssystem und Version auswählen, mit einem Tag, wie in den folgenden Beispielen für .NET Framework-basierten Windows-Container-Images:

> | **Tag** | **System- und version** |
> |---|---|
> | **microsoft/dotnet-framework:4.x-windowsservercore** | .NET Framework 4.x auf Windows Server Core |
> | **microsoft/aspnet:4.x-windowsservercore** | .NET Framework 4.x mit zusätzlichen ASP.NET anpassen, unter Windows Server Core |

Für .NET Core (Cross-Platform für Linux und Windows) würde die Tags wie folgt aussehen:

> | **Tag** | **System- und version**
> |---|---|
> | **microsoft/dotnet:2.0.0-runtime** | .NET Core 2.0 nur zur Laufzeit unter Linux |
> | **Microsoft/dotnet:2.0.0-Runtime-nanoserver** | .NET Core 2.0 nur zur Laufzeit auf Windows Nano Server |

### <a name="multi-arch-images"></a>Images für mehrere Architekturen

Seit Mitte 2017 können auch können Sie ein neues Feature in Docker namens [Multi-Arch](https://github.com/moby/moby/issues/15866) Images. .NET Core Docker-Images können Multi-arch-Tags. Die dockerfile-Datei Dateien werden nicht mehr erforderlich, das Betriebssystem zu definieren, das Sie verwenden möchten. Das mehrere Architekturen Feature ermöglicht es sich um ein einzelnes Tag über Konfigurationen für mehrere Computer hinweg verwendet werden. Z. B. mit mehreren Architekturen, können Sie eine allgemeine Tag: **microsoft/dotnet:2.0.0-runtime**. Wenn Sie dieses Tag von einer Linux-Container-Umgebung abrufen, erhalten Sie das Debian-basierten Image. Wenn Sie dieses Tag in einer Windows-Container-Umgebung abrufen, erhalten Sie die Nano Server-basiertes Image.

Da dem herkömmlichen .NET Framework nur Windows, unterstützt, können nicht Sie für .NET Framework-Images das mehrere Architekturen Feature verwenden.

## <a name="windows-container-types"></a>Windows-Containertypen

Wie Linux-Container werden Windows Server-Container mit Docker-Engine verwaltet. Im Gegensatz zu Linux-Container Windows-Container enthalten zwei verschiedene Containertypen, oder ausgeführt wird, wie oft – Windows Server-Container und Hyper-V-Isolierung.

**Windows Server-Container**: Bietet Anwendungsisolation mittels einer isolationstechnologie für Prozesse und Namespaces. Ein Windows Server-Container teilt sich einen Kernel mit dem containerhost und allen Containern, die auf dem Host ausgeführt werden. Diese Container bieten keine sicherheitsbegrenzung schädlicher und sollte nicht verwendet werden, um nicht vertrauenswürdigem Code zu isolieren. Aufgrund der Speicherplatz auf dem freigegebenen Kernel erfordern diese Container, den gleichen Kernel-Version und Konfiguration.

**Hyper-V-Isolierung**: Erweitert die Isolation von Windows Server-Container bereitgestellt werden, indem jeder Container auf einem hochgradig optimierten virtuellen Computer ausgeführt wird. In dieser Konfiguration wird der Kernel des containerhosts nicht mit anderen Containern auf demselben Host freigegeben. Diese Container dienen zum feindlichen mehrinstanzenfähige hosten, mit der gleichen Sicherheitsgarantien eines virtuellen Computers. Da sich diese Container den Kernel mit dem Host oder anderen Containern auf dem Host Teilen nicht, können sie den Kernel mit verschiedenen Versionen und Konfigurationen (mit unterstützten Versionen) ausgeführt. Beispielsweise können alle Windows-Container unter Windows 10 Hyper-V-Isolierung um die Kernel-Version von Windows Server und die Konfiguration zu nutzen.

Ausführen eines Containers auf Windows, mit oder ohne Hyper-V-Isolierung ist eine Entscheidung zur Laufzeit. Sie können zunächst erstellen Sie den Container mit Hyper-V-Isolierung, und wählen Sie für die Ausführung als Windows Server-Container stattdessen zur Laufzeit.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Dokumentation zu Windows-Containern**

    [https://docs.microsoft.com/virtualization/windowscontainers/](https://docs.microsoft.com/virtualization/windowscontainers/)

-   **Grundlagen der Windows-Containern**

    [https://docs.microsoft.com/virtualization/windowscontainers/about/](https://docs.microsoft.com/virtualization/windowscontainers/about/)

-   **INFOGRAFIK: Microsoft und Container**

    [https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf](https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf)


## <a name="the-container-ecosystem-in-azure"></a>Das Container-Ökosystem in Azure

In vorherigen Abschnitten wurde er erläutert gibt die Vorteile von Docker-Containern, sowie weitere Details zu den bestimmten Container-Images für .NET-Anwendungen. Alle diese allgemeine Informationen ist wesentlich, um entwickeln oder Packen eine Anwendung in Container.
Allerdings bietet Microsoft Azure bei zur produktionsumgebung oder sogar QA- und Dev/Test-Umgebungen eine offene und umfassende zahlreiche Möglichkeiten, eine vollständige Container-Ökosystem, in der Cloud (in der Abbildung unten dargestellt). Je nach Anforderungen Ihrer bestimmten Anwendung sollten Sie einen oder einen anderen Azure-Produkt auswählen.

![](./media/image7.5.png)

> **Abbildung 4: 7.5.** Das Container-Ökosystem in Azure

Aus dem Container-Ökosystem in Azure die folgenden Produkte, die Unterstützung von Containern, die Infrastruktur berücksichtigt werden:
-   **Azure Container Instances (ACI)**
-   **Virtuelle Azure-Computer** (mit Unterstützung des Containers)
-   **Azure Virtual Machine Scale Sets** (mit Unterstützung des Containers)

Aus diesen drei bietet ACI einen großer Vorteil, der ist die Tatsache, die Sie nicht das zugrunde liegende Betriebssystem, müssen Sie keine, upgraden/Patchen usw. verwalten müssen, aber ACI weiterhin befindet sich in der Infrastrukturebene, wie in den nächsten Abschnitten dieses Buchs besser erläutert.

Die Produkte in Azure unterstützen Container, die zur gleichen Zeit mehr in der PaaS (Platform-as-Dienst) positioniert Ebene sind:

-   **Azure App Service**
-   **Azure Kubernetes Service (AKS und ACS)**
-   **Azure Service Fabric** 
-   **Azure Batch** 

Dann ist Azure Container Registry-Instanz eine hoch skalierbare containerregistrierung gehostet in Azure, die Sie über alle vorherigen Produkte bei Registrierung und Bereitstellen Ihrer benutzerdefinierten containerimages verwenden können.

Nutzen Sie darüber hinaus von den Containern, anderen verwalteten Diensten in Azure wie Azure SQL-Datenbank, Azure Redis Cache, Azure Cosmos DB usw. Darüber hinaus stehen Lösungen/Plattformen von Drittanbietern im Azure Marketplace, wie Cloud Foundry und OpenShift, in dem Sie auch die Container in Azure verwenden können. 

In den nächsten Abschnitten können Sie Microsoft Empfehlungen dazu, wann die einzelnen diese Azure-Produkte und Lösungen verwendet werden, insbesondere, wenn Windows-Container als Ziel untersuchen.

>[!div class="step-by-step"]
>[Zurück](what-about-cloud-native-applications.md)
>[Weiter](when-not-to-deploy-to-windows-containers.md)