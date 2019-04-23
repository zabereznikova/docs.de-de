---
ms.openlocfilehash: 77e04333ed2b9a5ca8b900c1355fb5b12957772d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774354"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a><span data-ttu-id="be3f5-101">Die Methoden MachineKey.Encode und MachineKey.Decode sind jetzt veraltet</span><span class="sxs-lookup"><span data-stu-id="be3f5-101">MachineKey.Encode and MachineKey.Decode methods are now obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="be3f5-102">Details</span><span class="sxs-lookup"><span data-stu-id="be3f5-102">Details</span></span>|<span data-ttu-id="be3f5-103">Diese Methoden sind jetzt veraltet.</span><span class="sxs-lookup"><span data-stu-id="be3f5-103">These methods are now obsolete.</span></span> <span data-ttu-id="be3f5-104">Die Kompilierung von Code, der diese Methoden aufruft, erzeugt eine Compilerwarnung.</span><span class="sxs-lookup"><span data-stu-id="be3f5-104">Compilation of code that calls these methods produces a compiler warning.</span></span>|
|<span data-ttu-id="be3f5-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="be3f5-105">Suggestion</span></span>|<span data-ttu-id="be3f5-106">Die empfohlenen Alternativen sind <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> und <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span><span class="sxs-lookup"><span data-stu-id="be3f5-106">The recommended alternatives are <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> and <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span></span> <span data-ttu-id="be3f5-107">Alternativ können die Buildwarnungen unterdrückt oder durch die Verwendung eines älteren Compilers vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="be3f5-107">Alternatively, the build warnings can be suppressed, or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="be3f5-108">Die APIs werden weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be3f5-108">The APIs are still supported.</span></span>|
|<span data-ttu-id="be3f5-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="be3f5-109">Scope</span></span>|<span data-ttu-id="be3f5-110">Gering</span><span class="sxs-lookup"><span data-stu-id="be3f5-110">Minor</span></span>|
|<span data-ttu-id="be3f5-111">Version</span><span class="sxs-lookup"><span data-stu-id="be3f5-111">Version</span></span>|<span data-ttu-id="be3f5-112">4.5</span><span class="sxs-lookup"><span data-stu-id="be3f5-112">4.5</span></span>|
|<span data-ttu-id="be3f5-113">Typ</span><span class="sxs-lookup"><span data-stu-id="be3f5-113">Type</span></span>|<span data-ttu-id="be3f5-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="be3f5-114">Retargeting</span></span>|
|<span data-ttu-id="be3f5-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="be3f5-115">Affected APIs</span></span>|<ul><li><xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li><li><xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li></ul>|
