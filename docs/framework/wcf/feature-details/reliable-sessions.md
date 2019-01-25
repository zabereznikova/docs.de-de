---
title: Zuverlässige Sitzungen
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 1d87f6f4d94763dc8f6ac7e929c22b17940097ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735424"
---
# <a name="reliable-sessions"></a><span data-ttu-id="18850-102">Zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="18850-102">Reliable Sessions</span></span>

<span data-ttu-id="18850-103">In diesem Abschnitt wird beschrieben, welche eines Windows Communication Foundation (WCF) zuverlässige Sitzung ist, wofür sie, wie verwendet wird und wenn eine solche welche hierfür Bindungskonfiguration und Verweise auf Practices Best.</span><span class="sxs-lookup"><span data-stu-id="18850-103">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="18850-104">In der folgenden Tabelle werden Details über die wesentlichen Punkte und verwandte Themen in diesem Abschnitt zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="18850-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="18850-105">Die zuverlässige Sitzung WCF bietet integrierten Funktionen zur sicherzustellen, dass zwischen Endpunkten gesendete Nachrichten über SOAP oder transportvermittler übertragen übertragen werden und werden nur einmal und optional in der gleichen Reihenfolge, in der sie gesendet wurden, bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="18850-105">The reliable session WCF provides featrues ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="18850-106">Um eine zuverlässige Sitzung mit einer WCF-Anwendung verwenden möchten, verwenden Sie eine der vom System bereitgestellten Bindungen in WCF, die eine zuverlässige Sitzung standardmäßig oder als Option unterstützen, oder erstellen Sie eine eigene benutzerdefinierte Bindung, die die Sitzung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="18850-106">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="18850-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="18850-107">In This Section</span></span>

<span data-ttu-id="18850-108">[Übersicht über zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="18850-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span></span>  
<span data-ttu-id="18850-109">Beschreibt zuverlässige Sitzungen, wann diese verwendet werden sollten, die verschiedenen Bindungen, die zuverlässige Sitzungen unterstützen, und deren Funktionsweise.</span><span class="sxs-lookup"><span data-stu-id="18850-109">Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="18850-110">[Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span><span class="sxs-lookup"><span data-stu-id="18850-110">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span></span>  
<span data-ttu-id="18850-111">Beschreibt, wie eine zuverlässige Sitzung über HTTP mit einer benutzerdefinierten in der Konfiguration angegebenen Bindung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="18850-111">Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="18850-112">[Vorgehensweise: Sichern von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="18850-112">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span></span>  
<span data-ttu-id="18850-113">Beschreibt, wie eine zuverlässige Sitzung geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="18850-113">Describes how to secure a reliable session.</span></span>

<span data-ttu-id="18850-114">[Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span><span class="sxs-lookup"><span data-stu-id="18850-114">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span></span>  
<span data-ttu-id="18850-115">Beschreibt, wie eine zuverlässige Sitzung über HTTPS erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="18850-115">Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="18850-116">[Bewährte Methoden für zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="18850-116">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span></span>  
<span data-ttu-id="18850-117">Beschreibt einige der Best Practices in Verbindung mit der Verwendung einer zuverlässigen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="18850-117">Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="18850-118">Referenz</span><span class="sxs-lookup"><span data-stu-id="18850-118">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="18850-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18850-119">See also</span></span>

- [<span data-ttu-id="18850-120">Warteschlangen und zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="18850-120">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [<span data-ttu-id="18850-121">Sitzungen, Instanzerstellung und Parallelität</span><span class="sxs-lookup"><span data-stu-id="18850-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
