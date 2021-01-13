---
title: Übersicht über das Azure SDK für .NET
description: Bietet eine Übersicht über das Azure SDK für .NET und beschreibt die grundlegenden Schritte zur Verwendung des SDK in einer .NET-Anwendung
ms.date: 11/30/2020
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 3ec1ee9e8da3a6e03581ce2a29a655ec0d68fe54
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700902"
---
# <a name="azure-sdk-for-net-overview"></a><span data-ttu-id="a245e-103">Übersicht über das Azure SDK für .NET</span><span class="sxs-lookup"><span data-stu-id="a245e-103">Azure SDK for .NET overview</span></span>

## <a name="what-is-the-azure-sdk-for-net"></a><span data-ttu-id="a245e-104">Was ist das Azure SDK für .NET?</span><span class="sxs-lookup"><span data-stu-id="a245e-104">What is the Azure SDK for .NET</span></span>

<span data-ttu-id="a245e-105">Das **Azure SDK für .NET** wurde entwickelt, um die Verwendung von Azure-Diensten aus Ihren .NET-Anwendungen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="a245e-105">The **Azure SDK for .NET** is designed to make it easy to use Azure services from your .NET applications.</span></span>  <span data-ttu-id="a245e-106">Das Azure SDK für .NET bietet eine konsistente und vertraute Oberfläche für den Zugriff auf Azure-Dienste, unabhängig davon, ob Dateien in Blob Storage hochgeladen und heruntergeladen, Anwendungsgeheimnisse aus Azure Key Vault abgerufen oder Benachrichtigungen von Azure Event Hubs verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="a245e-106">Whether it is uploading and downloading files to Blob Storage, retrieving application secrets from Azure Key Vault, or processing notifications from Azure Event Hubs, the Azure SDK for .NET provides a consistent and familiar interface to access Azure services.</span></span>  

<span data-ttu-id="a245e-107">Das Azure SDK für .NET ist als Reihe von NuGet-Paketen verfügbar, die in .NET Core-Anwendungen (2.1 und höher) und .NET Framework (4.6.1 und höher) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a245e-107">The Azure SDK for .NET is available as series of NuGet packages that can be used in both .NET Core (2.1 and higher) and .NET Framework (4.6.1 and higher) applications.</span></span>

![Diagramm, das zeigt, wie .NET-Anwendungen mit dem Azure SDK auf Azure-Dienste zugreifen](./media/azure-sdk-for-dotnet-overview.png)

## <a name="use-the-azure-sdk-for-net-in-your-applications"></a><span data-ttu-id="a245e-109">Verwenden des Azure SDK für .NET in Ihren Anwendungen</span><span class="sxs-lookup"><span data-stu-id="a245e-109">Use the Azure SDK for .NET in your applications</span></span>

<span data-ttu-id="a245e-110">Wenn Sie ein Azure SDK-Paket in einer Ihrer .NET-Anwendungen verwenden möchten, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="a245e-110">To use an Azure SDK package in one of your .NET applications, you want to follow these steps.</span></span>

1. <span data-ttu-id="a245e-111">**Suchen des entsprechenden SDK-Pakets:** Verwenden Sie die [Paketliste](../packages.md), um das entsprechende Paket für den verwendeten Azure-Dienst zu suchen.</span><span class="sxs-lookup"><span data-stu-id="a245e-111">**Locate the appropriate SDK package -** Use the [package list](../packages.md) to find the appropriate package for the Azure service you are working with.</span></span>  <span data-ttu-id="a245e-112">Beachten Sie, dass die meisten Dienste über ein Clientpaket zum Arbeiten mit dem Dienst und ein Verwaltungspaket zum Erstellen und Verwalten von Instanzen des Diensts verfügen.</span><span class="sxs-lookup"><span data-stu-id="a245e-112">Be advised that most services have a client package for working with the service and a management package for creating and managing instances of the service.</span></span>  <span data-ttu-id="a245e-113">In den meisten Fällen benötigen Sie das Clientpaket.</span><span class="sxs-lookup"><span data-stu-id="a245e-113">In most cases, you will want the client package.</span></span>  <span data-ttu-id="a245e-114">Installieren Sie dieses Paket in Ihrer Anwendung mithilfe von NuGet.</span><span class="sxs-lookup"><span data-stu-id="a245e-114">Install this package in your application using NuGet.</span></span>

2. <span data-ttu-id="a245e-115">**Einrichten der Authentifizierung für Ihre Anwendung:** Für den Zugriff auf Azure-Ressourcen muss Ihre Anwendung über die erforderlichen Anmeldeinformationen und die entsprechenden in Azure zugewiesenen Zugriffsrechte verfügen.</span><span class="sxs-lookup"><span data-stu-id="a245e-115">**Set up authentication for your application -** To access Azure resources, your application will need to have the appropriate credentials and access rights assigned in Azure.</span></span>  <span data-ttu-id="a245e-116">Informationen zum Konfigurieren der Authentifizierung finden Sie unter [Authentifizieren von .NET-Anwendungen in Azure](../authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a245e-116">Learn how to configure authentication in [Authenticating .NET applications to Azure](../authentication.md).</span></span>

3. <span data-ttu-id="a245e-117">**Schreiben von Code mithilfe des SDK in Ihrer Anwendung:** Beim Arbeiten mit Azure-Diensten erstellt der Code zunächst ein Clientobjekt zum Arbeiten mit dem Dienst und ruft dann Methoden für dieses Clientobjekt zum Interagieren mit dem Dienst auf.</span><span class="sxs-lookup"><span data-stu-id="a245e-117">**Write code using the SDK in your application -** When working with Azure services, your code will first create a client object to work with the service and then call methods on that client object to interact with the service.</span></span>  <span data-ttu-id="a245e-118">Es werden sowohl synchrone als auch asynchrone Methoden bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a245e-118">Both synchronous and asynchronous methods are provided.</span></span>  <span data-ttu-id="a245e-119">Beispiele für die Verwendung der einzelnen SDK-Pakete finden Sie in der Azure-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a245e-119">Examples of using each individual SDK package are provided throughout the Azure documentation.</span></span>

4. <span data-ttu-id="a245e-120">**Konfigurieren der Protokollierung für das SDK (optional):** Wenn Sie Probleme zwischen Ihrer Anwendung und Azure diagnostizieren müssen, können Sie die [Protokollierung im Azure SDK für .NET aktivieren](./logging.md).</span><span class="sxs-lookup"><span data-stu-id="a245e-120">**Configure logging for the SDK (optional) -** If you need to diagnose issues between your application and Azure, you can [enable logging in the Azure SDK for .NET](./logging.md).</span></span>
