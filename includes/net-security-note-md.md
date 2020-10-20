---
ms.openlocfilehash: 3164233f1ac056de385faa119143d75d3c2dc50c
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224358"
---
> [!CAUTION]
> <span data-ttu-id="c295b-101">Code Zugriffssicherheit (Code Access Security, CAS) und teilweise vertrauenswürdiger Code</span><span class="sxs-lookup"><span data-stu-id="c295b-101">Code Access Security (CAS) and Partially Trusted Code</span></span>
>
> <span data-ttu-id="c295b-102">.NET Framework bietet einen Mechanismus namens Codezugriffssicherheit (Code Access Security, CAS) zur Erzwingung verschiedener Vertrauensebenen für anderen Code, der in der gleichen Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c295b-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>
>
> <span data-ttu-id="c295b-103">**CAS wird in .net Core, .net 5 oder höheren Versionen nicht unterstützt. CAS werden von Versionen von c# höher als 7,0 nicht unterstützt.**</span><span class="sxs-lookup"><span data-stu-id="c295b-103">**CAS is not supported in .NET Core, .NET 5, or later versions. CAS is not supported by versions of C# later than 7.0.**</span></span>
>
> <span data-ttu-id="c295b-104">CAS in .NET Framework sollten nicht als Mechanismus zum Erzwingen von Sicherheitsgrenzen auf der Grundlage von Code Ursprungs oder anderen Identitäts Aspekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c295b-104">CAS in .NET Framework should not be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="c295b-105">CAS und Security-Transparent Code werden nicht als Sicherheits Begrenzung mit teilweise vertrauenswürdigem Code unterstützt, insbesondere bei Code mit unbekannter Herkunft.</span><span class="sxs-lookup"><span data-stu-id="c295b-105">CAS and Security-Transparent Code are not supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="c295b-106">Wir raten davon ab, Code unbekannter Herkunft zu laden und auszuführen, ohne alternative Sicherheitsmaßnahmen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="c295b-106">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span> <span data-ttu-id="c295b-107">.NET Framework gibt keine Sicherheitspatches für Exploits mit Rechte Erweiterungen aus, die möglicherweise für den CAS-Sandkasten erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="c295b-107">.NET Framework will not issue security patches for any elevation-of-privilege exploits that might be discovered against the CAS sandbox.</span></span>
>
> <span data-ttu-id="c295b-108">Diese Richtlinie gilt für alle Versionen von .NET Framework, außer für die in Silverlight enthaltene .NET Framework-Version.</span><span class="sxs-lookup"><span data-stu-id="c295b-108">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>
