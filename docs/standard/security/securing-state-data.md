---
title: Sichern von Statusdaten
description: Deklarieren Sie Zustandsdaten als private oder interne Variablen, um den Zugriff darauf einzuschränken. Auf solche Daten kann weiterhin über Reflektion, Serialisierung und Debuggen zugegriffen werden.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
ms.openlocfilehash: b7fcb520fe6fa28cc098c4e1cbb56ce7da759c11
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291044"
---
# <a name="securing-state-data"></a><span data-ttu-id="96ba5-104">Sichern von Statusdaten</span><span class="sxs-lookup"><span data-stu-id="96ba5-104">Securing State Data</span></span>
<span data-ttu-id="96ba5-105">Anwendungen, die vertrauliche Daten verarbeiten oder irgendwelche Sicherheitsentscheidungen treffen, müssen diese Daten unter eigener Kontrolle behalten und sie vor dem direkten Zugriff durch möglicherweise böswilligen Code schützen.</span><span class="sxs-lookup"><span data-stu-id="96ba5-105">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="96ba5-106">Die beste Möglichkeit, Daten im Speicher zu schützen, besteht darin, diese als private oder interne (Gültigkeitsbereich ist auf dieselbe Assembly beschränkt) Variablen zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="96ba5-106">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="96ba5-107">Allerdings wird auch auf diese Daten zugegriffen, also sollten Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="96ba5-107">However, even this data is subject to access you should be aware of:</span></span>  
  
- <span data-ttu-id="96ba5-108">Über Reflektionsmechanismen kann sehr vertrauenswürdiger Code, der auf das Objekt verweisen kann, private Member abrufen und festlegen.</span><span class="sxs-lookup"><span data-stu-id="96ba5-108">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
- <span data-ttu-id="96ba5-109">Über Serialisierung kann sehr vertrauenswürdiger Code private Member abrufen und festlegen, wenn er auf die entsprechenden Daten in der serialisierten Form des Objekts zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="96ba5-109">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
- <span data-ttu-id="96ba5-110">Beim Debuggen können diese Daten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="96ba5-110">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="96ba5-111">Stellen Sie sicher, dass diese Werte in keiner Ihrer Methoden oder Eigenschaften versehentlich verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="96ba5-111">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96ba5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96ba5-112">See also</span></span>

- [<span data-ttu-id="96ba5-113">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="96ba5-113">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)
