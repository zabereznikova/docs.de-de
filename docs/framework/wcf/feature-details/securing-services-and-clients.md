---
title: Sichern von Diensten und Clients
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ed37992b5488d33b9292bdd54eef47f9eb12f225
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="7bb3b-102">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="7bb3b-102">Securing Services and Clients</span></span>
<span data-ttu-id="7bb3b-103">Im Mittelpunkt dieses Abschnitts stehen Informationen zur Programmiersicherheit in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bb3b-103">The information in this section focuses on programming security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="7bb3b-104">Hierzu zählt im Allgemeinen das Auswählen einer geeigneten vom System bereitgestellten Bindung, das Festlegen der Eigenschaften des Sicherheitselements sowie das anschließende Festlegen von Eigenschaften für das Dienstverhalten, mit denen gesteuert wird, wie Anmeldeinformationen für die Verwendung durch den Dienst oder den Client abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7bb3b-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="7bb3b-105">Diese Techniken die sicherheitsanforderungen der meisten Benutzer in den meisten Szenarien abzudecken, wie gezeigt in [häufige Sicherheitsszenarien](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="7bb3b-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="7bb3b-106">Wenn Ihr Szenario mehr Funktionen erfordert, zuerst finden Sie unter [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); ist eine Lösung nicht offensichtlich, finden Sie unter [Erweitern der Sicherheit](../../../../docs/framework/wcf/extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="7bb3b-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="7bb3b-107">Wenn Sie erstellen (oder Interoperabilität mit) ein Systems, die umfangreiche Ansprüche verwendet, finden Sie unter den Themen in [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="7bb3b-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7bb3b-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7bb3b-108">In This Section</span></span>  
 [<span data-ttu-id="7bb3b-109">Programmieren der WCF-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7bb3b-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="7bb3b-110">Eine Übersicht über das Programmiermodell, das zum Sichern von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7bb3b-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="7bb3b-111">Übersicht über die transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="7bb3b-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="7bb3b-112">Eine Übersicht über das Sichern von Nachrichten mithilfe der Transportschicht.</span><span class="sxs-lookup"><span data-stu-id="7bb3b-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="7bb3b-113">Nachrichtensicherheit</span><span class="sxs-lookup"><span data-stu-id="7bb3b-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="7bb3b-114">Eine Zusammenfassung von Gründen für die Verwendung der Sicherheit auf Nachrichtenebene in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bb3b-114">Summarizes reasons for using message-level security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
 [<span data-ttu-id="7bb3b-115">Sichere Sitzungen</span><span class="sxs-lookup"><span data-stu-id="7bb3b-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="7bb3b-116">Eine Diskussion der erforderlichen Überlegungen für das Sichern einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7bb3b-116">A discussion of the considerations required when securing a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] session.</span></span>  
  
 [<span data-ttu-id="7bb3b-117">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="7bb3b-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="7bb3b-118">Eine Erläuterung einiger der allgemeinen Aufgaben, die bei Verwendung von X.509-Zertifikaten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7bb3b-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7bb3b-119">Verweis</span><span class="sxs-lookup"><span data-stu-id="7bb3b-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="7bb3b-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="7bb3b-120">Related Sections</span></span>  
 [<span data-ttu-id="7bb3b-121">Schlüsselbegriffe der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7bb3b-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="7bb3b-122">Erweitern der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7bb3b-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="7bb3b-123">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="7bb3b-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="7bb3b-124">Bindungen und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7bb3b-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="7bb3b-125">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="7bb3b-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="7bb3b-126">Erweitern der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7bb3b-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="7bb3b-127">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="7bb3b-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="7bb3b-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bb3b-128">See Also</span></span>  
 [<span data-ttu-id="7bb3b-129">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="7bb3b-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="7bb3b-130">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="7bb3b-130">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
