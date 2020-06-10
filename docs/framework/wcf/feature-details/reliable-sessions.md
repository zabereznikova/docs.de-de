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
ms.openlocfilehash: 910ad952192243c6aa8a79417ad711d8c2a4ba2e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590539"
---
# <a name="reliable-sessions"></a><span data-ttu-id="65eeb-102">Zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="65eeb-102">Reliable Sessions</span></span>

<span data-ttu-id="65eeb-103">In diesem Abschnitt wird beschrieben, was eine zuverlässige Windows Communication Foundation (WCF)-Sitzung ist, wofür Sie verwendet wird, wie und wann Sie verwendet wird, welche Bindungs Konfigurationen Sie unterstützen, und wie Sie auf bewährte Methoden hinweisen.</span><span class="sxs-lookup"><span data-stu-id="65eeb-103">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="65eeb-104">In der folgenden Tabelle werden Details über die wesentlichen Punkte und verwandte Themen in diesem Abschnitt zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="65eeb-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="65eeb-105">Die zuverlässige Sitzung WCF stellt Features bereit, die sicherstellen, dass zwischen Endpunkten gesendete Nachrichten über SOAP-oder Transportvermittler übertragen werden und nur einmal und optional in derselben Reihenfolge übermittelt werden, in der Sie gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="65eeb-105">The reliable session WCF provides features ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="65eeb-106">Um eine zuverlässige Sitzung mit einer WCF-Anwendung zu verwenden, verwenden Sie entweder eine der vom System bereitgestellten Bindungen in WCF, die eine zuverlässige Sitzung standardmäßig oder als Option unterstützen, oder erstellen Sie eine eigene benutzerdefinierte Bindung, die die Sitzung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="65eeb-106">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="65eeb-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="65eeb-107">In This Section</span></span>

<span data-ttu-id="65eeb-108">[Übersicht über zuverlässige Sitzungen](reliable-sessions-overview.md) Beschreibt zuverlässige Sitzungen, wann Sie verwendet werden sollen, die verschiedenen Bindungen, die zuverlässige Sitzungen unterstützen, und wie Sie funktionieren.</span><span class="sxs-lookup"><span data-stu-id="65eeb-108">[Reliable Sessions Overview](reliable-sessions-overview.md) Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="65eeb-109">Vorgehens [Weise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](how-to-exchange-messages-within-a-reliable-session.md) Beschreibt, wie eine zuverlässige Sitzung über HTTP mithilfe einer benutzerdefinierten Bindung erstellt wird, die in der Konfiguration angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="65eeb-109">[How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md) Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="65eeb-110">Vorgehens [Weise: Sichern von Nachrichten innerhalb zuverlässiger Sitzungen](how-to-secure-messages-within-reliable-sessions.md) Hier wird beschrieben, wie eine zuverlässige Sitzung geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="65eeb-110">[How to: Secure Messages within Reliable Sessions](how-to-secure-messages-within-reliable-sessions.md) Describes how to secure a reliable session.</span></span>

<span data-ttu-id="65eeb-111">Gewusst [wie: Erstellen einer benutzerdefinierten zuverlässigen Sitzungs Bindung mit HTTPS](how-to-create-a-custom-reliable-session-binding-with-https.md) Hier wird beschrieben, wie eine zuverlässige Sitzung über HTTPS erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="65eeb-111">[How to: Create a Custom Reliable Session Binding with HTTPS](how-to-create-a-custom-reliable-session-binding-with-https.md) Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="65eeb-112">[Bewährte Methoden für zuverlässige Sitzungen](best-practices-for-reliable-sessions.md) Beschreibt einige bewährte Methoden für die Verwendung einer zuverlässigen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="65eeb-112">[Best Practices for Reliable Sessions](best-practices-for-reliable-sessions.md) Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="65eeb-113">Referenz</span><span class="sxs-lookup"><span data-stu-id="65eeb-113">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="65eeb-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65eeb-114">See also</span></span>

- [<span data-ttu-id="65eeb-115">Warteschlangen und zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="65eeb-115">Queues and Reliable Sessions</span></span>](queues-and-reliable-sessions.md)
- [<span data-ttu-id="65eeb-116">Sitzungen, Instanziierung und Parallelität</span><span class="sxs-lookup"><span data-stu-id="65eeb-116">Sessions, Instancing, and Concurrency</span></span>](sessions-instancing-and-concurrency.md)
