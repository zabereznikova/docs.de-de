---
title: Vorgehensweise beim Bereitstellen von vorhandenen .NET apps in Azure App Service
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Vorgehensweise beim Bereitstellen von vorhandenen .NET apps in Azure App Service"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: aefcd79574cbbf6b3759bfa6cc0f9e46a58244ce
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-deploy-existing-net-apps-to-azure-app-service"></a><span data-ttu-id="e5f59-103">Vorgehensweise beim Bereitstellen von vorhandenen .NET apps in Azure App Service</span><span class="sxs-lookup"><span data-stu-id="e5f59-103">How to deploy existing .NET apps to Azure App Service</span></span> 

<span data-ttu-id="e5f59-104">Die Web-Apps-Funktion von Azure App Service ist ein vollständig verwalteter Compute-Plattform, die zum Hosten von Websites und Web-apps optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="e5f59-104">The Web Apps feature of Azure App Service is a fully managed compute platform that is optimized for hosting websites and web apps.</span></span> <span data-ttu-id="e5f59-105">Diese PaaS-Angebot in Microsoft Azure können sich darauf konzentrieren Sie Ihre Geschäftslogik während Azure übernimmt die Infrastruktur zum Ausführen und skalieren Ihre apps.</span><span class="sxs-lookup"><span data-stu-id="e5f59-105">This PaaS offering in Microsoft Azure lets you focus on your business logic, while Azure takes care of the infrastructure to run and scale your apps.</span></span>

## <a name="validate-sites-and-migrate-to-app-service-with-azure-app-service-migration-assistant"></a><span data-ttu-id="e5f59-106">Überprüfen Sie Standorte und Migrieren von App-Dienst mit Azure App Service-Migration Assistant</span><span class="sxs-lookup"><span data-stu-id="e5f59-106">Validate sites and migrate to App Service with Azure App Service Migration Assistant</span></span>

<span data-ttu-id="e5f59-107">Beim Erstellen einer neuen Anwendung in Visual Studio, verschieben die app in der Regel in App Service ist einfach.</span><span class="sxs-lookup"><span data-stu-id="e5f59-107">When you create a new application in Visual Studio, moving the app to App Service usually is straightforward.</span></span> <span data-ttu-id="e5f59-108">Jedoch wenn Sie planen, eine bestehende Anwendung zu App Service migrieren, müssen Sie feststellen, ob alle Ihre Anwendung Abhängigkeiten mit App Service kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="e5f59-108">However, if you are planning to migrate an existing application to App Service, first you need to evaluate whether all your application's dependencies are compatible with App Service.</span></span> <span data-ttu-id="e5f59-109">Dies schließt Abhängigkeiten wie das Betriebssystem des Servers und Drittanbieter-Software, die auf dem Server installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e5f59-109">This includes dependencies like server OS and any third-party software that's installed on the server.</span></span>

<span data-ttu-id="e5f59-110">Sie können [Azure App Service-Migration Assistant](https://www.migratetoazure.net/) zum Analysieren von Standorten und anschließend migrieren vom Windows- und Linux-Webserver zum Anwendungsdienst.</span><span class="sxs-lookup"><span data-stu-id="e5f59-110">You can use [Azure App Service Migration Assistant](https://www.migratetoazure.net/) to analyze sites and then migrate them from Windows and Linux web servers to App Service.</span></span> <span data-ttu-id="e5f59-111">Im Rahmen der Migration erstellt das Tool die Web-apps und Datenbanken in Azure bei Bedarf veröffentlicht Inhalte und Ihrer Datenbank veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e5f59-111">As part of the migration, the tool creates web apps and databases on Azure as needed, publishes content, and publishes your database.</span></span>

<span data-ttu-id="e5f59-112">Azure App Service-Migration Assistant unterstützt das Migrieren von IIS unter Windows Server ausgeführt wird, in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="e5f59-112">Azure App Service Migration Assistant supports migrating from IIS running on Windows Server to the cloud.</span></span> <span data-ttu-id="e5f59-113">App Service unterstützt Windows Server 2003 und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="e5f59-113">App Service supports Windows Server 2003 and later versions.</span></span>

> ![https://www.migratetoazure.net/Images/ImageCanvas.png](./media/image5.png)
>
> <span data-ttu-id="e5f59-115">**Abbildung 4 bis 5.**</span><span class="sxs-lookup"><span data-stu-id="e5f59-115">**Figure 4-5.**</span></span> <span data-ttu-id="e5f59-116">Mithilfe von Azure App Service-Migrations-Assistenten</span><span class="sxs-lookup"><span data-stu-id="e5f59-116">Using Azure App Service Migration Assistant</span></span>

<span data-ttu-id="e5f59-117">App Service-Migration Assistant ist ein Tool, das Ihre Websites vom Webserver in der Azure-Cloud verschiebt.</span><span class="sxs-lookup"><span data-stu-id="e5f59-117">App Service Migration Assistant is a tool that moves your websites from your web servers to the Azure cloud.</span></span>

<span data-ttu-id="e5f59-118">Nachdem eine Website zum Anwendungsdienst migriert wird, verfügt der Standort alle sicher und effizient ausführen benötigten Informationen.</span><span class="sxs-lookup"><span data-stu-id="e5f59-118">After a website is migrated to App Service, the site has everything it needs to run safely and efficiently.</span></span> <span data-ttu-id="e5f59-119">Standorte einrichten und in der Azure PaaS-Clouddienst (Anwendungsdienst) automatisch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e5f59-119">Sites are set up and run automatically in the Azure cloud PaaS service (App Service).</span></span>

<span data-ttu-id="e5f59-120">Der App Services-Migrationstool kann analysieren Ihre Websites und auf ihre Kompatibilität für die Umstellung auf Anwendungsdienst melden.</span><span class="sxs-lookup"><span data-stu-id="e5f59-120">The App Service migration tool can analyze your websites and report on their compatibility for moving to App Service.</span></span> <span data-ttu-id="e5f59-121">Wenn Sie bei der Analyse zufrieden sind, können Sie App-Dienst Migration Assistant-Inhalt, Daten und Einstellungen für die Sie migrieren lassen.</span><span class="sxs-lookup"><span data-stu-id="e5f59-121">If you're happy with the analysis, you can let App Service Migration Assistant migrate content, data, and settings for you.</span></span> <span data-ttu-id="e5f59-122">Wenn ein Standort nicht sehr kompatibel ist, weist das Migrationstool Sie gesuchte anpassen, um funktionieren.</span><span class="sxs-lookup"><span data-stu-id="e5f59-122">If a site is not quite compatible, the migration tool tells you what you need to adjust to make it work.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="e5f59-123">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e5f59-123">Additional resources</span></span>

- <span data-ttu-id="e5f59-124">**Azure App Service-Migrations-Assistenten**</span><span class="sxs-lookup"><span data-stu-id="e5f59-124">**Azure App Service Migration Assistant**</span></span>

    [<span data-ttu-id="e5f59-125">https://www.migratetoazure.net/</span><span class="sxs-lookup"><span data-stu-id="e5f59-125">https://www.migratetoazure.net/</span></span>](https://www.migratetoazure.net/)

>[!div class="step-by-step"]
<span data-ttu-id="e5f59-126">[Zurück](what-about-cloud-optimized-applications.md)
[Weiter](deploy-existing-net-apps-as-windows-containers.md)</span><span class="sxs-lookup"><span data-stu-id="e5f59-126">[Previous](what-about-cloud-optimized-applications.md)
[Next](deploy-existing-net-apps-as-windows-containers.md)</span></span>
