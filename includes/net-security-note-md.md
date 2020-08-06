---
ms.openlocfilehash: 8b0edd9a49ca431355ab4f57fa041c5d1756d7eb
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855664"
---
> [!CAUTION]
> Code Zugriffssicherheit (Code Access Security, CAS) und teilweise vertrauenswürdiger Code
>
> .NET Framework bietet einen Mechanismus namens Codezugriffssicherheit (Code Access Security, CAS) zur Erzwingung verschiedener Vertrauensebenen für anderen Code, der in der gleichen Anwendung ausgeführt wird.
>
> **CAS wird in .net Core, .net 5 oder höheren Versionen nicht unterstützt. CAS werden von Versionen von c# höher als 7,0 nicht unterstützt.**
>
> CAS in .NET Framework sollten nicht als Mechanismus zum Erzwingen von Sicherheitsgrenzen auf der Grundlage von Code Ursprungs oder anderen Identitäts Aspekten verwendet werden. CAS und Sicherheits transparenter Code werden nicht als Sicherheitsgrenze mit teilweise vertrauenswürdigem Code unterstützt, insbesondere bei Code mit unbekannter Herkunft. Wir raten davon ab, Code unbekannter Herkunft zu laden und auszuführen, ohne alternative Sicherheitsmaßnahmen zu treffen.
>
> Diese Richtlinie gilt für alle Versionen von .NET Framework, außer für die in Silverlight enthaltene .NET Framework-Version.
