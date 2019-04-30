---
ms.openlocfilehash: f01d0a24202ecda7e23cbe925bb6dc8962cb7574
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750724"
---
> [!CAUTION]
>  Codezugriffssicherheit und teilweise vertrauenswürdiger Code  
>   
>  .NET Framework bietet einen Mechanismus namens Codezugriffssicherheit (Code Access Security, CAS) zur Erzwingung verschiedener Vertrauensebenen für anderen Code, der in der gleichen Anwendung ausgeführt wird.  Die Codezugriffssicherheit sollte in .NET Framework nicht als Mechanismus zum Erzwingen von Sicherheitsbegrenzungen verwendet werden, die auf dem Codeursprung oder anderen Identitätsaspekten beruhen. Wir aktualisieren unsere Leitfäden, um darauf hinzuweisen, dass die Codezugriffssicherheit und sicherheitstransparenter Code als Sicherheitsbegrenzung bei teilweise vertrauenswürdigem Code nicht unterstützt werden, insbesondere bei Code mit unbekannter Herkunft. Wir raten davon ab, Code unbekannter Herkunft zu laden und auszuführen, ohne alternative Sicherheitsmaßnahmen zu treffen.  
>   
>  Diese Richtlinie gilt für alle Versionen von .NET Framework, außer für die in Silverlight enthaltene .NET Framework-Version.