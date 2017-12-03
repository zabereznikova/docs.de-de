---
title: Richtlinien und empfohlene Vorgehensweisen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, guidelines
- best practices [WCF], application design
- Windows Communication Foundation, best practices
- WCF, best practices
- Windows Communication Foundation, guidelines
ms.assetid: 5098ba46-6e8d-4e02-b0c5-d737f9fdad84
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 12599c0bdf249271e8cd28e5a7591c130b1fd920
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="guidelines-and-best-practices"></a><span data-ttu-id="a9646-102">Richtlinien und empfohlene Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="a9646-102">Guidelines and Best Practices</span></span>
<span data-ttu-id="a9646-103">Dieser Abschnitt enthält Themen, die Richtlinien zum Erstellen von [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Anwendungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a9646-103">This section contains topics that provide guidelines for creating [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a9646-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a9646-104">In This Section</span></span>  
 [<span data-ttu-id="a9646-105">Bewährte Methoden: Versionsverwaltung von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="a9646-105">Best Practices: Data Contract Versioning</span></span>](../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 <span data-ttu-id="a9646-106">Erläutert, wie und wann Datenverträge zu erstellen sind, die auch mit zukünftigen Versionen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a9646-106">Explains how and when to create data contracts that do not break when future versions are created.</span></span>  
  
 [<span data-ttu-id="a9646-107">Dienstversionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="a9646-107">Service Versioning</span></span>](../../../docs/framework/wcf/service-versioning.md)  
 <span data-ttu-id="a9646-108">Stellt Überlegungen zur Versionsverwaltung in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] vor.</span><span class="sxs-lookup"><span data-stu-id="a9646-108">Explains how to consider versioning in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="a9646-109">Nach der Bereitstellung müssen Dienste (und die durch sie verfügbar gemachten Endpunkte) eventuell angepasst werden, um neuen Geschäfts- oder IT-Anforderungen zu begegnen oder Probleme zu beheben.</span><span class="sxs-lookup"><span data-stu-id="a9646-109">After deployment, services (and the endpoints they expose) might need to be changed, for example, to satisfy changing business requirements or IT requirements, or to fix issues.</span></span> <span data-ttu-id="a9646-110">Jede Änderung führt zu einer neuen Version des Diensts.</span><span class="sxs-lookup"><span data-stu-id="a9646-110">Each change introduces a new version of the service.</span></span>  
  
 [<span data-ttu-id="a9646-111">Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a9646-111">Load Balancing</span></span>](../../../docs/framework/wcf/load-balancing.md)  
 <span data-ttu-id="a9646-112">Führt Richtlinien für den Lastenausgleich bei einer Webfarm auf.</span><span class="sxs-lookup"><span data-stu-id="a9646-112">Lists guidelines for load balancing with a Web farm.</span></span>  
  
 [<span data-ttu-id="a9646-113">Kontrollieren des Ressourcenverbrauchs und Verbessern der Leistung</span><span class="sxs-lookup"><span data-stu-id="a9646-113">Controlling Resource Consumption and Improving Performance</span></span>](../../../docs/framework/wcf/controlling-resource-consumption-and-improving-performance.md)  
 <span data-ttu-id="a9646-114">Beschreibt die Eigenschaften, die Ihnen dabei helfen sollen, einen unnötigen Ressourcenverbrauch zu vermeiden und die Sicherheit zu verbessern. Außerdem enthält dieses Thema Verweise auf detaillierte Informationen zur Verwendung dieser Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a9646-114">Describes the properties that are designed to help prevent undue resource consumption and improve security and points to more complete information about their use.</span></span>  
  
 [<span data-ttu-id="a9646-115">Bereitstellen von WCF-Anwendungen mit ClickOnce</span><span class="sxs-lookup"><span data-stu-id="a9646-115">Deploying WCF Applications with ClickOnce</span></span>](../../../docs/framework/wcf/deploying-wcf-applications-with-clickonce.md)  
 <span data-ttu-id="a9646-116">Erläutert notwendige Überlegungen bei der Verwendung von ClickOnce-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="a9646-116">Describes the considerations to be made when using the ClickOnce feature.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a9646-117">Verweis</span><span class="sxs-lookup"><span data-stu-id="a9646-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="a9646-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="a9646-118">Related Sections</span></span>  
 [<span data-ttu-id="a9646-119">Konzeptionelle Übersicht</span><span class="sxs-lookup"><span data-stu-id="a9646-119">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
  
 [<span data-ttu-id="a9646-120">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="a9646-120">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="a9646-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9646-121">See Also</span></span>  
 [<span data-ttu-id="a9646-122">Was ist die Windows Communication Foundation?</span><span class="sxs-lookup"><span data-stu-id="a9646-122">What Is Windows Communication Foundation</span></span>](../../../docs/framework/wcf/whats-wcf.md)  
 [<span data-ttu-id="a9646-123">Windows Communication Foundation-Beispiele</span><span class="sxs-lookup"><span data-stu-id="a9646-123">Windows Communication Foundation Samples</span></span>](http://msdn.microsoft.com/en-us/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
 [<span data-ttu-id="a9646-124">Konzeptionelle Übersicht</span><span class="sxs-lookup"><span data-stu-id="a9646-124">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
 [<span data-ttu-id="a9646-125">Erstellen von Clients</span><span class="sxs-lookup"><span data-stu-id="a9646-125">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)
