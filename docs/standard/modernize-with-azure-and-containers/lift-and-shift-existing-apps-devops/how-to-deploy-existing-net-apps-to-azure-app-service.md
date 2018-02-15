---
title: Vorgehensweise beim Bereitstellen von vorhandenen .NET apps in Azure App Service
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Vorgehensweise beim Bereitstellen von vorhandenen .NET apps in Azure App Service"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 84bffe7aad6bbffb40519c9146d8156159d55850
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-deploy-existing-net-apps-to-azure-app-service"></a>Vorgehensweise beim Bereitstellen von vorhandenen .NET apps in Azure App Service 

Die Web-Apps-Funktion von Azure App Service ist ein vollständig verwalteter Compute-Plattform, die zum Hosten von Websites und Web-apps optimiert ist. Diese PaaS-Angebot in Microsoft Azure können sich darauf konzentrieren Sie Ihre Geschäftslogik während Azure übernimmt die Infrastruktur zum Ausführen und skalieren Ihre apps.

## <a name="validate-sites-and-migrate-to-app-service-with-azure-app-service-migration-assistant"></a>Überprüfen Sie Standorte und Migrieren von App-Dienst mit Azure App Service-Migration Assistant

Beim Erstellen einer neuen Anwendung in Visual Studio, verschieben die app in der Regel in App Service ist einfach. Jedoch wenn Sie planen, eine bestehende Anwendung zu App Service migrieren, müssen Sie feststellen, ob alle Ihre Anwendung Abhängigkeiten mit App Service kompatibel sind. Dies schließt Abhängigkeiten wie das Betriebssystem des Servers und Drittanbieter-Software, die auf dem Server installiert ist.

Sie können [Azure App Service-Migration Assistant](https://www.migratetoazure.net/) zum Analysieren von Standorten und anschließend migrieren vom Windows- und Linux-Webserver zum Anwendungsdienst. Im Rahmen der Migration erstellt das Tool die Web-apps und Datenbanken in Azure bei Bedarf veröffentlicht Inhalte und Ihrer Datenbank veröffentlicht werden sollen.

Azure App Service-Migration Assistant unterstützt das Migrieren von IIS unter Windows Server ausgeführt wird, in der Cloud. App Service unterstützt Windows Server 2003 und höheren Versionen.

> ![https://www.migratetoazure.net/Images/ImageCanvas.png](./media/image5.png)
>
> **Abbildung 4 bis 5.** Mithilfe von Azure App Service-Migrations-Assistenten

App Service-Migration Assistant ist ein Tool, das Ihre Websites vom Webserver in der Azure-Cloud verschiebt.

Nachdem eine Website zum Anwendungsdienst migriert wird, verfügt der Standort alle sicher und effizient ausführen benötigten Informationen. Standorte einrichten und in der Azure PaaS-Clouddienst (Anwendungsdienst) automatisch ausgeführt.

Der App Services-Migrationstool kann analysieren Ihre Websites und auf ihre Kompatibilität für die Umstellung auf Anwendungsdienst melden. Wenn Sie bei der Analyse zufrieden sind, können Sie App-Dienst Migration Assistant-Inhalt, Daten und Einstellungen für die Sie migrieren lassen. Wenn ein Standort nicht sehr kompatibel ist, weist das Migrationstool Sie gesuchte anpassen, um funktionieren.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Azure App Service-Migrations-Assistenten**

    [https://www.migratetoazure.net/](https://www.migratetoazure.net/)

>[!div class="step-by-step"]
[Zurück](what-about-cloud-optimized-applications.md)
[Weiter](deploy-existing-net-apps-as-windows-containers.md)
