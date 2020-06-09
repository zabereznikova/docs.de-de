---
title: Windows Communication Foundation-Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
ms.openlocfilehash: 327fb509a5186a0b3f428efc2ddd7f983bcfa978
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595142"
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="2245e-102">Windows Communication Foundation-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2245e-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="2245e-103">In den Themen in diesem Abschnitt werden Windows Communication Foundation (WCF)-Sicherheitsfeatures und deren Verwendung zum Sichern von Nachrichten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2245e-103">The topics in this section describe Windows Communication Foundation (WCF) security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="2245e-104">Weitere Informationen zu Windows Server AppFabric und Sicherheit finden Sie unter [Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10)) .</span><span class="sxs-lookup"><span data-stu-id="2245e-104">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2245e-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2245e-105">In This Section</span></span>  
 [<span data-ttu-id="2245e-106">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="2245e-106">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="2245e-107">Beschreibt die Sicherheitsfunktionen in WCF.</span><span class="sxs-lookup"><span data-stu-id="2245e-107">Describes the security features in WCF.</span></span>  
  
 [<span data-ttu-id="2245e-108">Sicherheitskonzepte</span><span class="sxs-lookup"><span data-stu-id="2245e-108">Security Concepts</span></span>](security-concepts.md)  
 <span data-ttu-id="2245e-109">Beschreibt die grundlegende Terminologie und Konzepte der WCF-Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="2245e-109">Describes the basic terminology and concepts used in WCF security.</span></span>  
  
 [<span data-ttu-id="2245e-110">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="2245e-110">Common Security Scenarios</span></span>](common-security-scenarios.md)  
 <span data-ttu-id="2245e-111">Beschreibt Szenarien und Topologien, die Sie mit WCF konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="2245e-111">Describes scenarios and topologies you can configure with WCF.</span></span>  
  
 [<span data-ttu-id="2245e-112">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="2245e-112">Security Behaviors</span></span>](security-behaviors-in-wcf.md)  
 <span data-ttu-id="2245e-113">Bietet eine Übersicht über WCF-Verhaltensweisen, die sich auf Sicherheit auswirken, z. B. das Festlegen von Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="2245e-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="2245e-114">Bindungen und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2245e-114">Bindings and Security</span></span>](bindings-and-security.md)  
 <span data-ttu-id="2245e-115">Eine sicherheitsorientierte Ansicht der Bindungen, einschließlich Themen, die veranschaulichen, wie benutzerdefinierte Sicherheitsbindungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2245e-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="2245e-116">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="2245e-116">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
 <span data-ttu-id="2245e-117">Beschreibt, wie Nachrichten mithilfe von WCF-Sicherheitsfunktionen gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="2245e-117">Describes how to secure messages using WCF security features.</span></span>  
  
 [<span data-ttu-id="2245e-118">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2245e-118">Authentication</span></span>](authentication-in-wcf.md)  
 <span data-ttu-id="2245e-119">Veranschaulicht allgemeine Authentifizierungsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="2245e-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="2245e-120">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="2245e-120">Authorization</span></span>](authorization-in-wcf.md)  
 <span data-ttu-id="2245e-121">Beschreibt allgemeine Autorisierungsszenarien mit Sicherheitsimplementierungen.</span><span class="sxs-lookup"><span data-stu-id="2245e-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="2245e-122">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="2245e-122">Federation and Issued Tokens</span></span>](federation-and-issued-tokens.md)  
 <span data-ttu-id="2245e-123">Beschreibt die Grundlagen des Verbunds und wie Clients, die mit Verbundservern kommunizieren, erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2245e-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="2245e-124">Teilweise Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="2245e-124">Partial Trust</span></span>](partial-trust.md)  
 <span data-ttu-id="2245e-125">Beschreibt das Ausführen teilweise vertrauenswürdiger Szenarien und WCF-Einschränkungen bei der Ausführung teilweise vertrauenswürdiger Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="2245e-125">Describes how to run partially-trusted scenarios and WCF limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="2245e-126">Auditing</span><span class="sxs-lookup"><span data-stu-id="2245e-126">Auditing</span></span>](auditing-security-events.md)  
 <span data-ttu-id="2245e-127">Beschreibt, wie Sicherheitsereignisse überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="2245e-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="2245e-128">Sicherheitsleitfaden und empfohlene Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="2245e-128">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)  
 <span data-ttu-id="2245e-129">Richtlinien zum Erstellen von sicheren WCF-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="2245e-129">Guidelines for creating secure WCF applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2245e-130">Referenz</span><span class="sxs-lookup"><span data-stu-id="2245e-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="2245e-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="2245e-131">Related Sections</span></span>  
 [<span data-ttu-id="2245e-132">Details zur WCF-Funktion</span><span class="sxs-lookup"><span data-stu-id="2245e-132">WCF Feature Details</span></span>](index.md)  
  
 [<span data-ttu-id="2245e-133">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="2245e-133">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
 [<span data-ttu-id="2245e-134">Tutorial zu den ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="2245e-134">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)  
  
 [<span data-ttu-id="2245e-135">Konzeptionelle Übersicht</span><span class="sxs-lookup"><span data-stu-id="2245e-135">Conceptual Overview</span></span>](../conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="2245e-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2245e-136">See also</span></span>

- [<span data-ttu-id="2245e-137">Konfigurieren der Anwendung</span><span class="sxs-lookup"><span data-stu-id="2245e-137">Configuring Your Application</span></span>](../diagnostics/configuring-your-application.md)
