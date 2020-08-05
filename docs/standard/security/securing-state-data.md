---
title: Sichern von Statusdaten
description: Deklarieren Sie Zustandsdaten als private oder interne Variablen, um den Zugriff darauf einzuschränken. Auf solche Daten kann weiterhin über Reflektion, Serialisierung und Debuggen zugegriffen werden.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
ms.openlocfilehash: 73bd0ace28e5b9661cc86d6749ceef9aa4c9ac92
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557124"
---
# <a name="securing-state-data"></a><span data-ttu-id="46a2b-104">Sichern von Statusdaten</span><span class="sxs-lookup"><span data-stu-id="46a2b-104">Securing State Data</span></span>

<span data-ttu-id="46a2b-105">Anwendungen, die vertrauliche Daten verarbeiten oder irgendwelche Sicherheitsentscheidungen treffen, müssen diese Daten unter eigener Kontrolle behalten und sie vor dem direkten Zugriff durch möglicherweise böswilligen Code schützen.</span><span class="sxs-lookup"><span data-stu-id="46a2b-105">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="46a2b-106">Die beste Möglichkeit, Daten im Speicher zu schützen, besteht darin, diese als private oder interne (Gültigkeitsbereich ist auf dieselbe Assembly beschränkt) Variablen zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="46a2b-106">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="46a2b-107">Allerdings wird auch auf diese Daten zugegriffen, also sollten Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="46a2b-107">However, even this data is subject to access you should be aware of:</span></span>  
  
- <span data-ttu-id="46a2b-108">Über Reflektionsmechanismen kann sehr vertrauenswürdiger Code, der auf das Objekt verweisen kann, private Member abrufen und festlegen.</span><span class="sxs-lookup"><span data-stu-id="46a2b-108">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
- <span data-ttu-id="46a2b-109">Über Serialisierung kann sehr vertrauenswürdiger Code private Member abrufen und festlegen, wenn er auf die entsprechenden Daten in der serialisierten Form des Objekts zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="46a2b-109">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
- <span data-ttu-id="46a2b-110">Beim Debuggen können diese Daten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="46a2b-110">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="46a2b-111">Stellen Sie sicher, dass diese Werte in keiner Ihrer Methoden oder Eigenschaften versehentlich verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="46a2b-111">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46a2b-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46a2b-112">See also</span></span>

- [<span data-ttu-id="46a2b-113">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="46a2b-113">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)
- [<span data-ttu-id="46a2b-114">ASP.net Core Sicherheit</span><span class="sxs-lookup"><span data-stu-id="46a2b-114">ASP.NET Core Security</span></span>](/aspnet/core/security/)
