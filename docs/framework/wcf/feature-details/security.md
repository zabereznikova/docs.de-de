---
title: Windows Communication Foundation-Sicherheit
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
caps.latest.revision: 21
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 6b93bfff2cd97e10d9c0dba4373839337f36aacb
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="50ef5-102">Windows Communication Foundation-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="50ef5-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="50ef5-103">In den Themen dieses Abschnitts werden [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Sicherheitsfunktionen und ihre Verwendung zur Sicherung von Nachrichten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="50ef5-103">The topics in this section describe [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="50ef5-104">Weitere Informationen zu Windows Server AppFabric und Sicherheit, finden Sie unter [Sicherheit Modell für Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="50ef5-104">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50ef5-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="50ef5-105">In This Section</span></span>  
 [<span data-ttu-id="50ef5-106">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="50ef5-106">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 <span data-ttu-id="50ef5-107">Beschreibt die Sicherheitsfunktionen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50ef5-107">Describes the security features in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="50ef5-108">Begriffe der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="50ef5-108">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 <span data-ttu-id="50ef5-109">Beschreibt die grundlegende Terminologie und die grundlegenden Konzepte, die für die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Sicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50ef5-109">Describes the basic terminology and concepts used in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security.</span></span>  
  
 [<span data-ttu-id="50ef5-110">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="50ef5-110">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 <span data-ttu-id="50ef5-111">Beschreibt Szenarien und Topologien, die Sie mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="50ef5-111">Describes scenarios and topologies you can configure with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="50ef5-112">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="50ef5-112">Security Behaviors</span></span>](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 <span data-ttu-id="50ef5-113">Bietet eine Übersicht über WCF-Verhaltensweisen, die sich auf Sicherheit auswirken, z. B. das Festlegen von Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="50ef5-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="50ef5-114">Bindungen und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="50ef5-114">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 <span data-ttu-id="50ef5-115">Eine sicherheitsorientierte Ansicht der Bindungen, einschließlich Themen, die veranschaulichen, wie benutzerdefinierte Sicherheitsbindungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="50ef5-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="50ef5-116">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="50ef5-116">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="50ef5-117">Beschreibt, wie Nachrichten mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Sicherheitsfunktionen gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="50ef5-117">Describes how to secure messages using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security features.</span></span>  
  
 [<span data-ttu-id="50ef5-118">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="50ef5-118">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
 <span data-ttu-id="50ef5-119">Veranschaulicht allgemeine Authentifizierungsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="50ef5-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="50ef5-120">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="50ef5-120">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 <span data-ttu-id="50ef5-121">Beschreibt allgemeine Autorisierungsszenarien mit Sicherheitsimplementierungen.</span><span class="sxs-lookup"><span data-stu-id="50ef5-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="50ef5-122">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="50ef5-122">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 <span data-ttu-id="50ef5-123">Beschreibt die Grundlagen des Verbunds und wie Clients, die mit Verbundservern kommunizieren, erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="50ef5-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="50ef5-124">Teilweise Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="50ef5-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 <span data-ttu-id="50ef5-125">Beschreibt, wie teilweise vertrauenswürdige Szenarien und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Einschränkungen ausgeführt werden, wenn sie als teilweise vertrauenswürdig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="50ef5-125">Describes how to run partially-trusted scenarios and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="50ef5-126">Überwachung</span><span class="sxs-lookup"><span data-stu-id="50ef5-126">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 <span data-ttu-id="50ef5-127">Beschreibt, wie Sicherheitsereignisse überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="50ef5-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="50ef5-128">Sicherheitsleitfaden und bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="50ef5-128">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 <span data-ttu-id="50ef5-129">Richtlinien zum Erstellen von sicheren [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="50ef5-129">Guidelines for creating secure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="50ef5-130">Referenz</span><span class="sxs-lookup"><span data-stu-id="50ef5-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="50ef5-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="50ef5-131">Related Sections</span></span>  
 [<span data-ttu-id="50ef5-132">Details zur WCF-Funktion</span><span class="sxs-lookup"><span data-stu-id="50ef5-132">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="50ef5-133">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="50ef5-133">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="50ef5-134">Tutorial mit ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="50ef5-134">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="50ef5-135">Konzeptionelle Übersicht</span><span class="sxs-lookup"><span data-stu-id="50ef5-135">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="50ef5-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50ef5-136">See Also</span></span>  
 [<span data-ttu-id="50ef5-137">Konfigurieren der Anwendung</span><span class="sxs-lookup"><span data-stu-id="50ef5-137">Configuring Your Application</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
