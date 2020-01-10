---
title: Sichern von Statusdaten
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
ms.openlocfilehash: c30bd2fe9e1ed371be2db60739d3b329fea788c7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705898"
---
# <a name="securing-state-data"></a>Sichern von Statusdaten
Anwendungen, die vertrauliche Daten verarbeiten oder irgendwelche Sicherheitsentscheidungen treffen, müssen diese Daten unter eigener Kontrolle behalten und sie vor dem direkten Zugriff durch möglicherweise böswilligen Code schützen. Die beste Möglichkeit, Daten im Speicher zu schützen, besteht darin, diese als private oder interne (Gültigkeitsbereich ist auf dieselbe Assembly beschränkt) Variablen zu deklarieren. Allerdings wird auch auf diese Daten zugegriffen, also sollten Sie Folgendes berücksichtigen:  
  
- Über Reflektionsmechanismen kann sehr vertrauenswürdiger Code, der auf das Objekt verweisen kann, private Member abrufen und festlegen.  
  
- Über Serialisierung kann sehr vertrauenswürdiger Code private Member abrufen und festlegen, wenn er auf die entsprechenden Daten in der serialisierten Form des Objekts zugreifen kann.  
  
- Beim Debuggen können diese Daten gelesen werden.  
  
 Stellen Sie sicher, dass diese Werte in keiner Ihrer Methoden oder Eigenschaften versehentlich verfügbar gemacht werden.  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
