---
title: Bereitstellen vorhandener .NET-Apps als Windows-Container
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Bereitstellen vorhandener .NET-Apps als Windows-Container
ms.date: 04/29/2018
ms.openlocfilehash: 28568ca363bfc8100f78b100f8a7f0242c4f04c9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "73089562"
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>Bereitstellen vorhandener .NET-Apps als Windows-Container

Bereitstellungen, die auf Windows-Containern basieren, lassen sich auf cloudoptimierte Anwendungen und cloudnative Anwendungen anwenden.

In dieser Anleitung und besonders in den folgenden Abschnitten konzentrieren wir uns jedoch hauptsächlich auf die Verwendung von Windows-Containern für *Cloud-Optimized*-Anwendungen (cloudoptimiert), bei denen Sie Ihre Anwendung nicht neu entwerfen müssen.

## <a name="what-are-containers-linux-or-windows"></a>Was sind Container? (Linux oder Windows)

Container sind eine Möglichkeit, eine Anwendung in ihrem eigenen, isolierten Paket zu verpacken. In seinem Container ist die Anwendung nicht von Anwendungen oder Prozessen betroffen, die außerhalb des Containers vorhanden sind. Alles, wovon die Anwendung abhängig ist, um erfolgreich als Prozess ausgeführt zu werden, befindet sich im Container. Egal, wohin der Container verschoben wird, werden die Anforderungen der Anwendung in Bezug auf direkte Abhängigkeiten immer erfüllt, da sie mit allen Komponenten gebündelt wurde, die sie für die Ausführung benötigt (Bibliotheksabhängigkeiten, Laufzeiten usw.).

Die wichtigste Eigenschaft eines Containers ist, dass er über verschiedene Bereitstellungen hinweg eine identische Umgebung bereitstellt, weil der Container selbst alle benötigten Abhängigkeiten enthält. Sie können die Anwendung auf Ihrem Computer debuggen und dann auf einem anderen Computer bereitstellen, wobei dieselbe Umgebung gewährleistet ist.

Ein Container ist eine Instanz eines Containerimages. Mit einem Containerimage können Sie eine Anwendung oder einen Dienst packen (wie eine Momentaufnahme) und dann auf zuverlässige und reproduzierbare Weise bereitstellen. Docker ist also nicht bloß eine Technologie, sondern eine Philosophie und ein Prozess.

Da Container von Tag zu Tag etablierter werden, entwickeln Sie sich branchenweit zu einer „Bereitstellungseinheit“.

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>Vorteile von Containern (Docker-Engine unter Linux oder Windows)

Das Erstellen von Anwendungen mithilfe von Containern, die auch als schlanke Bausteine definiert werden können, bietet eine deutliche Steigerung der Agilität beim Entwickeln, Versenden und Ausführen beliebiger Anwendungen in allen Infrastrukturen.

Mit Containern können Sie jede App mit nur wenigen oder gar keinen Codeänderungen von der Entwicklung bis zur Produktion bringen, dank der Docker-Integration über Microsoft-Entwicklertools, Betriebssysteme und die Cloud hinweg.

Bei der Bereitstellung auf einfachen VMs verfügen Sie wahrscheinlich bereits über eine etablierte Methode zum Bereitstellen von ASP.NET-Apps auf Ihren VMs. Es ist jedoch wahrscheinlich, dass Ihre Methode mehrere manuelle Schritte oder komplexe automatisierte Prozesse unter Verwendung Bereitstellungstools wie 0Puppet oder eines ähnlichen Tools umfasst. Möglicherweise müssen Sie Aufgaben wie das Ändern von Konfigurationselementen, das Kopieren von Anwendungsinhalten zwischen Servern und das Ausführen interaktiver Setupprogramme auf Grundlage von MSI-Setups ausführen, gefolgt von Tests. Alle diese Schritte in der Bereitstellung erhöhen Zeit und Risiko für Bereitstellungen. Bei jedem Fehlen einer Abhängigkeit in der Zielumgebung treten Fehler auf.

In Windows-Containern ist der Prozess zum Verpacken von Anwendungen vollständig automatisiert. Windows-Container basieren auf der Docker-Plattform, die automatische Updates und Rollbacks für Containerbereitstellungen bietet. Die wichtigste Verbesserung, die Sie durch die Verwendung der Docker-Engine erreichen, besteht darin, dass Sie Images erstellen, die sich wie Momentaufnahmen Ihrer Anwendung mit all ihren Abhängigkeiten verhalten. Die Images sind Docker-Images (in diesem Fall ein Windows-Containerimage). Die Images führen ASP.NET-Apps in Containern aus, ohne zum Quellcode zurückzukehren. Die Containermomentaufnahme wird zur Bereitstellungseinheit.

Viele Organisationen containerisieren vorhandene monolithische Anwendungen aus folgenden Gründen:

- **Release-Agilität durch verbesserte Bereitstellung**. Container bieten einen konsistenten Bereitstellungsvertrag zwischen Entwicklung und Betrieb. Wenn Sie Container verwenden, hören Sie von Entwicklern nie: „Es funktioniert auf meinem Computer. Warum nicht in der Produktion?“ Sie können sagen: „Es wird als Container ausgeführt, also wird es auch in der Produktion funktionieren.“ Die gepackte Anwendung mit all ihren Abhängigkeiten kann in einer beliebigen unterstützten, containerbasierten Umgebung ausgeführt werden. Sie wird so wie beabsichtigt in allen Bereitstellungszielen ausgeführt (Entwicklung, Qualitätssicherung, Staging, Produktion). Container beseitigen die meisten Reibungspunkte, wenn Sie von einer Phase zur nächsten fortschreiten, wodurch sich die Bereitstellung beträchtlich verbessert und Sie schneller ausliefern können.

- **Kosteneinsparungen**. Container führen zu niedrigeren Kosten, entweder durch die Konsolidierung und Beseitigung vorhandener Hardware oder durch das Ausführen von Anwendungen mit höherer Dichte pro Hardwareeinheit.

- **Übertragbarkeit:** Container sind modular und portierbar. Docker-Container werden auf jedem Serverbetriebssystem unterstützt (Linux und Windows), in allen wichtigen Public Clouds (Microsoft Azure, Amazon AWS, Google, IBM) sowie in lokalen und privaten oder Hybrid Cloud-Umgebungen.

- **Kontrolle**. Container bieten eine flexible und sichere Umgebung, die auf Containerebene kontrolliert wird. Ein Container kann gesichert, isoliert und sogar eingeschränkt werden, indem Ausführungseinschränkungsrichtlinien für den Container festgelegt werden. Wie im Abschnitt über Windows-Container ausführlich erläutert, bieten Windows Server 2016- und Hyper-V-Container zusätzliche Unterstützungsoptionen für Unternehmen.

Bedeutende Verbesserungen bei Agilität, Portierbarkeit und Kontrolle führen letztendlich zu deutlichen Kosteneinsparungen, wenn Sie Container zum Entwickeln und Verwalten von Anwendungen verwenden.

## <a name="what-is-docker"></a>Was ist Docker?

[Docker](https://www.docker.com/) ist ein [Open Source-Projekt](https://github.com/docker/docker) zur Automatisierung der Bereitstellung von Anwendungen als portierbare, eigenständige Container, die in der Cloud oder lokal ausgeführt werden können. Docker ist außerdem ein [Unternehmen](https://www.docker.com/), das diese Technologie weiterentwickelt. Die Firma arbeitet mit Cloud-, Linux- und Windows-Herstellern, einschließlich Microsoft, zusammen.

![Diagramm, das zeigt, wie Docker Container in der Hybrid Cloud bereitstellt.](./media/deploy-existing-net-apps-as-windows-containers/docker-deploys-containers-all-layers.png)

**Abbildung 4–6.** Docker stellt Container auf allen Ebenen der hybriden Cloud bereit

Einer Person, die mit virtuellen Computern vertraut ist, mögen Container sehr ähnlich erscheinen. Ein Container führt ein Betriebssystem aus, verfügt über ein Dateisystem und auf ihn kann über ein Netzwerk zugegriffen werden, genau wie bei einem physischen oder virtuellen Computersystem. Die hinter Containern stehenden Technologien und Konzepte unterscheiden sich jedoch in hohem Maße von virtuellen Computern. Aus Sicht des Entwicklers muss ein Container eher wie ein einzelner Prozess behandelt werden. Tatsächlich verfügt ein Container über einen einzigen Einstiegspunkt für einen Prozess.

Docker-Container (der Einfachheit halber *Container*) können nativ unter Linux und Windows ausgeführt werden. Bei Ausführung regulärer Container können Windows-Container nur auf Windows-Hosts (einem Hostserver oder einer VM) und Linux-Container nur auf Linux-Hosts ausgeführt werden. In neueren Versionen von Windows Server und Hyper-V-Containern kann ein Linux-Container jedoch auch nativ unter Windows Server ausgeführt werden, indem die Hyper-V-Isolationstechnologie verwendet wird, die derzeit nur in Windows Server-Containern verfügbar ist.

In naher Zukunft sind gemischte Umgebungen, die sowohl Linux- als auch Windows-Container enthalten, möglich und werden sogar gängiger.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>Vorteile von Windows-Containern für Ihre vorhandenen .NET-Anwendungen

Die Vorteile der Verwendung von Windows-Containern sind im Grunde mit denen identisch, die Sie von Containern im Allgemeinen erhalten. Die Verwendung von Windows-Containern stelle eine deutliche Verbesserung der Agilität, Portierbarkeit und Kontrolle dar.

Vorhandene .NET-Anwendungen verweisen auf diese Anwendungen, die mit dem .NET Framework erstellt wurden. Beispielsweise kann es sich bei ihnen um herkömmliche ASP.NET-Webanwendungen handeln, die kein .NET Core verwenden, das neuer ist und plattformübergreifend unter Linux, Windows und MacOS ausgeführt wird.

Die Hauptabhängigkeit in .NET Framework ist Windows. Es bestehen außerdem sekundäre Abhängigkeiten in herkömmlichem ASP.NET wie IIS und System.Web.

Eine .NET Framework-Anwendung muss unter Windows ausgeführt werden – Punkt. Wenn Sie vorhandene .NET Framework-Anwendungen containerisieren möchten, Sie aber nicht in eine Migration zu .NET Core investieren können oder möchten („Wenn es ordnungsgemäß funktioniert, migrieren Sie es nicht.“), steht Ihnen Container nur die Verwendung von Windows-Containern zur Auswahl.

Somit besteht einer der Hauptvorteile von Windows-Containern darin, dass sie Ihnen eine Möglichkeit bieten, Ihre vorhandenen .NET Framework-Anwendungen, die unter Windows ausgeführt werden, mittels Containerisierung zu modernisieren. Letztendlich verschaffen Ihnen Windows-Container die Vorteile, nach denen Sie durch die Verwendung von Containern suchen: Agilität, Portierbarkeit und bessere Kontrolle.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>Auswählen eines Zielbetriebssystems für .NET-basierte Container

Durch die Vielzahl der von Docker unterstützten Betriebssysteme und die Unterschiede zwischen .NET Framework und .NET Core sollten Sie abhängig von dem Framework, das Sie verwenden, auf ein bestimmtes Betriebssystem und bestimmte Versionen abzielen.

Für Windows können Sie Windows Server Core oder Windows Nano Server verwenden. Diese Windows-Versionen bieten unterschiedliche Eigenschaften (z. B. IIS gegenüber einem selbstgehosteten Webserver wie Kestrel), die jeweils für .NET Framework- oder .NET Core-Anwendungen erforderlich sind.

Für Linux sind mehrere Distributionen (z.B. Debian) verfügbar und werden in offiziellen .NET Docker-Images unterstützt.

Abbildung 4–7 zeigt Betriebssystemversionen, auf die Sie abzielen können, abhängig von der .NET Framework-Version der App.

![Diagramm, das zeigt, auf welches Betriebssystem abzuzielen ist, basierend auf der .NET Framework-Version.](./media/deploy-existing-net-apps-as-windows-containers/dotnet-framework-operating-systems.png)

**Abbildung 4–7**. Zielbetriebssystem, basierend auf der .NET Framework-Version

In Migrationsszenarien für vorhandene oder Legacyanwendungen, die auf .NET Framework-Anwendungen basieren, liegen die Hauptabhängigkeiten bei Windows und IIS. Ihre einzige Möglichkeit besteht in der Verwendung von Docker-Images, die auf Windows Server Core und .NET Framework basieren.

Wenn Sie den Namen des Images zu Ihrer Dockerfile-Datei hinzufügen, können Sie das Betriebssystem und die Version auswählen, indem Sie ein Tag auswählen, wie in den folgenden Beispielen für .NET Framework-basierte Windows-Containerimages dargestellt.

> | **Tag** | **System und Version** |
> |---|---|
> | **microsoft/dotnet-framework:4.x-windowsservercore** | .NET Framework 4.x unter Windows Server Core |
> | **microsoft/aspnet:4.x-windowsservercore** | .NET Framework 4.x mit zusätzlicher ASP.NET-Anpassung unter Windows Server Core |

Für .NET Core (plattformübergreifend für Linux und Windows) sähen die Tags wie folgt aus:

> | **Tag** | **System und Version**
> |---|---|
> | **microsoft/dotnet:2.0.0-runtime** | .NET Core 2.0-Runtime, nur unter Linux |
> | **microsoft/dotnet:2.0.0-runtime-nanoserver** | .NET Core 2.0-Runtime, nur unter Windows Nano Server |

### <a name="multi-arch-images"></a>Images für mehrere Architekturen

Ab Mitte-2017 können Sie auch eine neue Funktion in Docker verwenden, die Images für [mehrere Architekturen](https://github.com/moby/moby/issues/15866) heißt. .NET Core Docker-Images können Tags für mehrere Architekturen verwenden. Die Dockerfile-Dateien müssen nicht mehr das Betriebssystem definieren, auf das Sie abzielen. Die Funktion für mehrere Architekturen ermöglicht die Verwendung eines einzelnen Tags in mehreren Computerkonfigurationen. Beispielsweise können Sie mit der Funktion für mehrere Architekturen ein gemeinsames Tag verwenden: **microsoft/dotnet:2.0.0-runtime**. Wenn Sie dieses Tag aus einer Linux-Containerumgebung abrufen, erhalten Sie das Debian-basierte Image. Wenn Sie dieses Tag aus einer Windows-Containerumgebung abrufen, erhalten Sie das Nano Server-basierte Image.

Da das herkömmliche .NET Framework nur Windows unterstützt, können Sie bei .NET Framework-Images die Funktion für mehrere Architekturen nicht verwenden.

## <a name="windows-container-types"></a>Windows-Containertypen

Wie Linux-Container werden auch Windows Server-Container mithilfe der Docker-Engine verwaltet. Im Gegensatz zu Linux-Containern umfassen Windows-Container zwei verschiedene Typen von Containern oder Laufzeiten: Windows Server-Container und Hyper-V-Isolation.

**Windows Server-Container**: Bieten Isolation von Anwendungen durch Technologie zur Isolation von Prozessen und Namespaces. Ein Windows Server-Container teilt sich einen Kernel mit dem Containerhost und allen Containern, die auf dem Host ausgeführt werden. Diese Container bieten keine Sicherheitsgrenze gegenüber feindlichen Angriffen und sollten nicht zum Isolieren von nicht vertrauenswürdigem Code verwendet werden. Aufgrund des gemeinsam genutzten Kernelspeicherplatzes erfordern diese Container dieselbe Kernelversion und -konfiguration.

**Hyper-V-Isolation**: Erweitern die durch Windows Server-Container bereitgestellte Isolation, indem jeder Container in einem hochgradig optimierten virtuellen Computer ausgeführt wird. In dieser Konfiguration wird der Kernel des Containerhosts nicht mit anderen Containern auf demselben Host gemeinsam genutzt. Diese Container sind für das Hosting mehrerer feindlicher Instanzen konzipiert, mit denselben Sicherheitszusicherungen eines virtuellen Computers. Da diese Container den Kernel nicht mit dem Host oder anderen Containern auf dem Host gemeinsam nutzen, können sie Kernel mit verschiedenen Versionen und Konfigurationen (mit unterstützten Versionen) ausführen. Beispielsweise verwenden alle Windows-Container unter Windows 10 Hyper-V-Isolation, um die Windows Server-Kernelversion und -konfiguration zu verwenden.

Ob ein Container unter Windows mit oder ohne Hyper-V-Isolation ausgeführt wird, ist eine Laufzeitentscheidung. Sie können sich entscheiden, den Container anfänglich mit Hyper-V-Isolation zu erstellen, und zur Laufzeit beschließen, ihn stattdessen als Windows Server-Container auszuführen.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Dokumentation zu Windows-Containern**

    <https://docs.microsoft.com/virtualization/windowscontainers/>

- **Grundlagen zu Windows-Containern**

    <https://docs.microsoft.com/virtualization/windowscontainers/about/>

- **Infografik: Microsoft und Container**

    <https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf>

## <a name="the-container-ecosystem-in-azure"></a>Das Containerökosystem in Azure

In den vorherigen Abschnitten wurde erläutert, was die Vorteile von Docker-Containern sind sowie die Details zu den spezifischen Containerimages für .NET-Anwendungen. All diese allgemeinen Informationen sind von grundlegender Bedeutung, um eine Anwendung zu entwickeln oder zu containerisieren.
Wenn Sie jedoch an die Produktionsbereitstellungsumgebung oder sogar an Qualitätssicherungs- und Entwicklungs-/Testumgebungen denken, bietet Microsoft Azure eine offene und breite Vielfalt von Optionen – ein vollständiges Containerökosystem in der Cloud (siehe im folgenden Diagramm). Abhängig von den spezifischen Anforderungen Ihrer jeweiligen Anwendung sollten Sie das eine oder andere Azure-Produkt auswählen.

![Diagramm des Containerökosystems in Azure.](./media/deploy-existing-net-apps-as-windows-containers/azure-container-ecosystem.png)

**Abbildung 4–7.5.** Das Containerökosystem in Azure

Aus dem Containerökosystem in Azure werden die folgenden Produkte, die Container unterstützen, als Infrastruktur angesehen:

- **Azure Container Instances (ACI)**
- **Azure Virtual Machines** (Mit Unterstützung für Container)
- **Azure Virtual Machine Scale Sets** (Mit Unterstützung für Container)

Von diesen drei bietet ACI einen großen Vorteil, wobei es sich um die Tatsache handelt, dass Sie das zugrunde liegende Betriebssystem nicht verwalten, keine Upgrades/Patches durchführen usw. müssen, sondern ACI bleibt weiterhin auf Infrastrukturebene angesiedelt, wie in den bevorstehenden Abschnitten dieses Buchs noch besser erläutert wird.

Die Produkte in Azure, die Container unterstützen, die gleichzeitig stärker auf der PaaS-Ebene (Platform-as-a-Service) angesiedelt sind, sind:

- **Azure App Service**
- **Azure Kubernetes Service (AKS und ACS)**
- **Azure Batch**

Dann ist Azure Container Registry eine hochskalierbare Containerregistrierung, die in Azure gehostet wird und die Sie aus all den vorherigen Produkte verwenden können, wenn Sie Ihre benutzerdefinierten Containerimages registrieren und bereitstellen.

Darüber hinaus können Sie aus ihren Containern heraus andere verwaltete Dienste in Azure wie Azure SQL-Datenbank, Azure Redis Cache, Azure Cosmos DB usw. nutzen. Ferner gibt es Lösungen/Plattformen von Drittanbietern, die in Azure Marketplace verfügbar sind, wie Cloud Foundry und OpenShift, mit denen Sie ebenfalls Container in Azure verwenden können.

In den nächsten Abschnitten können Sie die Empfehlungen von Microsoft nachlesen, wann Sie jede/s der einzelnen Azure-Produkte und -Lösungen verwenden sollten, insbesondere wenn Windows-Container verwendet werden sollen.

>[!div class="step-by-step"]
>[Zurück](what-about-cloud-native-applications.md)
>[Weiter](when-not-to-deploy-to-windows-containers.md)
