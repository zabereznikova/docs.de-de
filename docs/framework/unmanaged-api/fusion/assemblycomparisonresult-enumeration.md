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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6c417eec9583ff069c9d61fa31e9c14f3931130
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778507"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="8203b-102">AssemblyComparisonResult-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8203b-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="8203b-103">Gibt die Gleichwertigkeit von zwei Assemblyidentitäten, bestimmt durch die [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="8203b-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8203b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8203b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="8203b-105">Member</span><span class="sxs-lookup"><span data-stu-id="8203b-105">Members</span></span>  
  
|<span data-ttu-id="8203b-106">Membername</span><span class="sxs-lookup"><span data-stu-id="8203b-106">Member name</span></span>|<span data-ttu-id="8203b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8203b-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="8203b-108">Gibt an, dass alle im Vergleich übereinstimmen Assemblyfelder.</span><span class="sxs-lookup"><span data-stu-id="8203b-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="8203b-109">Gibt an, dass Assemblys als gleichwertig basierend auf der common Language Runtime-Version (CLR) Vereinheitlichung von Assemblyversionsnummern in .NET Framework, Version 2.0 angesehen werden.</span><span class="sxs-lookup"><span data-stu-id="8203b-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="8203b-110">Gibt eine teilweise Übereinstimmung der basierend auf der CLR-Vereinheitlichung der Assembly-Versionsnummern in .NET Framework 2.0-Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="8203b-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="8203b-111">Gibt eine teilweise Übereinstimmung der Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="8203b-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="8203b-112">Gibt eine teilweise Übereinstimmung der älteren aufgrund der Vereinheitlichung der Versionsnummern in Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="8203b-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="8203b-113">Gibt eine teilweise Übereinstimmung von Assemblys mit einfachen Namen an.</span><span class="sxs-lookup"><span data-stu-id="8203b-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="8203b-114">Gibt an, dass Assemblys als gleichwertig basierend auf der CLR-Vereinheitlichung der Versionsnummern in älteren Versionen von .NET Framework angesehen werden.</span><span class="sxs-lookup"><span data-stu-id="8203b-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="8203b-115">Gibt eine Übereinstimmung zwischen zwei Assemblys, die eine Verbindung, deren Versionsnummern ignoriert wurden, mit einfachen Namen an.</span><span class="sxs-lookup"><span data-stu-id="8203b-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="8203b-116">Gibt an, dass keine Übereinstimmung zwischen den beiden Assemblys aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8203b-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="8203b-117">Gibt an, dass die beiden Assemblys ihre Versionsnummern übereinstimmen, die nur teilweise übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8203b-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="8203b-118">Gibt an, dass die beiden Assemblys ihre Versionsnummern übereinstimmen, die nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8203b-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="8203b-119">Gibt an, dass der Grund für nicht vorhandene Äquivalenz nicht bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="8203b-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8203b-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8203b-120">Requirements</span></span>  
 <span data-ttu-id="8203b-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8203b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8203b-122">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="8203b-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8203b-123">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8203b-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8203b-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8203b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8203b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8203b-125">See also</span></span>

- [<span data-ttu-id="8203b-126">CompareAssemblyIdentity-Funktion</span><span class="sxs-lookup"><span data-stu-id="8203b-126">CompareAssemblyIdentity Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)
- [<span data-ttu-id="8203b-127">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="8203b-127">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
