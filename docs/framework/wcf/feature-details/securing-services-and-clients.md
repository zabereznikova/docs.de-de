---
title: Sichern von Diensten und Clients
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: e455c7a48e1484d5acdcc5f6cdc9098997a3ba83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120728"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="5e070-102">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="5e070-102">Securing Services and Clients</span></span>
<span data-ttu-id="5e070-103">Die Informationen in diesem Abschnitt programmiersicherheit in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5e070-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="5e070-104">Hierzu zählt im Allgemeinen das Auswählen einer geeigneten vom System bereitgestellten Bindung, das Festlegen der Eigenschaften des Sicherheitselements sowie das anschließende Festlegen von Eigenschaften für das Dienstverhalten, mit denen gesteuert wird, wie Anmeldeinformationen für die Verwendung durch den Dienst oder den Client abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5e070-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="5e070-105">Diese Techniken decken die sicherheitsanforderungen der meisten Benutzer in den meisten Fällen, siehe [häufige Sicherheitsszenarien](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="5e070-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="5e070-106">Wenn Ihr Szenario mehr Funktionen erforderlich sind, lesen Sie zunächst [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); ist eine Lösung nicht offensichtlich ist, finden Sie unter [Erweitern von Sicherheit](../../../../docs/framework/wcf/extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="5e070-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="5e070-107">Wenn Sie erstellen (oder Interoperabilität mit) ein System, das umfangreiche Ansprüche verwendet, finden Sie unter den Themen in [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="5e070-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e070-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5e070-108">In This Section</span></span>  
 [<span data-ttu-id="5e070-109">Programmieren der WCF-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5e070-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="5e070-110">Eine Übersicht über das Programmiermodell, das zum Sichern von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5e070-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="5e070-111">Übersicht über die Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="5e070-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="5e070-112">Eine Übersicht über das Sichern von Nachrichten mithilfe der Transportschicht.</span><span class="sxs-lookup"><span data-stu-id="5e070-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="5e070-113">Nachrichtensicherheit</span><span class="sxs-lookup"><span data-stu-id="5e070-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="5e070-114">Eine Zusammenfassung von Gründen für die Verwendung von Sicherheit auf Nachrichtenebene in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5e070-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="5e070-115">Sichere Sitzungen</span><span class="sxs-lookup"><span data-stu-id="5e070-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="5e070-116">Eine Erläuterung der Aspekte ist erforderlich, wenn eine WCF-Sitzung zu sichern.</span><span class="sxs-lookup"><span data-stu-id="5e070-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="5e070-117">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="5e070-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="5e070-118">Eine Erläuterung einiger der allgemeinen Aufgaben, die bei Verwendung von X.509-Zertifikaten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5e070-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5e070-119">Referenz</span><span class="sxs-lookup"><span data-stu-id="5e070-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="5e070-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="5e070-120">Related Sections</span></span>  
 [<span data-ttu-id="5e070-121">Begriffe der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5e070-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="5e070-122">Erweitern der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5e070-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="5e070-123">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="5e070-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="5e070-124">Bindungen und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5e070-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="5e070-125">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="5e070-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="5e070-126">Erweitern der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5e070-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="5e070-127">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="5e070-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="5e070-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e070-128">See also</span></span>

- [<span data-ttu-id="5e070-129">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="5e070-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="5e070-130">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="5e070-130">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
