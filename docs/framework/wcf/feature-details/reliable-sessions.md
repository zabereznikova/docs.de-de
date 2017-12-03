---
title: "Zuverlässige Sitzungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 53bb63fbbcf92650085514118a5e9464ab2dea30
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-sessions"></a><span data-ttu-id="26621-102">Zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="26621-102">Reliable Sessions</span></span>

<span data-ttu-id="26621-103">In diesem Abschnitt wird beschrieben, was eine [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zuverlässige Sitzung ist, wie Verwendungsweise ist und wenn ein verwenden möchten, welche Bindungskonfiguration hierfür erforderlich, und Verweise auf Practices Best.</span><span class="sxs-lookup"><span data-stu-id="26621-103">This section describes what a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="26621-104">In der folgenden Tabelle werden Details über die wesentlichen Punkte und verwandte Themen in diesem Abschnitt zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="26621-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="26621-105">Die zuverlässige Sitzung [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet Featrues sicherstellen, dass zwischen Endpunkten gesendete Nachrichten über SOAP oder transportvermittler übertragen übertragen werden und werden nur einmal und optional in der gleichen Reihenfolge, in der sie gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="26621-105">The reliable session [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides featrues ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="26621-106">Um eine zuverlässige Sitzung mit einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendung zu verwenden, nutzen Sie entweder eine der vom System bereitgestellten Bindungen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], die eine zuverlässige Sitzung standardmäßig oder als Option unterstützen, oder erstellen Sie eine eigene benutzerdefinierte Bindung, die diese Sitzung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="26621-106">To use a reliable session with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, either use one of the system-provided bindings in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="26621-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="26621-107">In This Section</span></span>

<span data-ttu-id="26621-108">[Übersicht über zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="26621-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span></span>  
<span data-ttu-id="26621-109">Beschreibt zuverlässige Sitzungen, wann diese verwendet werden sollten, die verschiedenen Bindungen, die zuverlässige Sitzungen unterstützen, und deren Funktionsweise.</span><span class="sxs-lookup"><span data-stu-id="26621-109">Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="26621-110">[Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span><span class="sxs-lookup"><span data-stu-id="26621-110">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span></span>  
<span data-ttu-id="26621-111">Beschreibt, wie eine zuverlässige Sitzung über HTTP mit einer benutzerdefinierten in der Konfiguration angegebenen Bindung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="26621-111">Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="26621-112">[Vorgehensweise: Sichern von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="26621-112">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span></span>  
<span data-ttu-id="26621-113">Beschreibt, wie eine zuverlässige Sitzung geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="26621-113">Describes how to secure a reliable session.</span></span>

<span data-ttu-id="26621-114">[Vorgehensweise: erstellen eine benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span><span class="sxs-lookup"><span data-stu-id="26621-114">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span></span>  
<span data-ttu-id="26621-115">Beschreibt, wie eine zuverlässige Sitzung über HTTPS erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="26621-115">Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="26621-116">[Bewährte Vorgehensweisen für zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="26621-116">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span></span>  
<span data-ttu-id="26621-117">Beschreibt einige der Best Practices in Verbindung mit der Verwendung einer zuverlässigen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="26621-117">Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="26621-118">Verweis</span><span class="sxs-lookup"><span data-stu-id="26621-118">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="26621-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26621-119">See Also</span></span>

<span data-ttu-id="26621-120">[Warteschlangen und zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="26621-120">[Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md) </span></span>  
[<span data-ttu-id="26621-121">Sitzungen, Instanziierung und Parallelität</span><span class="sxs-lookup"><span data-stu-id="26621-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
