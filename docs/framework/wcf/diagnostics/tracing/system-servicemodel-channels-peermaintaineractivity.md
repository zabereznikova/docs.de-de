---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.date: 03/30/2017
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
ms.openlocfilehash: ce97eaa2ad5c9dbd5f4d6f81186960c489eb4b85
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596076"
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a><span data-ttu-id="75ffb-102">System.ServiceModel.Channels.PeerMaintainerActivity</span><span class="sxs-lookup"><span data-stu-id="75ffb-102">System.ServiceModel.Channels.PeerMaintainerActivity</span></span>
<span data-ttu-id="75ffb-103">Das PeerMaintainer-Modul führt einen bestimmten Vorgang (Details innerhalb des Ablaufverfolgungsnachrichtentexts) aus.</span><span class="sxs-lookup"><span data-stu-id="75ffb-103">The PeerMaintainer module is performing a specific operation (details contained within the trace message body).</span></span>  
  
## <a name="description"></a><span data-ttu-id="75ffb-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="75ffb-104">Description</span></span>  
 <span data-ttu-id="75ffb-105">Diese Ablaufverfolgung tritt während verschiedener PeerMaintainer-Vorgänge auf.</span><span class="sxs-lookup"><span data-stu-id="75ffb-105">This trace occurs during various PeerMaintainer operations.</span></span>  
  
 <span data-ttu-id="75ffb-106">PeerMaintainer ist eine interne Komponente von PeerNode.</span><span class="sxs-lookup"><span data-stu-id="75ffb-106">PeerMaintainer is an internal component of PeerNode.</span></span> <span data-ttu-id="75ffb-107">Jede Minute &#8211; oder nach 32&#160;empfangenen Nachrichten &#8211; wird eine LinkUtility-Nachricht an die Nachbarn gesendet. Diese Nachricht enthält eine Statistik mit der Anzahl der ausgetauschten Nachrichten sowie mit Informationen dazu, wie viele der Nachrichten nützlich waren (also keine Duplikate und nicht manipuliert).</span><span class="sxs-lookup"><span data-stu-id="75ffb-107">Every minute, or every 32 messages received, it sends a LinkUtility message to its neighbors with statistics about how many messages are exchanged and how many are useful (non-duplicates, untampered).</span></span> <span data-ttu-id="75ffb-108">Dadurch lässt sich das Verknüpfungsprogramm eines bestimmten Nachbarn ermitteln.</span><span class="sxs-lookup"><span data-stu-id="75ffb-108">This helps determine a particular neighbor's Link Utility.</span></span> <span data-ttu-id="75ffb-109">Etwa alle fünf Minuten überprüft der Maintainer die Integrität der Nachbarverbindungen.</span><span class="sxs-lookup"><span data-stu-id="75ffb-109">Approximately every five minutes, the maintainer checks the health of neighbor connections.</span></span> <span data-ttu-id="75ffb-110">Übersteigt die Anzahl von Nachbarverbindungen die Idealmenge, werden die am wenigsten nützlichen Verbindungen entfernt.</span><span class="sxs-lookup"><span data-stu-id="75ffb-110">If the number of neighbor connections exceeds the ideal amount, the maintainer prunes off the least useful connections.</span></span> <span data-ttu-id="75ffb-111">Sind nicht genügend Verbindungen verfügbar, werden vom Maintainer neue Verbindungen eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="75ffb-111">If there are not enough connections, the maintainer acquires new connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ffb-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75ffb-112">See also</span></span>

- [<span data-ttu-id="75ffb-113">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="75ffb-113">Tracing</span></span>](index.md)
- [<span data-ttu-id="75ffb-114">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="75ffb-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="75ffb-115">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="75ffb-115">Administration and Diagnostics</span></span>](../index.md)
