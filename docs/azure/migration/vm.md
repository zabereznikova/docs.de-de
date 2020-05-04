---
title: Migrieren einer ASP.NET-Web-App zu einer Azure-VM
description: Hier erfahren Sie, wie Sie eine ASP.NET-Webanwendung aus einer lokalen Umgebung zu einem virtuellen Azure-Computer migrieren.
ms.topic: how-to
ms.date: 11/15/2017
ms.openlocfilehash: cc9477de92e6105762636ed3a2241949e69ac8ea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "81433361"
---
# <a name="migrate-an-aspnet-web-application-to-an-azure-virtual-machine"></a><span data-ttu-id="b9443-103">Migrieren einer ASP.NET-Webanwendung zu einem virtuellen Azure-Computer</span><span class="sxs-lookup"><span data-stu-id="b9443-103">Migrate an ASP.NET Web application to an Azure Virtual Machine</span></span>

<span data-ttu-id="b9443-104">In diesem Übersichtsdokument erfahren Sie, wie Sie eine ASP.NET-Webanwendung aus einer lokalen Umgebung zu einem virtuellen Azure-Computer migrieren.</span><span class="sxs-lookup"><span data-stu-id="b9443-104">This document provides an overview of how to migrate an ASP.NET web application from on-premises to an Azure Virtual Machine.</span></span>

## <a name="quickstart"></a><span data-ttu-id="b9443-105">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="b9443-105">Quickstart</span></span>

<span data-ttu-id="b9443-106">Informationen zum Erstellen eines virtuellen Computers und Veröffentlichen Ihrer App darauf: [Veröffentlichen auf einem virtuellen Azure-Computer](https://tutorials.visualstudio.com/aspnet-vm/intro)</span><span class="sxs-lookup"><span data-stu-id="b9443-106">Learn how to create a virtual machine and publish your app to it: [Publish to an Azure VM](https://tutorials.visualstudio.com/aspnet-vm/intro)</span></span>

## <a name="get-started"></a><span data-ttu-id="b9443-107">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="b9443-107">Get Started</span></span>

<span data-ttu-id="b9443-108">Die folgenden Tutorials zeigen Schritt für Schritt, wie Sie einen virtuellen Computer erstellen (oder migrieren), Ihre Webanwendung für den virtuellen Computer veröffentlichen und andere Aufgaben durchführen, die ggf. erforderlich sind, damit Ihre Anwendung in Azure unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="b9443-108">These tutorials demonstrate the steps to create (or migrate) a virtual machine, publish your web application to it, and other tasks that may be required to support your application in Azure.</span></span>

- <span data-ttu-id="b9443-109">Erstellen Sie mithilfe einer der folgenden Optionen einen virtuellen Computer für Ihre ASP.NET-Anwendung in Azure:</span><span class="sxs-lookup"><span data-stu-id="b9443-109">Create a virtual machine for your ASP.NET application in Azure using one of the following options:</span></span>
  - [<span data-ttu-id="b9443-110">Erstellen eines neuen virtuellen Computers für ASP.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b9443-110">Create a new virtual machine for ASP.NET Applications</span></span>](https://go.microsoft.com/fwlink/?linkid=863237)
  - [<span data-ttu-id="b9443-111">Migrieren von VMware-VMs zu Azure (ohne Agent)</span><span class="sxs-lookup"><span data-stu-id="b9443-111">Migrate an existing on-premises VMWare virtual machine</span></span>](https://docs.microsoft.com/azure/migrate/tutorial-migrate-vmware)
  - [<span data-ttu-id="b9443-112">Migrieren von virtuellen Hyper-V-Computern zu Azure</span><span class="sxs-lookup"><span data-stu-id="b9443-112">Migrate an existing on-premises Hyper-V virtual machine</span></span>](https://docs.microsoft.com/azure/migrate/tutorial-migrate-hyper-v)
- [<span data-ttu-id="b9443-113">Veröffentlichen Ihrer App mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b9443-113">Publish your app using Visual Studio</span></span>](https://go.microsoft.com/fwlink/?linkid=863240)
- [<span data-ttu-id="b9443-114">Erstellen eines sicheren virtuellen Netzwerks für Ihre virtuellen Computer</span><span class="sxs-lookup"><span data-stu-id="b9443-114">Create a secure virtual network for your VMs</span></span>](https://docs.microsoft.com/azure/virtual-network/virtual-network-get-started-vnet-subnet)
- [<span data-ttu-id="b9443-115">Erstellen einer CI/CD-Pipeline für Ihre Anwendung</span><span class="sxs-lookup"><span data-stu-id="b9443-115">Create a CI/CD pipeline for your application</span></span>](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-webdeploy-iis-deploygroups)
- [<span data-ttu-id="b9443-116">Verwenden einer VM-Skalierungsgruppe für hohe Verfügbarkeit und Skalierbarkeit</span><span class="sxs-lookup"><span data-stu-id="b9443-116">Move to a VM scale set for high availability and scalability</span></span>](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-deploy-app)

## <a name="considerations"></a><span data-ttu-id="b9443-117">Weitere Überlegungen</span><span class="sxs-lookup"><span data-stu-id="b9443-117">Considerations</span></span>

### <a name="benefits"></a><span data-ttu-id="b9443-118">Vorteile</span><span class="sxs-lookup"><span data-stu-id="b9443-118">Benefits</span></span>

<span data-ttu-id="b9443-119">Mit virtuellen Computern lässt sich eine Anwendung am einfachsten aus der lokalen Umgebung zur Cloud migrieren.</span><span class="sxs-lookup"><span data-stu-id="b9443-119">Virtual machines offer the easiest path to migrate an application from on-premises to the cloud.</span></span> <span data-ttu-id="b9443-120">Sie ermöglichen die Replizierung der gleichen Umgebung, die Ihre Anwendung auch lokal verwendet, haben aber den Vorteil, dass Sie keine eigenen Rechenzentren mehr verwalten müssen.</span><span class="sxs-lookup"><span data-stu-id="b9443-120">They enable you to replicate the same environment your application uses on-premises, while removing the need to maintain your own data centers.</span></span> <span data-ttu-id="b9443-121">VM-Skalierungsgruppen bieten hohe Verfügbarkeit und Skalierbarkeit für Anwendungen, die in Virtual Machines ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b9443-121">Virtual Machine Scale Sets provide high availability and scalability for applications running in Virtual Machines.</span></span>

### <a name="virtual-machine-size"></a><span data-ttu-id="b9443-122">VM-Größe</span><span class="sxs-lookup"><span data-stu-id="b9443-122">Virtual Machine Size</span></span>

<span data-ttu-id="b9443-123">Wählen Sie eine VM-Größe und einen VM-Typ, die am besten für Ihre Workload geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="b9443-123">Choose the virtual machine size and type that is best optimized for your workload.</span></span> <span data-ttu-id="b9443-124">Weitere Informationen finden Sie unter [Größen für virtuelle Windows-Computer in Azure](https://docs.microsoft.com/azure/virtual-machines/windows/sizes).</span><span class="sxs-lookup"><span data-stu-id="b9443-124">For more information, see [Sizes for Windows virtual machines in Azure](https://docs.microsoft.com/azure/virtual-machines/windows/sizes).</span></span>

### <a name="maintenance"></a><span data-ttu-id="b9443-125">Wartung </span><span class="sxs-lookup"><span data-stu-id="b9443-125">Maintenance</span></span>

<span data-ttu-id="b9443-126">Virtuelle Computer müssen genau wie lokale Computer gewartet und aktualisiert werden<sup>&#42;</sup>.</span><span class="sxs-lookup"><span data-stu-id="b9443-126">Just like an on-premises machine, you are responsible for maintaining and updating the virtual machine<sup>&#42;</sup>.</span></span> <span data-ttu-id="b9443-127">Bei Anwendungen, die in einer PaaS-Umgebung (Plattform-as-a-Service) wie etwa [Azure App Service](https://docs.microsoft.com/azure/app-service/) oder in einem [Container](https://docs.microsoft.com/azure/app-service/containers/) ausgeführt werden können, entfällt diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="b9443-127">If your application can run in a Platform as a Service (PaaS) environment such as [Azure App Service](https://docs.microsoft.com/azure/app-service/) or in a [container](https://docs.microsoft.com/azure/app-service/containers/), that will remove this need.</span></span>

<span data-ttu-id="b9443-128">*<sup>&#42;</sup>[Automatische Betriebssystemupgrades für Azure-VM-Skalierungsgruppen](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-automatic-upgrade) stehen derzeit als Vorschauversion zur Verfügung.*</span><span class="sxs-lookup"><span data-stu-id="b9443-128">*<sup>&#42;</sup>[Automatic OS upgrades for virtual machine scale sets](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-automatic-upgrade) is currently available as a Preview service.*</span></span>

### <a name="virtual-networks"></a><span data-ttu-id="b9443-129">Virtuelle Netzwerke</span><span class="sxs-lookup"><span data-stu-id="b9443-129">Virtual Networks</span></span>

<span data-ttu-id="b9443-130">Virtuelle Azure-Netzwerke ermöglichen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b9443-130">Azure Virtual Networks enable you to:</span></span>

- <span data-ttu-id="b9443-131">Erstellen einer von Ihnen kontrollierten Hybridinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="b9443-131">Build a hybrid infrastructure that you control</span></span>
- <span data-ttu-id="b9443-132">Verwenden eigener IP-Adressen und DNS-Server</span><span class="sxs-lookup"><span data-stu-id="b9443-132">Bring your own IP addresses and DNS servers</span></span>
- <span data-ttu-id="b9443-133">Schaffen einer isolierten und hochsicheren Umgebung für Ihre Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b9443-133">Create an isolated and highly secure environment for your applications</span></span>
- <span data-ttu-id="b9443-134">Herstellen einer Verbindung zwischen Ihrem virtuellen Computer und Ihrem lokalen Netzwerk über eine der verfügbaren [Verbindungsoptionen](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways#s2smulti)</span><span class="sxs-lookup"><span data-stu-id="b9443-134">Connect your VM to your on-premises network using one of several [connectivity options](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways#s2smulti)</span></span>
- <span data-ttu-id="b9443-135">Integrieren Ihres virtuellen Computers in Ihr lokales Netzwerk mithilfe von [ExpressRoute](https://azure.microsoft.com/services/expressroute/)</span><span class="sxs-lookup"><span data-stu-id="b9443-135">Integrate your virtual machine into your on-premises network using [ExpressRoute](https://azure.microsoft.com/services/expressroute/)</span></span>

<span data-ttu-id="b9443-136">Informationen zu den ersten Schritten finden Sie in der [Dokumentation zu Virtual Network](https://docs.microsoft.com/azure/virtual-network/).</span><span class="sxs-lookup"><span data-stu-id="b9443-136">To get started, see the [Virtual Network documentation](https://docs.microsoft.com/azure/virtual-network/)</span></span>

### <a name="active-directory"></a><span data-ttu-id="b9443-137">Active Directory</span><span class="sxs-lookup"><span data-stu-id="b9443-137">Active Directory</span></span>
<span data-ttu-id="b9443-138">Viele Anwendungen verwenden Active Directory für die Authentifizierung und Identitätsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="b9443-138">Many applications use Active Directory for authentication and identity management.</span></span>

- <span data-ttu-id="b9443-139">Mit Azure AD Connect können Sie Ihre lokalen Verzeichnisse in Azure Active Directory integrieren.</span><span class="sxs-lookup"><span data-stu-id="b9443-139">Azure AD Connect enables you to integrate your on-premises directories with Azure Active Directory.</span></span> <span data-ttu-id="b9443-140">Informationen zu den ersten Schritten finden Sie unter [Integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="b9443-140">To get started, see [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="b9443-141">Alternativ können Sie Ihrer Anwendung mit [ExpressRoute](https://azure.microsoft.com/services/expressroute/) den Zugriff auf Ihr lokales Active Directory ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b9443-141">Alternatively, [ExpressRoute](https://azure.microsoft.com/services/expressroute/) enables your application to access your on-premises Active Directory.</span></span>

### <a name="sql-databases"></a><span data-ttu-id="b9443-142">SQL-DATENBANKEN</span><span class="sxs-lookup"><span data-stu-id="b9443-142">SQL Databases</span></span>

<span data-ttu-id="b9443-143">Wenn Ihre Anwendung eine lokale Datenbank verwendet, kann sie standardmäßig nicht mit ihr kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="b9443-143">If your application is using an on-premises database, your app will not be able to talk to it by default.</span></span> <span data-ttu-id="b9443-144">Sie haben folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="b9443-144">You can either:</span></span>

- <span data-ttu-id="b9443-145">Konfigurieren Sie ein Hybridnetzwerk, über das Ihre Anwendung auf die lokal ausgeführte Datenbank zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="b9443-145">Configure a hybrid network that enables your application to access your database running on-premises.</span></span>
- <span data-ttu-id="b9443-146">Migrieren Sie Ihre Datenbank zu Azure.</span><span class="sxs-lookup"><span data-stu-id="b9443-146">Migrate your database to the Azure.</span></span> <span data-ttu-id="b9443-147">Weitere Informationen finden Sie unter [Migrieren einer ASP.NET-Webanwendung zu einem virtuellen Azure-Computer](sql.md).</span><span class="sxs-lookup"><span data-stu-id="b9443-147">For more information, see [Migrate your SQL Server database to Azure](sql.md).</span></span>

### <a name="high-availability-and-scalability"></a><span data-ttu-id="b9443-148">Hochverfügbarkeit und Skalierbarkeit</span><span class="sxs-lookup"><span data-stu-id="b9443-148">High Availability and Scalability</span></span>

#### <a name="virtual-machine-scale-sets"></a><span data-ttu-id="b9443-149">Virtual Machine Scale Sets</span><span class="sxs-lookup"><span data-stu-id="b9443-149">Virtual Machine Scale Sets</span></span>
<span data-ttu-id="b9443-150">Wenn Ihre Anwendung hochverfügbar und skalierbar sein soll, empfiehlt es sich, das VM-Image zu einer Azure-VM-Skalierungsgruppe zu migrieren, um die Verfügbarkeit und Skalierbarkeit der Anwendung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b9443-150">You want to make sure that your application is highly available and can scale, migrate your VM image to an Azure Virtual Machine Scale Set to improve the availability and scalability of your application.</span></span> <span data-ttu-id="b9443-151">Mit VM-Skalierungsgruppen können Sie einen bereits konfigurierten virtuellen Computer verwenden oder eine Buildpipeline für die Erstellung eines Images mit Ihrer Anwendung einrichten.</span><span class="sxs-lookup"><span data-stu-id="b9443-151">VM Scale Sets provide the ability to use an existing VM you've already configured or set up a build pipeline to build an image with your application.</span></span>

<span data-ttu-id="b9443-152">Informationen zu den ersten Schritten finden Sie unter [Bereitstellen der App in VM-Skalierungsgruppen](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-deploy-app).</span><span class="sxs-lookup"><span data-stu-id="b9443-152">To get started, see [Deploy your application on virtual machine scale sets](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-deploy-app).</span></span>

#### <a name="centralized-logging"></a><span data-ttu-id="b9443-153">Zentralisierte Protokollierung</span><span class="sxs-lookup"><span data-stu-id="b9443-153">Centralized Logging</span></span>
<span data-ttu-id="b9443-154">Wenn Ihre Anwendung über mehrere Instanzen hinweg ausgeführt wird, empfiehlt es sich unter Umständen, die Protokolle an einem zentralen Ort zu speichern – beispielsweise in [Azure Storage](https://docs.microsoft.com/azure/storage/).</span><span class="sxs-lookup"><span data-stu-id="b9443-154">When running your application across multiple instances, consider storing your logs in a centralized location such as [Azure Storage](https://docs.microsoft.com/azure/storage/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b9443-155">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b9443-155">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b9443-156">Migrieren einer SQL Server-Datenbank zu Azure</span><span class="sxs-lookup"><span data-stu-id="b9443-156">Migrate a SQL Server database to Azure</span></span>](sql.md)
