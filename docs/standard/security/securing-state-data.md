---
title: Sichern von Statusdaten
description: Deklarieren Sie Zustandsdaten als private oder interne Variablen, um den Zugriff darauf einzuschränken. Auf solche Daten kann weiterhin durch Reflektion, Serialisierung und Debuggen zugegriffen werden.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
ms.openlocfilehash: f95bf409f7eef8c2636d3c180d2bbd95fbc689c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186826"
---
# <a name="securing-state-data"></a><span data-ttu-id="f3295-104">Sichern von Statusdaten</span><span class="sxs-lookup"><span data-stu-id="f3295-104">Securing State Data</span></span>
<span data-ttu-id="f3295-105">Anwendungen, die vertrauliche Daten verarbeiten oder irgendwelche Sicherheitsentscheidungen treffen, müssen diese Daten unter eigener Kontrolle behalten und sie vor dem direkten Zugriff durch möglicherweise böswilligen Code schützen.</span><span class="sxs-lookup"><span data-stu-id="f3295-105">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="f3295-106">Die beste Möglichkeit, Daten im Speicher zu schützen, besteht darin, diese als private oder interne (Gültigkeitsbereich ist auf dieselbe Assembly beschränkt) Variablen zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="f3295-106">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="f3295-107">Allerdings wird auch auf diese Daten zugegriffen, also sollten Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="f3295-107">However, even this data is subject to access you should be aware of:</span></span>  
  
- <span data-ttu-id="f3295-108">Über Reflektionsmechanismen kann sehr vertrauenswürdiger Code, der auf das Objekt verweisen kann, private Member abrufen und festlegen.</span><span class="sxs-lookup"><span data-stu-id="f3295-108">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
- <span data-ttu-id="f3295-109">Über Serialisierung kann sehr vertrauenswürdiger Code private Member abrufen und festlegen, wenn er auf die entsprechenden Daten in der serialisierten Form des Objekts zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="f3295-109">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
- <span data-ttu-id="f3295-110">Beim Debuggen können diese Daten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="f3295-110">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="f3295-111">Stellen Sie sicher, dass diese Werte in keiner Ihrer Methoden oder Eigenschaften versehentlich verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f3295-111">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3295-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3295-112">See also</span></span>

- [<span data-ttu-id="f3295-113">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="f3295-113">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
