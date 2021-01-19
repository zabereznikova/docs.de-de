---
title: Migrieren einer ASP.NET-Web-App zu einer Azure-VM
description: Hier erfahren Sie, wie Sie eine ASP.NET-Webanwendung aus einer lokalen Umgebung zu einem virtuellen Azure-Computer migrieren.
ms.topic: how-to
ms.date: 06/20/2020
ms.openlocfilehash: 0bf591ce0bd02537414527c8f3ba22bd41cf51d6
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189212"
---
# <a name="migrate-an-aspnet-web-application-to-an-azure-virtual-machine"></a>Migrieren einer ASP.NET-Webanwendung zu einem virtuellen Azure-Computer

In diesem Übersichtsdokument erfahren Sie, wie Sie eine ASP.NET-Webanwendung aus einer lokalen Umgebung zu einem virtuellen Azure-Computer migrieren.

## <a name="quickstart"></a>Schnellstart

Informationen zum Erstellen eines virtuellen Computers und Veröffentlichen Ihrer App darauf: [Veröffentlichen auf einem virtuellen Azure-Computer](https://tutorials.visualstudio.com/aspnet-vm/intro)

## <a name="get-started"></a>Erste Schritte

Die folgenden Tutorials zeigen Schritt für Schritt, wie Sie einen virtuellen Computer erstellen (oder migrieren), Ihre Webanwendung für den virtuellen Computer veröffentlichen und andere Aufgaben durchführen, die ggf. erforderlich sind, damit Ihre Anwendung in Azure unterstützt wird.

- Erstellen Sie mithilfe einer der folgenden Optionen einen virtuellen Computer für Ihre ASP.NET-Anwendung in Azure:
  - [Erstellen eines neuen virtuellen Computers für ASP.NET-Anwendungen](https://go.microsoft.com/fwlink/?linkid=863237)
  - [Migrieren von VMware-VMs zu Azure (ohne Agent)](/azure/migrate/tutorial-migrate-vmware)
  - [Migrieren von virtuellen Hyper-V-Computern zu Azure](/azure/migrate/tutorial-migrate-hyper-v)
- [Veröffentlichen Ihrer App mithilfe von Visual Studio](/azure/virtual-machines/windows/publish-web-app-from-visual-studio)
- [Erstellen eines sicheren virtuellen Netzwerks für Ihre virtuellen Computer](/azure/virtual-network/virtual-network-get-started-vnet-subnet)
- [Erstellen einer CI/CD-Pipeline für Ihre Anwendung](/vsts/build-release/apps/cd/deploy-webdeploy-iis-deploygroups)
- [Verwenden einer VM-Skalierungsgruppe für hohe Verfügbarkeit und Skalierbarkeit](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-deploy-app)

## <a name="considerations"></a>Weitere Überlegungen

### <a name="benefits"></a>Vorteile

Mit virtuellen Computern lässt sich eine Anwendung am einfachsten aus der lokalen Umgebung zur Cloud migrieren. Sie ermöglichen die Replizierung der gleichen Umgebung, die Ihre Anwendung auch lokal verwendet, haben aber den Vorteil, dass Sie keine eigenen Rechenzentren mehr verwalten müssen. VM-Skalierungsgruppen bieten hohe Verfügbarkeit und Skalierbarkeit für Anwendungen, die in Virtual Machines ausgeführt werden.

### <a name="virtual-machine-size"></a>VM-Größe

Wählen Sie eine VM-Größe und einen VM-Typ, die am besten für Ihre Workload geeignet sind. Weitere Informationen finden Sie unter [Größen für virtuelle Windows-Computer in Azure](/azure/virtual-machines/windows/sizes).

### <a name="maintenance"></a>Wartung 

Virtuelle Computer müssen genau wie lokale Computer gewartet und aktualisiert werden<sup>&#42;</sup>. Bei Anwendungen, die in einer PaaS-Umgebung (Plattform-as-a-Service) wie etwa [Azure App Service](/azure/app-service/) oder in einem [Container](/azure/app-service/containers/) ausgeführt werden können, entfällt diese Aufgabe.

*<sup>&#42;</sup>[Automatische Betriebssystemupgrades für Azure-VM-Skalierungsgruppen](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-automatic-upgrade) stehen derzeit als Vorschauversion zur Verfügung.*

### <a name="virtual-networks"></a>Virtuelle Netzwerke

Virtuelle Azure-Netzwerke ermöglichen Folgendes:

- Erstellen einer von Ihnen kontrollierten Hybridinfrastruktur
- Verwenden eigener IP-Adressen und DNS-Server
- Schaffen einer isolierten und hochsicheren Umgebung für Ihre Anwendungen
- Herstellen einer Verbindung zwischen Ihrem virtuellen Computer und Ihrem lokalen Netzwerk über eine der verfügbaren [Verbindungsoptionen](/azure/vpn-gateway/vpn-gateway-about-vpngateways#s2smulti)
- Integrieren Ihres virtuellen Computers in Ihr lokales Netzwerk mithilfe von [ExpressRoute](https://azure.microsoft.com/services/expressroute/)

Informationen zu den ersten Schritten finden Sie in der [Dokumentation zu Virtual Network](/azure/virtual-network/).

### <a name="active-directory"></a>Active Directory

Viele Anwendungen verwenden Active Directory für die Authentifizierung und Identitätsverwaltung.

- Mit Azure AD Connect können Sie Ihre lokalen Verzeichnisse in Azure Active Directory integrieren. Informationen zu den ersten Schritten finden Sie unter [Integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).
- Alternativ können Sie Ihrer Anwendung mit [ExpressRoute](https://azure.microsoft.com/services/expressroute/) den Zugriff auf Ihr lokales Active Directory ermöglichen.

### <a name="sql-databases"></a>SQL-DATENBANKEN

Wenn Ihre Anwendung eine lokale Datenbank verwendet, kann sie standardmäßig nicht mit ihr kommunizieren. Sie haben folgende Möglichkeiten:

- Konfigurieren Sie ein Hybridnetzwerk, über das Ihre Anwendung auf die lokal ausgeführte Datenbank zugreifen kann.
- Migrieren Sie Ihre Datenbank zu Azure. Weitere Informationen finden Sie unter [Migrieren einer ASP.NET-Webanwendung zu einem virtuellen Azure-Computer](sql.md).

### <a name="high-availability-and-scalability"></a>Hochverfügbarkeit und Skalierbarkeit

#### <a name="virtual-machine-scale-sets"></a>Virtual Machine Scale Sets

Wenn Ihre Anwendung hochverfügbar und skalierbar sein soll, empfiehlt es sich, das VM-Image zu einer Azure-VM-Skalierungsgruppe zu migrieren, um die Verfügbarkeit und Skalierbarkeit der Anwendung zu verbessern. Mit VM-Skalierungsgruppen können Sie einen bereits konfigurierten virtuellen Computer verwenden oder eine Buildpipeline für die Erstellung eines Images mit Ihrer Anwendung einrichten.

Informationen zu den ersten Schritten finden Sie unter [Bereitstellen der App in VM-Skalierungsgruppen](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-deploy-app).

#### <a name="centralized-logging"></a>Zentralisierte Protokollierung

Wenn Ihre Anwendung über mehrere Instanzen hinweg ausgeführt wird, empfiehlt es sich unter Umständen, die Protokolle an einem zentralen Ort zu speichern – beispielsweise in [Azure Storage](/azure/storage/).

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Migrieren einer SQL Server-Datenbank zu Azure](sql.md)
