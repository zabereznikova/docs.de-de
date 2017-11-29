---
title: Windows Communication Foundation-Endpunkte
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: endpoints [WCF]
ms.assetid: bd0c310f-dd9f-4081-9be2-3db5909850b6
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4ac3d1f16d860ea01217d0d1d35d0588da0c8d87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="windows-communication-foundation-endpoints"></a><span data-ttu-id="9ac77-102">Windows Communication Foundation-Endpunkte</span><span class="sxs-lookup"><span data-stu-id="9ac77-102">Windows Communication Foundation Endpoints</span></span>
<span data-ttu-id="9ac77-103">Die gesamte Kommunikation mit einem [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] -Dienst verläuft über die *Endpunkte* des Diensts.</span><span class="sxs-lookup"><span data-stu-id="9ac77-103">All communication with a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="9ac77-104">Endpunkte ermöglichen Clients den Zugriff auf die Funktionalität, die ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst anbietet.</span><span class="sxs-lookup"><span data-stu-id="9ac77-104">Endpoints provide clients access to the functionality that a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service offers.</span></span>  
  
 <span data-ttu-id="9ac77-105">Eine Übersicht darüber, wie Sie einen Endpunkt zu erstellen, finden Sie unter [Endpunkterstellung](../../../docs/framework/wcf/endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9ac77-105">For an overview about how to create an endpoint, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="9ac77-106">Jeder Endpunkt enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9ac77-106">Each endpoint contains:</span></span>  
  
-   <span data-ttu-id="9ac77-107">Eine Adresse, die angibt, wo der Endpunkt zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="9ac77-107">An address that indicates where to find the endpoint.</span></span>  
  
-   <span data-ttu-id="9ac77-108">Eine Bindung, die angibt, wie ein Client mit dem Endpunkt kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="9ac77-108">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
-   <span data-ttu-id="9ac77-109">Ein Vertrag, der die verfügbaren Methoden identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9ac77-109">A contract that identifies the methods available.</span></span>  
  
 <span data-ttu-id="9ac77-110">Beschreibungen, wie Sie diese einzelnen Teile eines Endpunkts angeben, finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="9ac77-110">For descriptions about how to specify these individual parts of an endpoint, see:</span></span>  
  
-   [<span data-ttu-id="9ac77-111">Angeben einer Endpunktadresse</span><span class="sxs-lookup"><span data-stu-id="9ac77-111">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
  
-   [<span data-ttu-id="9ac77-112">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="9ac77-112">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
  
-   [<span data-ttu-id="9ac77-113">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="9ac77-113">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="in-this-section"></a><span data-ttu-id="9ac77-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9ac77-114">In This Section</span></span>  
 [<span data-ttu-id="9ac77-115">Übersicht über die Endpunkterstellung</span><span class="sxs-lookup"><span data-stu-id="9ac77-115">Endpoint Creation Overview</span></span>](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 <span data-ttu-id="9ac77-116">Beschreibt die Struktur eines Endpunkts und erläutert, wie Sie einen Endpunkt in einer Konfiguration oder im Code definieren und wie die Standardendpunkte, Bindungen und Verhalten von der Runtime bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9ac77-116">Describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code, as well as how to use the default endpoints, bindings, and behaviors provided by the runtime.</span></span>  
  
 [<span data-ttu-id="9ac77-117">Angeben einer Endpunktadresse</span><span class="sxs-lookup"><span data-stu-id="9ac77-117">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 <span data-ttu-id="9ac77-118">Beschreibt, wie die Kommunikation mit einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst über Endpunkte erfolgt.</span><span class="sxs-lookup"><span data-stu-id="9ac77-118">Describes how communication with a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service occurs through endpoints.</span></span>  
  
 [<span data-ttu-id="9ac77-119">Vorgehensweise: Erstellen eines Dienstendpunkts in der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9ac77-119">How to: Create a Service Endpoint in Configuration</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="9ac77-120">Veranschaulicht, wie Sie einen Dienstendpunkt in einer Konfiguration erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ac77-120">Demonstrates how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="9ac77-121">Vorgehensweise: Erstellen eines Dienstendpunkts im Code</span><span class="sxs-lookup"><span data-stu-id="9ac77-121">How to: Create a Service Endpoint in Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="9ac77-122">Veranschaulicht, wie Sie einen Dienstendpunkt im Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ac77-122">Demonstrates how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="9ac77-123">Veröffentlichen von Metadatenendpunkten</span><span class="sxs-lookup"><span data-stu-id="9ac77-123">Publishing Metadata Endpoints</span></span>](../../../docs/framework/wcf/publishing-metadata-endpoints.md)  
 <span data-ttu-id="9ac77-124">Veranschaulicht, wie Sie Metadaten veröffentlichen, indem Sie Metadatenendpunkte in der Konfiguration und im Code veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="9ac77-124">Demonstrates how to publish metadata by publishing metadata endpoints in configuration and in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9ac77-125">Verweis</span><span class="sxs-lookup"><span data-stu-id="9ac77-125">Reference</span></span>  
 <xref:System.ServiceModel.EndpointAddress>  
  
## <a name="related-sections"></a><span data-ttu-id="9ac77-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="9ac77-126">Related Sections</span></span>  
 [<span data-ttu-id="9ac77-127">Grundlegender Programmierlebenszyklus</span><span class="sxs-lookup"><span data-stu-id="9ac77-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)
