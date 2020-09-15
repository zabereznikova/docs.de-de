---
ms.openlocfilehash: e9d34465970287ed94c0f0373ee4ae94d55aa1ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617177"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a><span data-ttu-id="862e1-101">Die Methoden MachineKey.Encode und MachineKey.Decode sind jetzt veraltet</span><span class="sxs-lookup"><span data-stu-id="862e1-101">MachineKey.Encode and MachineKey.Decode methods are now obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="862e1-102">Details</span><span class="sxs-lookup"><span data-stu-id="862e1-102">Details</span></span>

<span data-ttu-id="862e1-103">Diese Methoden sind jetzt veraltet.</span><span class="sxs-lookup"><span data-stu-id="862e1-103">These methods are now obsolete.</span></span> <span data-ttu-id="862e1-104">Die Kompilierung von Code, der diese Methoden aufruft, erzeugt eine Compilerwarnung.</span><span class="sxs-lookup"><span data-stu-id="862e1-104">Compilation of code that calls these methods produces a compiler warning.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="862e1-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="862e1-105">Suggestion</span></span>

<span data-ttu-id="862e1-106">Die empfohlenen Alternativen sind <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> und <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span><span class="sxs-lookup"><span data-stu-id="862e1-106">The recommended alternatives are <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> and <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span></span> <span data-ttu-id="862e1-107">Alternativ können die Buildwarnungen unterdrückt oder durch die Verwendung eines älteren Compilers vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="862e1-107">Alternatively, the build warnings can be suppressed, or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="862e1-108">Die APIs werden weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="862e1-108">The APIs are still supported.</span></span>

| <span data-ttu-id="862e1-109">name</span><span class="sxs-lookup"><span data-stu-id="862e1-109">Name</span></span>    | <span data-ttu-id="862e1-110">Wert</span><span class="sxs-lookup"><span data-stu-id="862e1-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="862e1-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="862e1-111">Scope</span></span>   | <span data-ttu-id="862e1-112">Gering</span><span class="sxs-lookup"><span data-stu-id="862e1-112">Minor</span></span>       |
| <span data-ttu-id="862e1-113">Version</span><span class="sxs-lookup"><span data-stu-id="862e1-113">Version</span></span> | <span data-ttu-id="862e1-114">4.5</span><span class="sxs-lookup"><span data-stu-id="862e1-114">4.5</span></span>         |
| <span data-ttu-id="862e1-115">Typ</span><span class="sxs-lookup"><span data-stu-id="862e1-115">Type</span></span>    | <span data-ttu-id="862e1-116">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="862e1-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="862e1-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="862e1-117">Affected APIs</span></span>

- <xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
- <xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
