---
title: Sichern von Statusdaten
description: Deklarieren Sie Zustandsdaten als private oder interne Variablen, um den Zugriff darauf einzuschränken. Auf solche Daten kann weiterhin über Reflektion, Serialisierung und Debuggen zugegriffen werden.
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
ms.openlocfilehash: 849ed993befaceda1b04becbb7fb2530c5c62a77
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824160"
---
# <a name="securing-state-data"></a>Sichern von Statusdaten

Anwendungen, die vertrauliche Daten verarbeiten oder irgendwelche Sicherheitsentscheidungen treffen, müssen diese Daten unter eigener Kontrolle behalten und sie vor dem direkten Zugriff durch möglicherweise böswilligen Code schützen. Die beste Möglichkeit, Daten im Speicher zu schützen, besteht darin, diese als private oder interne (Gültigkeitsbereich ist auf dieselbe Assembly beschränkt) Variablen zu deklarieren. Allerdings wird auch auf diese Daten zugegriffen, also sollten Sie Folgendes berücksichtigen:  
  
- Über Reflektionsmechanismen kann sehr vertrauenswürdiger Code, der auf das Objekt verweisen kann, private Member abrufen und festlegen.  
  
- Über Serialisierung kann sehr vertrauenswürdiger Code private Member abrufen und festlegen, wenn er auf die entsprechenden Daten in der serialisierten Form des Objekts zugreifen kann.  
  
- Beim Debuggen können diese Daten gelesen werden.  
  
 Stellen Sie sicher, dass diese Werte in keiner Ihrer Methoden oder Eigenschaften versehentlich verfügbar gemacht werden.  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für das Schreiben von sicherem Code](secure-coding-guidelines.md)
- [ASP.net Core Sicherheit](/aspnet/core/security/)
