---
ms.openlocfilehash: 023b7d8c5aa9d435d3493935b4439ae4262c85bb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65670845"
---
> [!CAUTION]
>  <span data-ttu-id="34ffd-101">Codezugriffssicherheit und teilweise vertrauenswürdiger Code</span><span class="sxs-lookup"><span data-stu-id="34ffd-101">Code Access Security and Partially Trusted Code</span></span>  
>   
>  <span data-ttu-id="34ffd-102">.NET Framework bietet einen Mechanismus namens Codezugriffssicherheit (Code Access Security, CAS) zur Erzwingung verschiedener Vertrauensebenen für anderen Code, der in der gleichen Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="34ffd-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>  <span data-ttu-id="34ffd-103">Die Codezugriffssicherheit sollte in .NET Framework nicht als Mechanismus zum Erzwingen von Sicherheitsbegrenzungen verwendet werden, die auf dem Codeursprung oder anderen Identitätsaspekten beruhen.</span><span class="sxs-lookup"><span data-stu-id="34ffd-103">Code Access Security in .NET Framework should not  be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="34ffd-104">Wir aktualisieren unsere Leitfäden, um darauf hinzuweisen, dass die Codezugriffssicherheit und sicherheitstransparenter Code als Sicherheitsbegrenzung bei teilweise vertrauenswürdigem Code nicht unterstützt werden, insbesondere bei Code mit unbekannter Herkunft.</span><span class="sxs-lookup"><span data-stu-id="34ffd-104">We are updating our guidance to reflect that Code Access Security and Security-Transparent Code will not be supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="34ffd-105">Wir raten davon ab, Code unbekannter Herkunft zu laden und auszuführen, ohne alternative Sicherheitsmaßnahmen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="34ffd-105">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span>  
>   
>  <span data-ttu-id="34ffd-106">Diese Richtlinie gilt für alle Versionen von .NET Framework, außer für die in Silverlight enthaltene .NET Framework-Version.</span><span class="sxs-lookup"><span data-stu-id="34ffd-106">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>
