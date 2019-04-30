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
ms.openlocfilehash: 9a2cd06c4c5a73d9fb5c4c7f09632e10c3eb0d87
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991158"
---
# <a name="reliable-sessions"></a><span data-ttu-id="b0c7a-102">Zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="b0c7a-102">Reliable Sessions</span></span>

<span data-ttu-id="b0c7a-103">In diesem Abschnitt wird beschrieben, welche eines Windows Communication Foundation (WCF) zuverlässige Sitzung ist, wofür sie, wie verwendet wird und wenn eine solche welche hierfür Bindungskonfiguration und Verweise auf Practices Best.</span><span class="sxs-lookup"><span data-stu-id="b0c7a-103">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="b0c7a-104">In der folgenden Tabelle werden Details über die wesentlichen Punkte und verwandte Themen in diesem Abschnitt zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="b0c7a-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="b0c7a-105">Die zuverlässige Sitzung WCF bietet Funktionen, die sicherstellen, dass zwischen Endpunkten gesendete Nachrichten über SOAP oder transportvermittler übertragen übertragen werden und werden nur einmal und optional in der gleichen Reihenfolge, in der sie gesendet wurden, bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b0c7a-105">The reliable session WCF provides features ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="b0c7a-106">Um eine zuverlässige Sitzung mit einer WCF-Anwendung verwenden möchten, verwenden Sie eine der vom System bereitgestellten Bindungen in WCF, die eine zuverlässige Sitzung standardmäßig oder als Option unterstützen, oder erstellen Sie eine eigene benutzerdefinierte Bindung, die die Sitzung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b0c7a-106">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b0c7a-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b0c7a-107">In This Section</span></span>

<span data-ttu-id="b0c7a-108">[Übersicht über zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) beschreibt zuverlässige Sitzungen, wann sie zu, die verschiedenen Bindungen verwenden, die zuverlässige Sitzungen unterstützen und zu deren Funktionsweise.</span><span class="sxs-lookup"><span data-stu-id="b0c7a-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="b0c7a-109">[Vorgehensweise: Exchange-Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) enthält Informationen zum Erstellen einer zuverlässigen Sitzungs über HTTP unter Verwendung einer benutzerdefinierten Bindung, die in der Konfiguration angegeben.</span><span class="sxs-lookup"><span data-stu-id="b0c7a-109">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="b0c7a-110">[Vorgehensweise: Schützen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) wird beschrieben, wie eine zuverlässige Sitzung geschützt.</span><span class="sxs-lookup"><span data-stu-id="b0c7a-110">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) Describes how to secure a reliable session.</span></span>

<span data-ttu-id="b0c7a-111">[Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzung Bindungen mit HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) wird beschrieben, wie eine zuverlässige Sitzung über HTTPS zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0c7a-111">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="b0c7a-112">[Bewährte Methoden für zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) beschreibt einige bewährte Methoden für die Verwendung einer zuverlässigen Sitzungs.</span><span class="sxs-lookup"><span data-stu-id="b0c7a-112">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="b0c7a-113">Referenz</span><span class="sxs-lookup"><span data-stu-id="b0c7a-113">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="b0c7a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0c7a-114">See also</span></span>

- [<span data-ttu-id="b0c7a-115">Warteschlangen und zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="b0c7a-115">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [<span data-ttu-id="b0c7a-116">Sitzungen, Instanzerstellung und Parallelität</span><span class="sxs-lookup"><span data-stu-id="b0c7a-116">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
