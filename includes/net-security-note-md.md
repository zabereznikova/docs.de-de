---
ms.openlocfilehash: 3164233f1ac056de385faa119143d75d3c2dc50c
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224358"
---
> [!CAUTION]
> Code Zugriffssicherheit (Code Access Security, CAS) und teilweise vertrauenswürdiger Code
>
> .NET Framework bietet einen Mechanismus namens Codezugriffssicherheit (Code Access Security, CAS) zur Erzwingung verschiedener Vertrauensebenen für anderen Code, der in der gleichen Anwendung ausgeführt wird.
>
> **CAS wird in .net Core, .net 5 oder höheren Versionen nicht unterstützt. CAS werden von Versionen von c# höher als 7,0 nicht unterstützt.**
>
> CAS in .NET Framework sollten nicht als Mechanismus zum Erzwingen von Sicherheitsgrenzen auf der Grundlage von Code Ursprungs oder anderen Identitäts Aspekten verwendet werden. CAS und Security-Transparent Code werden nicht als Sicherheits Begrenzung mit teilweise vertrauenswürdigem Code unterstützt, insbesondere bei Code mit unbekannter Herkunft. Wir raten davon ab, Code unbekannter Herkunft zu laden und auszuführen, ohne alternative Sicherheitsmaßnahmen zu treffen. .NET Framework gibt keine Sicherheitspatches für Exploits mit Rechte Erweiterungen aus, die möglicherweise für den CAS-Sandkasten erkannt werden.
>
> Diese Richtlinie gilt für alle Versionen von .NET Framework, außer für die in Silverlight enthaltene .NET Framework-Version.
