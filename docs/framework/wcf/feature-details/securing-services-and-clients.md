---
title: Sichern von Diensten und Clients
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: 719ab26198bd7b83310025e03e541fa11b109612
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746415"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="fe23f-102">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="fe23f-102">Securing Services and Clients</span></span>
<span data-ttu-id="fe23f-103">Die Informationen in diesem Abschnitt konzentrieren sich auf die Programmier Sicherheit in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fe23f-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="fe23f-104">Hierzu zählt im Allgemeinen das Auswählen einer geeigneten vom System bereitgestellten Bindung, das Festlegen der Eigenschaften des Sicherheitselements sowie das anschließende Festlegen von Eigenschaften für das Dienstverhalten, mit denen gesteuert wird, wie Anmeldeinformationen für die Verwendung durch den Dienst oder den Client abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fe23f-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="fe23f-105">Diese Verfahren decken die Sicherheitsanforderungen der meisten Benutzer für die meisten Szenarien ab, wie in [allgemeinen Sicherheits Szenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)dargestellt.</span><span class="sxs-lookup"><span data-stu-id="fe23f-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="fe23f-106">Wenn Ihr Szenario mehr Funktionen erfordert, sehen Sie sich zuerst die [Sicherheitsfunktionen mit benutzerdefinierten Bindungen an](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md). Wenn eine Lösung nicht ersichtlich ist, finden Sie weitere Informationen unter [Erweitern der Sicherheit](../../../../docs/framework/wcf/extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="fe23f-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="fe23f-107">Wenn Sie ein System erstellen (oder mit diesem zusammenarbeiten), das umfangreiche Ansprüche verwendet, lesen Sie die Themen unter [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="fe23f-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fe23f-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fe23f-108">In This Section</span></span>  
 [<span data-ttu-id="fe23f-109">Programmieren der WCF-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fe23f-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="fe23f-110">Eine Übersicht über das Programmiermodell, das zum Sichern von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fe23f-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="fe23f-111">Übersicht über die Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="fe23f-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="fe23f-112">Eine Übersicht über das Sichern von Nachrichten mithilfe der Transportschicht.</span><span class="sxs-lookup"><span data-stu-id="fe23f-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="fe23f-113">Nachrichtensicherheit</span><span class="sxs-lookup"><span data-stu-id="fe23f-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="fe23f-114">Fasst die Gründe für die Verwendung der Sicherheit auf Nachrichten Ebene in Windows Communication Foundation (WCF) zusammen.</span><span class="sxs-lookup"><span data-stu-id="fe23f-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="fe23f-115">Sichere Sitzungen</span><span class="sxs-lookup"><span data-stu-id="fe23f-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="fe23f-116">Eine Erläuterung der Punkte, die beim Sichern einer WCF-Sitzung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="fe23f-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="fe23f-117">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="fe23f-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="fe23f-118">Eine Erläuterung einiger der allgemeinen Aufgaben, die bei Verwendung von X.509-Zertifikaten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="fe23f-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="fe23f-119">Verweis</span><span class="sxs-lookup"><span data-stu-id="fe23f-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="fe23f-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="fe23f-120">Related Sections</span></span>  
 [<span data-ttu-id="fe23f-121">Begriffe der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fe23f-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="fe23f-122">Erweitern der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fe23f-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="fe23f-123">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="fe23f-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="fe23f-124">Bindungen und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fe23f-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="fe23f-125">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="fe23f-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="fe23f-126">Erweitern der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fe23f-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="fe23f-127">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="fe23f-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="fe23f-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe23f-128">See also</span></span>

- [<span data-ttu-id="fe23f-129">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="fe23f-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)
- <span data-ttu-id="fe23f-130">[Sicherheitsmodell für Windows Server-App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="fe23f-130">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
