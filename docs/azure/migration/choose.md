---
title: Auswählen der passenden Azure-Hostingoption
description: Hier erfahren Sie, welcher Azure-Migrationspfad für Ihre ASP.NET-Webanwendung der richtige ist.
author: CESARDELATORRE
ms.author: cesardl
ms.date: 03/01/2020
ms.openlocfilehash: 162dc8eb87dfd78d050b93b1c24ac573d7092126
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174295"
---
# <a name="choose-the-right-azure-hosting-option"></a>Auswählen der passenden Azure-Hostingoption

Dieser Artikel enthält Informationen über und Vergleiche zwischen den verschiedenen Optionen, die Ihnen in Azure zur Verfügung stehen, wenn Sie Ihre vorhandenen .NET Framework-Anwendungen aus Ihrer lokalen Umgebung zu Azure migrieren möchten.

Bei der Migration vorhandener .NET-Anwendungen zu Azure sind grundsätzlich folgende Bereiche zu berücksichtigen:

1. Computeoptionen
1. Datenbankoptionen
1. Netzwerk- und Sicherheitsaspekte
1. Authentifizierungs- und Autorisierungsaspekte

## <a name="compute-choices"></a>Computeoptionen

Bei der Migration vorhandener .NET Framework-Anwendungen zu Azure stehen Ihnen mehrere Optionen zur Verfügung. Da .NET Framework allerdings auf Windows basiert, beschränken sich die im Anschluss angegebenen Optionen auf Windows-basierte Computedienste.

Die folgende Tabelle enthält verschiedene Gegenüberstellungen und Empfehlungen, um Sie bei der Wahl des passenden Computemigrationspfads für Ihre vorhandene .NET-Anwendung zu unterstützen:

|                 | Virtuelle Azure-Computer | Azure App Service | Windows-Container |
|-----------------|-----------|-------------------|--------------------|
|Empfohlene Verwendung      |<ul><li>Die Anwendung ist stark vom Server und von lokalen MSI-Installationen abhängig.</li><li>Sie möchten den einfachsten Migrationspfad für die Anwendung nutzen.</li></ul>|Die App ist nicht vom Server abhängig, sondern einfach eine reine ASP.NET-Web-App (MVC, WebForm) oder N-Tier-App (Web-API, WCf), die auf einen Datenbankserver zugreift. |<ul><li>Die Anwendung ist zwar vom Ursprungsserver abhängig, diese Abhängigkeiten können aber in das Docker-Windows-Image aufgenommen werden.</li><li>Sie möchten die App modernisieren, damit sie [cloud- und DevOps-fähig](../../architecture/modernize-with-azure-containers/modernize-existing-apps-to-cloud-optimized/reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md) ist.</li></ul>|
|Vorteile  |<ul><li>Einfachster Migrationspfad</li><li>Vertraute Umgebung. Die Bereitstellungsumgebung ist ein virtueller Computer und ähnelt somit stark einem lokalen Server.</li></ul> |Laufende PaaS-Wartung, einfachste Methode für die Verwaltung und Skalierung von Apps in Azure |<ul><li>Zukunftssicher, cloud- und DevOps-fähig mit Abhängigkeiten, die in die Container der App integriert sind</li><li>Nahezu keine Überarbeitung von .NET-/C#-Code erforderlich</li></ul> |
|Nachteile             |IaaS. Teure Wartung. Sie müssen das Netzwerk, den Lastenausgleich, die horizontale Skalierung, die IIS und Ähnliches für die VM-Infrastruktur verwalten. |<ul><li>Nicht alle Apps werden [unterstützt](https://appmigration.microsoft.com/assessment).</li><li>Der Code einiger Apps muss möglicherweise umgestaltet werden, damit diese Azure App Service unterstützen. Gegebenenfalls muss sogar die Architektur geringfügig angepasst werden.</li></ul> |<ul><li>Lernkurve für Docker</li><li>Änderungen am Code und an den App-Konfigurationseinstellungen</li></ul>|
|Anforderungen |Virtueller Windows Server-Computer mit den gleichen Anforderungen wie bei der App für die lokale Umgebung | Anforderungen für Azure App Service, die unter [Bereitschaftsprüfungen](https://github.com/Azure/App-Service-Migration-Assistant/wiki/Readiness-Checks) angegeben sind |<ul><li>[Docker Engine – Enterprise für Windows Server 2019](https://azuremarketplace.microsoft.com/marketplace/apps/cloud-infrastructure-services.docker-windows-2019)<br />oder</li><li>[Azure Container Service (AKS)](https://azure.microsoft.com/services/container-service/) (also Kubernetes-Orchestrator)<br />oder<li>[Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)-Orchestrator</li></ul> |
|Vorgehensweise zum Migrieren |[Migrieren einer ASP.NET-Webanwendung zu einem virtuellen Azure-Computer](vm.md) | [Migrieren einer ASP.NET-Webanwendung zu Azure App Service](app-service.md) | Überlegungen, Szenarios und exemplarische Vorgehensweisen finden Sie im E-Book [Modernisieren vorhandener .NET-Apps mit Azure und Windows-Containern](https://aka.ms/liftandshiftwithcontainersebook). |

Im folgende Flussdiagramm wird ein Entscheidungsbaum für die Planung der Migration Ihrer vorhandenen .NET Framework-Anwendungen zu Azure dargestellt. Falls möglich, probieren Sie zuerst Option A, Option B ist jedoch der einfachste Weg.

![Flussdiagramm mit Hosting-Entscheidungsstruktur](../media/migration/choose/decision-tree.png)

## <a name="database-choices"></a>Datenbankoptionen

Wenn Sie relationale Datenbanken zu Azure migrieren möchten, haben Sie mehrere Möglichkeiten. Hilfreiche Informationen zur Wahl des passenden Datenbankmigrationspfads für Ihre vorhandene .NET-Anwendung finden Sie unter [Migrieren einer SQL Server-Datenbank zu Azure](sql.md).

## <a name="networking-and-security-considerations"></a>Netzwerk- und Sicherheitsaspekte

Wenn Sie Anwendungen in einer öffentlichen Cloud wie Microsoft Azure bereitstellen, empfiehlt es sich unter Umständen, bestimmte Netzwerke durch [Erstellen von Netzwerk-DMZs](/azure/architecture/reference-architectures/dmz/) zu isolieren und zu schützen – etwa durch eine [DMZ zwischen Azure und Ihrem lokalen Datencenter](/azure/architecture/reference-architectures/dmz/secure-vnet-hybrid) oder durch eine [ DMZ zwischen Azure und dem Internet](/azure/architecture/reference-architectures/dmz/secure-vnet-dmz). DMZs können mit [Azure Virtual Network](/azure/virtual-network/virtual-networks-overview) implementiert werden.

Virtuelle Azure-Netzwerke ermöglichen Folgendes:

- Erstellen einer von Ihnen kontrollierten Hybridinfrastruktur
- Verwenden eigener IP-Adressen und DNS-Server
- Schützen von Verbindungen mit einem IPsec-VPN oder mit ExpressRoute
- Differenzierte Kontrolle über den Datenverkehr zwischen Subnetzen
- Erstellen durchdachter Netzwerktopologien mit virtuellen Geräten
- Schaffen einer isolierten und hochgradig sicheren Umgebung für Ihre Anwendungen

Informationen zu den ersten Schritten beim Erstellen eines eigenen virtuellen Netzwerks finden Sie in der [Dokumentation zu Azure Virtual Network](/azure/virtual-network/).

## <a name="authentication-and-authorization-considerations-when-migrating-to-azure"></a>Authentifizierungs- und Autorisierungsaspekte bei der Migration zu Azure

Die Sicherheit ist eines der Hauptanliegen von Organisationen, die eine Migration in die Cloud durchführen. Die meisten Unternehmen haben viel Zeit, Geld und Know-how in die Gestaltung und Entwicklung eines Sicherheitsmodells investiert. Daher ist es wichtig, dass ihre Investitionen in Maßnahmen wie Identitätsspeicher und Lösungen für einmaliges Anmelden nicht umsonst waren.

Viele lokal ausgeführte B2E-.NET-Unternehmensanwendungen nutzen zur Authentifizierung und Identitätsverwaltung Active Directory. Mit Azure AD Connect können Sie Ihre lokalen Verzeichnisse in Azure Active Directory integrieren. Informationen zu den ersten Schritten finden Sie unter [Integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).

Ausführlichere Informationen zur Azure Active Directory-Planung finden Sie unter [Ermitteln der Identitätsanforderungen für Ihre Hybrid-Identitätslösung](/azure/active-directory/active-directory-hybrid-identity-design-considerations-business-needs).

Als Authentifizierungsprotokolle stehen außerdem [OAuth](https://en.wikipedia.org/wiki/OAuth) und [OpenID](https://en.wikipedia.org/wiki/OpenID) zur Verfügung, die häufig in kundenorientierten Anwendungen zum Einsatz kommen. Bei Verwendung autonomer Identitätsdatenbanken (etwa eine SQL-basierte ASP.NET-Identitätsdatenbank, die unter Verwendung von OAuth in IdentityServer4 eingeschlossen ist) ist in der Regel keine Verbindung mit lokalen Datenbanken oder Verzeichnissen erforderlich.

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Migrieren einer ASP.NET-Webanwendung zu Azure App Service](app-service.md)
