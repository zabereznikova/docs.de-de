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
ms.openlocfilehash: e3cdb648397ca4f4aa2326e4f2349a5a14c3edcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178291"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="8aca7-102">AssemblyComparisonResult-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8aca7-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="8aca7-103">Gibt die Äquivalenz zweier Assemblyidentitäten an, die durch die [CompareAssemblyIdentity-Funktion](compareassemblyidentity-function.md) bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="8aca7-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aca7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8aca7-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="8aca7-105">Members</span><span class="sxs-lookup"><span data-stu-id="8aca7-105">Members</span></span>  
  
|<span data-ttu-id="8aca7-106">Membername</span><span class="sxs-lookup"><span data-stu-id="8aca7-106">Member name</span></span>|<span data-ttu-id="8aca7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8aca7-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="8aca7-108">Gibt an, dass alle Baugruppenfelder in der Vergleichsübereinstimmung übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8aca7-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="8aca7-109">Gibt an, dass Assemblys basierend auf der CLR-Vereinheitlichung (Common Language Runtime Version) von Assemblyversionsnummern in der .NET Framework Version 2.0 als gleichwertig betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="8aca7-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="8aca7-110">Gibt eine partielle Übereinstimmung der Assemblys basierend auf der CLR-Vereinheitlichung von Assemblyversionsnummern in .NET Framework 2.0 an.</span><span class="sxs-lookup"><span data-stu-id="8aca7-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="8aca7-111">Gibt eine teilgleiche Übereinstimmung der Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="8aca7-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="8aca7-112">Gibt eine teilweise Übereinstimmung der Assemblys basierend auf der älteren Vereinheitlichung von Versionsnummern an.</span><span class="sxs-lookup"><span data-stu-id="8aca7-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="8aca7-113">Gibt eine partielle Übereinstimmung von einfach benannten Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="8aca7-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="8aca7-114">Gibt an, dass Assemblys basierend auf der CLR-Vereinheitlichung von Versionsnummern in älteren Versionen von .NET Framework als gleichwertig betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="8aca7-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="8aca7-115">Gibt eine Übereinstimmung zwischen zwei einfach benannten Assemblys an, deren Versionsnummern ignoriert wurden.</span><span class="sxs-lookup"><span data-stu-id="8aca7-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="8aca7-116">Gibt an, dass keine Übereinstimmung zwischen den beiden Assemblys aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8aca7-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="8aca7-117">Gibt an, dass die beiden Assemblys mit Ausnahme ihrer Versionsnummern übereinstimmen, die nur teilweise übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8aca7-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="8aca7-118">Gibt an, dass die beiden Assemblys mit Ausnahme ihrer Versionsnummern übereinstimmen, die nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8aca7-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="8aca7-119">Gibt an, dass der Grund für die Nichtäquivalenz nicht bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="8aca7-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8aca7-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8aca7-120">Requirements</span></span>  
 <span data-ttu-id="8aca7-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8aca7-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aca7-122">**Kopfzeile:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="8aca7-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8aca7-123">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8aca7-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8aca7-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aca7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aca7-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8aca7-125">See also</span></span>

- [<span data-ttu-id="8aca7-126">CompareAssemblyIdentity-Funktion</span><span class="sxs-lookup"><span data-stu-id="8aca7-126">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)
- [<span data-ttu-id="8aca7-127">Fusionsenumerationen</span><span class="sxs-lookup"><span data-stu-id="8aca7-127">Fusion Enumerations</span></span>](fusion-enumerations.md)
