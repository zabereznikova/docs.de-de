---
ms.openlocfilehash: 8b0edd9a49ca431355ab4f57fa041c5d1756d7eb
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855664"
---
> [!CAUTION]
> <span data-ttu-id="b30bb-101">Code Zugriffssicherheit (Code Access Security, CAS) und teilweise vertrauenswürdiger Code</span><span class="sxs-lookup"><span data-stu-id="b30bb-101">Code Access Security (CAS) and Partially Trusted Code</span></span>
>
> <span data-ttu-id="b30bb-102">.NET Framework bietet einen Mechanismus namens Codezugriffssicherheit (Code Access Security, CAS) zur Erzwingung verschiedener Vertrauensebenen für anderen Code, der in der gleichen Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b30bb-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>
>
> <span data-ttu-id="b30bb-103">**CAS wird in .net Core, .net 5 oder höheren Versionen nicht unterstützt. CAS werden von Versionen von c# höher als 7,0 nicht unterstützt.**</span><span class="sxs-lookup"><span data-stu-id="b30bb-103">**CAS is not supported in .NET Core, .NET 5, or later versions. CAS is not supported by versions of C# later than 7.0.**</span></span>
>
> <span data-ttu-id="b30bb-104">CAS in .NET Framework sollten nicht als Mechanismus zum Erzwingen von Sicherheitsgrenzen auf der Grundlage von Code Ursprungs oder anderen Identitäts Aspekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b30bb-104">CAS in .NET Framework should not be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="b30bb-105">CAS und Sicherheits transparenter Code werden nicht als Sicherheitsgrenze mit teilweise vertrauenswürdigem Code unterstützt, insbesondere bei Code mit unbekannter Herkunft.</span><span class="sxs-lookup"><span data-stu-id="b30bb-105">CAS and Security-Transparent Code are not supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="b30bb-106">Wir raten davon ab, Code unbekannter Herkunft zu laden und auszuführen, ohne alternative Sicherheitsmaßnahmen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="b30bb-106">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span>
>
> <span data-ttu-id="b30bb-107">Diese Richtlinie gilt für alle Versionen von .NET Framework, außer für die in Silverlight enthaltene .NET Framework-Version.</span><span class="sxs-lookup"><span data-stu-id="b30bb-107">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>
