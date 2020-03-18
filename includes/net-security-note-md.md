---
ms.openlocfilehash: f70452cbadc8927521f0fcfda693586c277e4d0f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "70041161"
---
> [!CAUTION]
> <span data-ttu-id="68f86-101">Codezugriffssicherheit und teilweise vertrauenswürdiger Code</span><span class="sxs-lookup"><span data-stu-id="68f86-101">Code Access Security and Partially Trusted Code</span></span>
>
> <span data-ttu-id="68f86-102">.NET Framework bietet einen Mechanismus namens Codezugriffssicherheit (Code Access Security, CAS) zur Erzwingung verschiedener Vertrauensebenen für anderen Code, der in der gleichen Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="68f86-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>  <span data-ttu-id="68f86-103">Die Codezugriffssicherheit sollte in .NET Framework nicht als Mechanismus zum Erzwingen von Sicherheitsbegrenzungen verwendet werden, die auf dem Codeursprung oder anderen Identitätsaspekten beruhen.</span><span class="sxs-lookup"><span data-stu-id="68f86-103">Code Access Security in .NET Framework should not  be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="68f86-104">Wir aktualisieren unsere Leitfäden, um darauf hinzuweisen, dass die Codezugriffssicherheit und sicherheitstransparenter Code als Sicherheitsbegrenzung bei teilweise vertrauenswürdigem Code nicht unterstützt werden, insbesondere bei Code mit unbekannter Herkunft.</span><span class="sxs-lookup"><span data-stu-id="68f86-104">We are updating our guidance to reflect that Code Access Security and Security-Transparent Code will not be supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="68f86-105">Wir raten davon ab, Code unbekannter Herkunft zu laden und auszuführen, ohne alternative Sicherheitsmaßnahmen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="68f86-105">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span>
>
> <span data-ttu-id="68f86-106">Diese Richtlinie gilt für alle Versionen von .NET Framework, außer für die in Silverlight enthaltene .NET Framework-Version.</span><span class="sxs-lookup"><span data-stu-id="68f86-106">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>
