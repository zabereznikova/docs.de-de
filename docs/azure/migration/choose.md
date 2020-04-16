---
title: Auswählen der passenden Azure-Hostingoption
description: Hier erfahren Sie, welcher Azure-Migrationspfad für Ihre ASP.NET-Webanwendung der richtige ist.
author: CESARDELATORRE
ms.author: cesardl
ms.date: 03/01/2020
ms.openlocfilehash: a8ad946b03f97272cb8685620858af6b21a372dc
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "81433349"
---
# <a name="choose-the-right-azure-hosting-option"></a>Auswählen der passenden Azure-Hostingoption

Dieser Artikel enthält Überlegungen und Vergleiche zwischen den verschiedenen Optionen, die Sie in Azure haben, wenn Sie Ihre vorhandenen .NET Framework-Anwendungen von lokal nach Azure migrieren.

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
|Verwendung      |<ul><li>Die Anwendung ist stark vom Server und von lokalen MSI-Installationen abhängig.</li><li>Sie möchten den einfachsten Migrationspfad für die Anwendung nutzen.</li></ul>|Die App ist nicht vom Server abhängig, sondern einfach eine reine ASP.NET-Web-App (MVC, WebForm) oder N-Tier-App (Web-API, WCf), die auf einen Datenbankserver zugreift. |<ul><li>Die Anwendung ist zwar vom Ursprungsserver abhängig, diese Abhängigkeiten können aber in das Docker-Windows-Image aufgenommen werden.</li><li>Möchten Sie die App so modernisieren, dass sie [Cloud DevOps-Ready](../../architecture/modernize-with-azure-containers/modernize-existing-apps-to-cloud-optimized/reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md) ist</li></ul>|
|Vorteile  |<ul><li>Einfachster Migrationspfad</li><li>Vertraute Umgebung. Die Bereitstellungsumgebung ist eine VM, die also lokalen Servern ähnelt.</li></ul> |Laufende PaaS-Wartung, einfachste Methode für die Verwaltung und Skalierung von Apps in Azure |<ul><li>Für die Zukunft vorbereitet, Cloud DevOps-Ready mit Abhängigkeiten in den Containern der App.</li><li>Fast keine Notwendigkeit, .NET /C-Code umzugestalten.</li></ul> |
|Nachteile             |IaaS. Teure Wartung. Sie müssen die Infrastruktur der VM über Netzwerk, Load Balancer, Scale-out, IIS-Management usw. verwalten. |<ul><li>Nicht alle Apps werden [unterstützt](https://appmigration.microsoft.com/assessment).</li><li>Einige Apps müssen möglicherweise umgestaltet und sogar leicht umgestaltet werden, sodass sie Azure App Service unterstützen.</li></ul> |<ul><li>Dockers Lernkurve für Fähigkeiten</li><li>Änderungen am Code und an den App-Konfigurationseinstellungen</li></ul>|
|Requirements (Anforderungen) |Virtueller Windows Server-Computer mit den gleichen Anforderungen wie bei der App für die lokale Umgebung | Azure App Service-Anforderungen, die in [Bereitschaftsprüfungen](https://github.com/Azure/App-Service-Migration-Assistant/wiki/Readiness-Checks)angegeben sind. |<ul><li>[Docker Engine - Enterprise für Windows Server 2019](https://azuremarketplace.microsoft.com/marketplace/apps/cloud-infrastructure-services.docker-windows-2019)<br />oder</li><li>[Azure Container Service (AKS)](https://azure.microsoft.com/services/container-service/) (also Kubernetes-Orchestrator)<br />oder<li>[Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)-Orchestrator</li></ul> |
|Vorgehensweise zum Migrieren |[Migrieren einer ASP.NET-Webanwendung zu einem virtuellen Azure-Computer](vm.md) | [Migrieren einer ASP.NET-Webanwendung zu Azure App Service](app-service.md) | Befolgen Sie die Überlegungen, Szenarien und exemplarischen Vorgehensweisen, die in den [Erweiterungs-. .NET-Apps mit Azure und Windows Containers eBook](https://aka.ms/liftandshiftwithcontainersebook) erläutert werden |

Das folgende Flussdiagramm zeigt eine Entscheidungsstruktur beim Planen einer Migration zu Azure für Ihre vorhandenen .NET Framework-Anwendungen. Wenn es praktikabel ist, versuchen Sie Option A zuerst, aber Option B ist der einfachste Pfad durchzuführen.

![Flussdiagramm mit Hosting-Entscheidungsstruktur](../media/migration/choose/decision-tree.png)

## <a name="database-choices"></a>Datenbankoptionen

Wenn Sie relationale Datenbanken zu Azure migrieren möchten, haben Sie mehrere Möglichkeiten. Hilfreiche Informationen zur Wahl des passenden Datenbankmigrationspfads für Ihre vorhandene .NET-Anwendung finden Sie unter [Migrieren einer SQL Server-Datenbank zu Azure](sql.md).

## <a name="networking-and-security-considerations"></a>Netzwerk- und Sicherheitsaspekte

Wenn Sie Anwendungen in einer öffentlichen Cloud wie Microsoft Azure bereitstellen, empfiehlt es sich unter Umständen, bestimmte Netzwerke durch [Erstellen von Netzwerk-DMZs](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/) zu isolieren und zu schützen – etwa durch eine [DMZ zwischen Azure und Ihrem lokalen Datencenter](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/secure-vnet-hybrid) oder durch eine [ DMZ zwischen Azure und dem Internet](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/secure-vnet-dmz). DMZs können mit [Azure Virtual Network](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) implementiert werden.

Virtuelle Azure-Netzwerke ermöglichen Folgendes:

- Erstellen einer von Ihnen kontrollierten Hybridinfrastruktur
- Verwenden eigener IP-Adressen und DNS-Server
- Schützen von Verbindungen mit einem IPsec-VPN oder mit ExpressRoute
- Differenzierte Kontrolle über den Datenverkehr zwischen Subnetzen
- Erstellen durchdachter Netzwerktopologien mit virtuellen Geräten
- Erhalten Sie eine isolierte und hochsichere Umgebung für Ihre Anwendungen

Informationen zu den ersten Schritten beim Erstellen eines eigenen virtuellen Netzwerks finden Sie in der [Dokumentation zu Azure Virtual Network](https://docs.microsoft.com/azure/virtual-network/).

## <a name="authentication-and-authorization-considerations-when-migrating-to-azure"></a>Authentifizierungs- und Autorisierungsaspekte bei der Migration zu Azure

Die Sicherheit ist eines der Hauptanliegen von Organisationen, die eine Migration in die Cloud durchführen. Die meisten Unternehmen haben viel Zeit, Geld und Engineering in die Entwicklung und Entwicklung eines Sicherheitsmodells investiert, und es ist wichtig, dass sie in der Lage sind, vorhandene Investitionen wie Identitätsspeicher und Single Sign-On-Lösungen zu nutzen.

Viele lokal ausgeführte B2E-.NET-Unternehmensanwendungen nutzen zur Authentifizierung und Identitätsverwaltung Active Directory. Mit Azure AD Connect können Sie Ihre lokalen Verzeichnisse in Azure Active Directory integrieren. Informationen zu den ersten Schritten finden Sie unter [Integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

Ausführlichere Informationen zur Azure Active Directory-Planung finden Sie unter [Ermitteln der Identitätsanforderungen für Ihre Hybrid-Identitätslösung](https://docs.microsoft.com/azure/active-directory/active-directory-hybrid-identity-design-considerations-business-needs).

Als Authentifizierungsprotokolle stehen außerdem [OAuth](https://en.wikipedia.org/wiki/OAuth) und [OpenID](https://en.wikipedia.org/wiki/OpenID) zur Verfügung, die häufig in kundenorientierten Anwendungen zum Einsatz kommen. Bei Verwendung autonomer Identitätsdatenbanken (etwa eine SQL-basierte ASP.NET-Identitätsdatenbank, die unter Verwendung von OAuth in IdentityServer4 eingeschlossen ist) ist in der Regel keine Verbindung mit lokalen Datenbanken oder Verzeichnissen erforderlich.

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Migrieren einer ASP.NET-Webanwendung zu Azure App Service](app-service.md)
