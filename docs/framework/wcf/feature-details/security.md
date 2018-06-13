---
title: Windows Communication Foundation-Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: fb48ae39d269f21a7120ecf143dc4c4680efe39d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499088"
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="187a4-102">Windows Communication Foundation-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="187a4-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="187a4-103">Die Themen in diesem Abschnitt beschreiben die Windows Communication Foundation (WCF)--Sicherheitsfunktionen und ihre Verwendung zur Sicherung von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="187a4-103">The topics in this section describe Windows Communication Foundation (WCF) security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="187a4-104">Weitere Informationen zu Windows Server AppFabric und Sicherheit, finden Sie unter [Sicherheit Modell für Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="187a4-104">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="187a4-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="187a4-105">In This Section</span></span>  
 [<span data-ttu-id="187a4-106">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="187a4-106">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 <span data-ttu-id="187a4-107">Beschreibt die Sicherheitsfunktionen in WCF.</span><span class="sxs-lookup"><span data-stu-id="187a4-107">Describes the security features in WCF.</span></span>  
  
 [<span data-ttu-id="187a4-108">Begriffe der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="187a4-108">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 <span data-ttu-id="187a4-109">Beschreibt die grundlegende Terminologie und Konzepte, die in WCF-Sicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="187a4-109">Describes the basic terminology and concepts used in WCF security.</span></span>  
  
 [<span data-ttu-id="187a4-110">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="187a4-110">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 <span data-ttu-id="187a4-111">Beschreibt Szenarien und Topologien, die Sie mit WCF konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="187a4-111">Describes scenarios and topologies you can configure with WCF.</span></span>  
  
 [<span data-ttu-id="187a4-112">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="187a4-112">Security Behaviors</span></span>](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 <span data-ttu-id="187a4-113">Bietet eine Übersicht über WCF-Verhaltensweisen, die sich auf Sicherheit auswirken, z. B. das Festlegen von Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="187a4-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="187a4-114">Bindungen und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="187a4-114">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 <span data-ttu-id="187a4-115">Eine sicherheitsorientierte Ansicht der Bindungen, einschließlich Themen, die veranschaulichen, wie benutzerdefinierte Sicherheitsbindungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="187a4-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="187a4-116">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="187a4-116">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="187a4-117">Beschreibt, wie Nachrichten mithilfe von WCF-Sicherheitsfunktionen zu sichern.</span><span class="sxs-lookup"><span data-stu-id="187a4-117">Describes how to secure messages using WCF security features.</span></span>  
  
 [<span data-ttu-id="187a4-118">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="187a4-118">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
 <span data-ttu-id="187a4-119">Veranschaulicht allgemeine Authentifizierungsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="187a4-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="187a4-120">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="187a4-120">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 <span data-ttu-id="187a4-121">Beschreibt allgemeine Autorisierungsszenarien mit Sicherheitsimplementierungen.</span><span class="sxs-lookup"><span data-stu-id="187a4-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="187a4-122">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="187a4-122">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 <span data-ttu-id="187a4-123">Beschreibt die Grundlagen des Verbunds und wie Clients, die mit Verbundservern kommunizieren, erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="187a4-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="187a4-124">Teilweise Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="187a4-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 <span data-ttu-id="187a4-125">Beschreibt, wie teilweise vertrauenswürdige Szenarien und WCF-Einschränkungen ausgeführt werden, wenn teilweise vertrauenswürdig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="187a4-125">Describes how to run partially-trusted scenarios and WCF limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="187a4-126">Überwachung</span><span class="sxs-lookup"><span data-stu-id="187a4-126">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 <span data-ttu-id="187a4-127">Beschreibt, wie Sicherheitsereignisse überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="187a4-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="187a4-128">Sicherheitsleitfaden und bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="187a4-128">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 <span data-ttu-id="187a4-129">Richtlinien zum Erstellen sicherer WCF-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="187a4-129">Guidelines for creating secure WCF applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="187a4-130">Referenz</span><span class="sxs-lookup"><span data-stu-id="187a4-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="187a4-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="187a4-131">Related Sections</span></span>  
 [<span data-ttu-id="187a4-132">Details zur WCF-Funktion</span><span class="sxs-lookup"><span data-stu-id="187a4-132">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="187a4-133">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="187a4-133">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="187a4-134">Tutorial mit ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="187a4-134">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="187a4-135">Konzeptionelle Übersicht</span><span class="sxs-lookup"><span data-stu-id="187a4-135">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="187a4-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="187a4-136">See Also</span></span>  
 [<span data-ttu-id="187a4-137">Konfigurieren der Anwendung</span><span class="sxs-lookup"><span data-stu-id="187a4-137">Configuring Your Application</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
