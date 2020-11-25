---
title: AssemblyComparisonResult-Enumeration
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
ms.openlocfilehash: cde25a9507006c89ef6490c13ae82033f04c2931
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731032"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="8f95f-102">AssemblyComparisonResult-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8f95f-102">AssemblyComparisonResult Enumeration</span></span>

<span data-ttu-id="8f95f-103">Gibt die Äquivalenz zweier Assemblyidentitäten an, die durch die [CompareAssemblyIdentity](compareassemblyidentity-function.md) -Funktion bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="8f95f-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f95f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f95f-104">Syntax</span></span>  
  
```cpp  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a><span data-ttu-id="8f95f-105">Member</span><span class="sxs-lookup"><span data-stu-id="8f95f-105">Members</span></span>  
  
|<span data-ttu-id="8f95f-106">Membername</span><span class="sxs-lookup"><span data-stu-id="8f95f-106">Member name</span></span>|<span data-ttu-id="8f95f-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8f95f-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="8f95f-108">Gibt an, dass alle Assemblyfelder im Vergleich stimmen.</span><span class="sxs-lookup"><span data-stu-id="8f95f-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="8f95f-109">Gibt an, dass Assemblys basierend auf der CLR-Vereinheitlichung (Common Language Runtime Version) der Assemblyversionsnummern in der .NET Framework Version 2,0 als äquivalent betrachtet werden</span><span class="sxs-lookup"><span data-stu-id="8f95f-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="8f95f-110">Gibt eine Teil Übereinstimmung der Assemblys basierend auf der CLR-Vereinheitlichung der Assemblyversionsnummern im .NET Framework 2,0 an.</span><span class="sxs-lookup"><span data-stu-id="8f95f-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="8f95f-111">Gibt eine Teil Übereinstimmung der Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="8f95f-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="8f95f-112">Gibt eine Teil Übereinstimmung der Assemblys basierend auf der Legacy-Vereinheitlichung von Versionsnummern an.</span><span class="sxs-lookup"><span data-stu-id="8f95f-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="8f95f-113">Gibt eine Teil Übereinstimmung von einfach benannten Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="8f95f-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="8f95f-114">Gibt an, dass Assemblys basierend auf der CLR-Vereinheitlichung der Versionsnummern in älteren Versionen der .NET Framework als gleichwertig betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="8f95f-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="8f95f-115">Gibt eine Entsprechung zwischen zwei einfach benannten Assemblys an, deren Versionsnummern ignoriert wurden.</span><span class="sxs-lookup"><span data-stu-id="8f95f-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="8f95f-116">Gibt an, dass zwischen den beiden Assemblys keine Entsprechung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="8f95f-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="8f95f-117">Gibt an, dass die beiden Assemblys mit Ausnahme ihrer Versionsnummern stimmen, die nur teilweise abgeglichen werden.</span><span class="sxs-lookup"><span data-stu-id="8f95f-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="8f95f-118">Gibt an, dass die beiden Assemblys mit Ausnahme ihrer Versionsnummern stimmen, die nicht mit identisch sind.</span><span class="sxs-lookup"><span data-stu-id="8f95f-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="8f95f-119">Gibt an, dass der Grund für die nicht Äquivalenz nicht bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="8f95f-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f95f-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8f95f-120">Requirements</span></span>  

 <span data-ttu-id="8f95f-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f95f-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f95f-122">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="8f95f-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8f95f-123">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8f95f-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8f95f-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f95f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f95f-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f95f-125">See also</span></span>

- [<span data-ttu-id="8f95f-126">CompareAssemblyIdentity-Funktion</span><span class="sxs-lookup"><span data-stu-id="8f95f-126">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)
- [<span data-ttu-id="8f95f-127">Fusionsenumerationen</span><span class="sxs-lookup"><span data-stu-id="8f95f-127">Fusion Enumerations</span></span>](fusion-enumerations.md)
