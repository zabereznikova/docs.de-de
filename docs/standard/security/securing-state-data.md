---
title: Sichern von Statusdaten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d5f8c4d17e17f7bcdf58db7052dbb2cf2b737a9c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="securing-state-data"></a><span data-ttu-id="d7e58-102">Sichern von Statusdaten</span><span class="sxs-lookup"><span data-stu-id="d7e58-102">Securing State Data</span></span>
<span data-ttu-id="d7e58-103">Anwendungen, die vertrauliche Daten verarbeiten oder irgendwelche Sicherheitsentscheidungen treffen, müssen diese Daten unter eigener Kontrolle behalten und sie vor dem direkten Zugriff durch möglicherweise böswilligen Code schützen.</span><span class="sxs-lookup"><span data-stu-id="d7e58-103">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="d7e58-104">Die beste Möglichkeit, Daten im Speicher zu schützen, besteht darin, diese als private oder interne (Gültigkeitsbereich ist auf dieselbe Assembly beschränkt) Variablen zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d7e58-104">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="d7e58-105">Allerdings wird auch auf diese Daten zugegriffen, also sollten Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="d7e58-105">However, even this data is subject to access you should be aware of:</span></span>  
  
-   <span data-ttu-id="d7e58-106">Über Reflektionsmechanismen kann sehr vertrauenswürdiger Code, der auf das Objekt verweisen kann, private Member abrufen und festlegen.</span><span class="sxs-lookup"><span data-stu-id="d7e58-106">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
-   <span data-ttu-id="d7e58-107">Über Serialisierung kann sehr vertrauenswürdiger Code private Member abrufen und festlegen, wenn er auf die entsprechenden Daten in der serialisierten Form des Objekts zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="d7e58-107">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
-   <span data-ttu-id="d7e58-108">Beim Debuggen können diese Daten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="d7e58-108">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="d7e58-109">Stellen Sie sicher, dass diese Werte in keiner Ihrer Methoden oder Eigenschaften versehentlich verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d7e58-109">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e58-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7e58-110">See Also</span></span>  
 [<span data-ttu-id="d7e58-111">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="d7e58-111">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
