---
title: Bereitstellen vorhandener .NET-Apps als Windows-Container
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Bereitstellen vorhandener .net-apps als Windows-Container
ms.date: 04/29/2018
ms.openlocfilehash: ba9af3fc3a5bf285830bb873fa6a5da8390dc6b4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578313"
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>Bereitstellen vorhandener .NET-Apps als Windows-Container

Bereit Stellungen, die auf Windows-Containern basieren, gelten für cloudanwendungen und Native Cloud-Anwendungen.

In dieser Anleitung und vor allem in den folgenden Abschnitten konzentriert sie sich jedoch hauptsächlich auf die Verwendung von Windows-Containern für cloudanwendungen, in denen Sie Ihre Anwendung nicht neu entwerfen müssen.

## <a name="what-are-containers-linux-or-windows"></a>Was sind Container? (Linux oder Windows)

Container sind eine Möglichkeit, eine Anwendung in ein eigenes isoliertes Paket einzubinden. Im Container ist die Anwendung nicht von Anwendungen oder Prozessen betroffen, die außerhalb des Containers vorhanden sind. Alles, von dem die Anwendung abhängig ist, um erfolgreich ausgeführt zu werden, wenn ein Prozess im Container ausgeführt wird. Immer wenn der Container verschoben wird, werden die Anforderungen der Anwendung in Bezug auf direkte Abhängigkeiten immer erfüllt, da Sie mit allen Komponenten gebündelt werden, die für die Ausführung erforderlich sind (Bibliotheksabhängigkeiten, Runtimes usw.).

Das wichtigste Merkmal eines Containers ist, dass die Umgebung in verschiedenen bereit Stellungen identisch ist, da der Container selbst alle benötigten Abhängigkeiten enthält. Sie können die Anwendung auf dem Computer Debuggen und dann auf einem anderen Computer bereitstellen, in dem die gleiche Umgebung garantiert ist.

Ein Container ist eine Instanz eines Container Images. Ein Container Image ist eine Möglichkeit, eine APP oder einen Dienst (z. b. eine Momentaufnahme) zu verpacken und dann auf zuverlässige und reproduzierbare Weise bereitzustellen. Sie können sagen, dass docker nicht nur eine Technologie ist, sondern auch eine Philosophie und ein Prozess.

Da Container täglich häufiger werden, werden Sie zu einer branchenweiten "Bereitstellungs Einheit".

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>Vorteile von Containern (docker-Engine unter Linux oder Windows)

Das Entwickeln von Anwendungen mithilfe von Containern, die auch als Lightweight-Bausteine definiert werden können, bietet eine deutliche Steigerung der Agilität für das entwickeln, versenden und Ausführen beliebiger Anwendungen in allen Infrastrukturen.

Mit Containern können Sie jede APP von der Entwicklung bis zur Produktion mit wenig oder ohne Codeänderung durchführen, dank der Docker-Integration über Microsoft-Entwicklertools, Betriebssysteme und die Cloud hinweg.

Bei der Bereitstellung auf einfachen VMS verfügen Sie wahrscheinlich bereits über eine Methode zum Bereitstellen von ASP.net-apps auf Ihren virtuellen Computern. Es ist jedoch wahrscheinlich, dass Ihre Methode mehrere manuelle Schritte oder komplexe automatisierte Prozesse mithilfe eines Bereitstellungs Tools wie Puppet oder eines ähnlichen Tools umfasst. Möglicherweise müssen Sie Aufgaben wie das Ändern von Konfigurationselementen, das Kopieren von Anwendungs Inhalten zwischen Servern und das Ausführen interaktiver Setup Programme auf der Grundlage von MSI-Setups ausführen, gefolgt von Tests. Alle Schritte in der Bereitstellung erhöhen Zeit und Risiko für bereit Stellungen. Wenn eine Abhängigkeit in der Zielumgebung nicht vorhanden ist, treten Fehler auf.

In Windows-Containern ist der Prozess zum Verpacken von Anwendungen vollständig automatisiert. Windows-Container basieren auf der Docker-Plattform, die automatische Updates und Rollbacks für Container Bereitstellungen bietet. Die wichtigste Verbesserung bei der Verwendung der Docker-Engine besteht darin, dass Sie Images wie Momentaufnahmen Ihrer Anwendung mit all ihren Abhängigkeiten erstellen. Die Images sind docker-Images (in diesem Fall ein Windows-Container Image). Die Images werden ASP.net-apps in Containern ausgeführt, ohne zum Quellcode zurückzukehren. Die Container Momentaufnahme wird zur Bereitstellungs Einheit.

Viele Organisationen werden aus folgenden Gründen in die Container vorhandener monolithischer Anwendungen übertragen:

- **Freigeben von Agilität durch verbesserte Bereitstellung**. Container bieten einen konsistenten Bereitstellungs Vertrag zwischen Entwicklung und Betrieb. Wenn Sie Container verwenden, sagen Entwickler nicht, dass es auf meinem Computer funktioniert, warum nicht in der Produktion. Sie können sagen, "Es wird als Container ausgeführt, sodass es in der Produktionsumgebung ausgeführt wird." Die gepackte Anwendung mit all ihren Abhängigkeiten kann in einer beliebigen unterstützten Container basierten Umgebung ausgeführt werden. Er wird so ausgeführt, wie er in allen Bereitstellungs Zielen (dev, QA, Staging, Produktion) ausgeführt werden sollte. Container eliminieren die meisten Verschiebungen, wenn Sie von einer Phase zur nächsten wechseln, wodurch die Bereitstellung beträchtlich verbessert wird, und Sie können schneller ausgeliefert werden.

- **Kosteneinsparungen**. Container führen zu geringeren Kosten, entweder durch Konsolidierung und Entfernung vorhandener Hardware oder durch Ausführung von Anwendungen mit einer höheren Dichte pro Hardware Einheit.

- **Portabilität**. Container sind modular und portabel. Docker-Container werden auf allen Server Betriebssystemen (Linux und Windows) unterstützt, in allen wichtigen Public Cloud (Microsoft Azure, Amazon AWS, Google, IBM) und in lokalen und privaten oder Hybrid Cloud Umgebungen.

- \- **Steuer**Element. Container bieten eine flexible und sichere Umgebung, die auf Container Ebene gesteuert wird. Ein Container kann gesichert, isoliert und sogar eingeschränkt werden, indem Ausführungs Einschränkungs Richtlinien für den Container festgelegt werden. Wie im Abschnitt zu Windows-Containern ausführlich erläutert, bieten Windows Server 2016-und Hyper-V-Container zusätzliche Supportoptionen für Unternehmen.

Bedeutende Verbesserungen bei Agilität, Portabilität und Kontrolle führen letztendlich zu erheblichen Kosteneinsparungen, wenn Sie Container zum entwickeln und Verwalten von Anwendungen verwenden.

## <a name="what-is-docker"></a>Was ist Docker?

[Docker](https://www.docker.com/) ist ein [Open Source-Projekt](https://github.com/docker/docker) , das die Bereitstellung von Anwendungen als Portier Bare, eigenständige Container, die in der Cloud oder lokal ausgeführt werden können, automatisiert. Docker ist außerdem ein [Unternehmen](https://www.docker.com/), das diese Technologie weiterentwickelt. Das Unternehmen arbeitet in Zusammenarbeit mit Cloud-, Linux-und Windows-Anbietern, einschließlich Microsoft.

![](./media/image6.png)

> **Abbildung 4-6.** Docker stellt Container auf allen Ebenen der hybriden Cloud bereit

Für eine Person, die mit virtuellen Computern vertraut ist, scheinen Container möglicherweise sehr ähnlich zu sein. Ein Container führt ein Betriebssystem aus, verfügt über ein Dateisystem und kann über ein Netzwerk wie ein physisches oder virtuelles Computersystem aufgerufen werden. Die Technologie und die Konzepte hinter Containern unterscheiden sich jedoch erheblich von virtuellen Computern. Aus Sicht des Entwicklers muss ein Container eher wie ein einzelner Prozess behandelt werden. Tatsächlich verfügt ein Container über einen einzigen Einstiegspunkt für einen Prozess.

Docker-Container (aus Gründender Einfachheit) können nativ unter Linux und Windows ausgeführt werden. Wenn Sie reguläre Container ausführen, können Windows-Container nur auf Windows-Hosts (einem Host Server oder einer VM) ausgeführt werden, und Linux-Container können nur auf Linux-Hosts ausgeführt werden. In neueren Versionen von Windows Server und Hyper-v-Containern kann ein Linux-Container jedoch auch System intern unter Windows Server ausgeführt werden, indem die Hyper-V-Isolations Technologie verwendet wird, die derzeit nur in Windows Server-Containern verfügbar ist.

In naher Zukunft sind gemischte Umgebungen, die sowohl Linux-als auch Windows-Container haben, möglich und sogar üblich.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>Vorteile von Windows-Containern für vorhandene .NET-Anwendungen

Die Vorteile der Verwendung von Windows-Containern sind im Grunde dieselben Vorteile, die Sie von Containern im Allgemeinen erhalten. Die Verwendung von Windows-Containern ist eine deutliche Verbesserung der Agilität, Portabilität und Kontrolle.

Vorhandene .NET-Anwendungen verweisen auf Anwendungen, die mit dem .NET Framework erstellt wurden. Beispielsweise können Sie herkömmliche ASP.NET-Webanwendungen verwenden. Sie verwenden nicht .net Core, das neuer ist und plattformübergreifend unter Linux, Windows und MacOS ausgeführt wird.

Die hauptabhängigkeit in der .NET Framework ist Windows. Außerdem werden sekundäre Abhängigkeiten wie IIS und System. Web in herkömmlichem ASP.net angezeigt.

Eine .NET Framework Anwendung muss unter Windows, period, ausgeführt werden. Wenn Sie vorhandene .NET Framework Anwendungen containerisieren möchten oder nicht in eine Migration zu .net Core investieren möchten ("Wenn Sie ordnungsgemäß funktioniert, nicht migrieren"), ist die einzige Wahl für Container die Verwendung von Windows-Containern.

Einer der Hauptvorteile von Windows-Containern besteht darin, dass Sie Ihnen eine Möglichkeit bieten, Ihre vorhandenen .NET Framework Anwendungen zu modernisieren, die unter Windows-through-Containerisierung ausgeführt werden. Letztendlich erhalten Windows-Container die Vorteile, nach denen Sie suchen, indem Sie Container verwenden: Agilität, Portabilität und bessere Kontrolle.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>Wählen Sie ein Betriebssystem für das Ziel aus. NET-basierte Container

Angesichts der Vielfalt von Betriebssystemen, die von Docker unterstützt werden, sowie der Unterschiede zwischen .NET Framework und .net Core sollten Sie ein bestimmtes Betriebssystem und bestimmte Versionen basierend auf dem von Ihnen verwendeten Framework als Ziel verwenden.

Für Windows können Sie Windows Server Core oder Windows Nano Server verwenden. Diese Windows-Versionen bieten unterschiedliche Merkmale (z. b. IIS im Vergleich zu einem selbstgeh osteten Webserver wie Kestrel), die möglicherweise von .NET Framework-oder .net Core-Anwendungen benötigt werden.

Für Linux sind mehrere Distributionen (z.B. Debian) verfügbar und werden in offiziellen .NET Docker-Images unterstützt.

In Abbildung 4-7 werden Betriebssystemversionen angezeigt, die Sie als Ziel für die App-Version der .NET Framework ausrichten können.

![](./media/image7.png)

> **Abbildung 4-7.** Zu zielende Betriebssysteme basierend auf .NET Framework Version

In Migrationsszenarien für vorhandene oder Legacy Anwendungen, die auf .NET Framework Anwendungen basieren, sind die Haupt Abhängigkeiten unter Windows und IIS. Ihre einzige Option ist die Verwendung von Docker-Images, die auf Windows Server Core und den .NET Framework basieren.

Wenn Sie den Image Namen der dockerfile-Datei hinzufügen, können Sie das Betriebssystem und die Version mithilfe eines Tags auswählen, wie in den folgenden Beispielen für .NET Framework-basierte Windows-Container Images:

> | **Tag** | **System und Version** |
> |---|---|
> | **microsoft/dotnet-framework:4.x-windowsservercore** | .NET Framework 4. x unter Windows Server Core |
> | **microsoft/aspnet:4.x-windowsservercore** | .NET Framework 4. x mit zusätzlicher ASP.net-Anpassung unter Windows Server Core |

Für .net Core (plattformübergreifend für Linux und Windows) würden die Tags wie folgt aussehen:

> | **Tag** | **System und Version**
> |---|---|
> | **microsoft/dotnet:2.0.0-runtime** | .Net Core 2,0-Laufzeit nur unter Linux |
> | **microsoft/dotnet:2.0.0-runtime-nanoserver** | .Net Core 2,0-Laufzeit nur unter Windows Nano Server |

### <a name="multi-arch-images"></a>Multi-Arch-Images

Ab Mitte-2017 können Sie auch ein neues Feature in docker verwenden, das als [Multi-Arch-](https://github.com/moby/moby/issues/15866) Images bezeichnet wird. .Net Core docker-Images können Multi-Arch-Tags verwenden. Die dockerfile-Dateien müssen nicht mehr das Betriebssystem definieren, das Sie als Ziel festlegen. Das multiarch-Feature ermöglicht die Verwendung eines einzelnen Tags in mehreren Computerkonfigurationen. Beispielsweise können Sie mit Multi-Arch ein gemeinsames Tag verwenden: **Microsoft/DotNet: 2.0.0-Runtime**. Wenn Sie dieses Tag aus einer Linux-Container Umgebung abrufen, erhalten Sie das Debian-basierte Image. Wenn Sie dieses Tag aus einer Windows-Container Umgebung abrufen, erhalten Sie das Nano Server-basierte Image.

Wenn die herkömmlichen .NET Framework nur Windows unterstützt, können Sie die Multi-Arch-Funktion für .NET Framework-Images nicht verwenden.

## <a name="windows-container-types"></a>Windows-Containertypen

Wie Linux-Container werden Windows Server-Container mithilfe der Docker-Engine verwaltet. Im Gegensatz zu Linux-Containern enthalten Windows-Container zwei verschiedene Containertypen oder Laufzeiten: Windows Server-Container und Hyper-V-Isolation.

**Windows Server-Container**: Bietet Anwendungs Isolation durch Prozess-und Namespace-Isolations Technologie. Ein Windows Server-Container verwendet einen Kernel mit dem Container Host und allen Containern, die auf dem Host ausgeführt werden. Diese Container bieten keine feindliche Sicherheitsgrenze und sollten nicht zum Isolieren von nicht vertrauenswürdigem Code verwendet werden. Aufgrund des freigegebenen Kernel-Speicherplatzes erfordern diese Container die gleiche Kernel Version und-Konfiguration.

**Hyper-V-Isolation**: Erweitert die von Windows Server-Containern bereitgestellte Isolation, indem jeder Container auf einem hochgradig optimierten virtuellen Computer ausgeführt wird. In dieser Konfiguration wird der Kernel des Container Hosts nicht gemeinsam mit anderen Containern auf dem gleichen Host verwendet. Diese Container sind für das mehr Instanzen fähige Hosting mit den gleichen Sicherheits Zusicherungen eines virtuellen Computers konzipiert. Da diese Container den Kernel nicht mit dem Host oder anderen Containern auf dem Host gemeinsam nutzen, können Sie Kernel mit verschiedenen Versionen und Konfigurationen (mit unterstützten Versionen) ausführen. Alle Windows-Container unter Windows 10 verwenden z. b. die Hyper-V-Isolation, um die Windows Server-Kernel Version und-Konfiguration zu verwenden.

Das Ausführen eines Containers unter Windows mit oder ohne Hyper-V-Isolation ist eine Lauf Zeit Entscheidung. Sie können den Container zunächst mit der Hyper-V-Isolation erstellen und zur Laufzeit stattdessen als Windows Server-Container ausführen.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Dokumentation zu Windows-Containern**

    <https://docs.microsoft.com/virtualization/windowscontainers/>

- **Grundlagen zu Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/about/>

- **Infografik Microsoft und Container**

    <https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf>

## <a name="the-container-ecosystem-in-azure"></a>Das containerökosystem in Azure

In den vorherigen Abschnitten wurde erläutert, was die Vorteile von Docker-Containern und Details zu den spezifischen Container Images für .NET-Anwendungen sind. Alle allgemeinen Informationen sind grundlegend, um eine Anwendung zu entwickeln oder in Container zu packen.
Wenn Sie sich jedoch über die Produktions Bereitstellungs Umgebung oder sogar über QA-und Entwicklungs-/Testumgebungen Gedanken machen, bietet Microsoft Azure eine offene und große Vielfalt von Optionen, ein vollständiges containerökosystem in der Cloud (siehe Abbildung unten). Abhängig von den Anforderungen ihrer jeweiligen Anwendung sollten Sie ein oder ein anderes Azure-Produkt auswählen.

![](./media/image7.5.png)

> **Abbildung 4-7.5.** Das containerökosystem in Azure

Über das containerökosystem in Azure unterstützen die folgenden Produkte Container, die als Infrastruktur angesehen werden:
- **Azure Container Instances (ACI)**
- **Azure-Virtual Machines** (Mit Unterstützung für Container)
- **Azure-Virtual Machine Scale Sets** (Mit Unterstützung für Container)

Von diesen drei Vorteilen bietet ACI einen großen Vorteil, d. h., Sie müssen nicht das zugrunde liegende Betriebssystem verwalten, Sie müssen kein Upgrade/Patch durchführen, sondern es ist immer noch auf der Infrastruktur Ebene positioniert, was in den bevorstehenden Abschnitten dieses Buchs besser erläutert wird.

Die Produkte in Azure, die Container gleichzeitig unterstützen, sind mehr auf der Ebene von PAS (Platform-as-a-Service) positioniert:

- **Azure App Service**
- **Azure Kubernetes-Dienst (AKS und ACS)**
- **Azure Batch** 

Azure Container Registry ist dann eine hochskalierbare Container Registrierung, die in Azure gehostet wird und die Sie für alle vorherigen Produkte verwenden können, wenn Sie Ihre benutzerdefinierten Container Images registrieren und bereitstellen.

Darüber hinaus können Sie in ihren Containern andere verwaltete Dienste in Azure wie Azure SQL-Datenbank, Azure redis Cache, Azure Cosmos DB usw. nutzen. Außerdem gibt es Lösungen/Plattformen von Drittanbietern, die in Azure Marketplace wie Cloud Foundry und openshift verfügbar sind, wo Sie auch Container in Azure verwenden können. 

In den nächsten Abschnitten werden die Empfehlungen von Microsoft erläutert, wann die einzelnen Azure-Produkte und-Lösungen speziell für Windows-Container verwendet werden sollen.

>[!div class="step-by-step"]
>[Zurück](what-about-cloud-native-applications.md)
>[Weiter](when-not-to-deploy-to-windows-containers.md)
