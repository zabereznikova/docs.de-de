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
# <a name="securing-state-data"></a>Sichern von Statusdaten
Anwendungen, die vertrauliche Daten verarbeiten oder irgendwelche Sicherheitsentscheidungen treffen, müssen diese Daten unter eigener Kontrolle behalten und sie vor dem direkten Zugriff durch möglicherweise böswilligen Code schützen. Die beste Möglichkeit, Daten im Speicher zu schützen, besteht darin, diese als private oder interne (Gültigkeitsbereich ist auf dieselbe Assembly beschränkt) Variablen zu deklarieren. Allerdings wird auch auf diese Daten zugegriffen, also sollten Sie Folgendes berücksichtigen:  
  
-   Über Reflektionsmechanismen kann sehr vertrauenswürdiger Code, der auf das Objekt verweisen kann, private Member abrufen und festlegen.  
  
-   Über Serialisierung kann sehr vertrauenswürdiger Code private Member abrufen und festlegen, wenn er auf die entsprechenden Daten in der serialisierten Form des Objekts zugreifen kann.  
  
-   Beim Debuggen können diese Daten gelesen werden.  
  
 Stellen Sie sicher, dass diese Werte in keiner Ihrer Methoden oder Eigenschaften versehentlich verfügbar gemacht werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
