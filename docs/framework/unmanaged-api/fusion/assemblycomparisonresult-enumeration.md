---
title: AssemblyComparisonResult-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2c38561a804a331df102a600d4b0b0f6312aaa6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="82382-102">AssemblyComparisonResult-Enumeration</span><span class="sxs-lookup"><span data-stu-id="82382-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="82382-103">Gibt die Gleichwertigkeit von zwei Assemblyidentitäten an, durch die [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="82382-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82382-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82382-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="82382-105">Member</span><span class="sxs-lookup"><span data-stu-id="82382-105">Members</span></span>  
  
|<span data-ttu-id="82382-106">Membername</span><span class="sxs-lookup"><span data-stu-id="82382-106">Member name</span></span>|<span data-ttu-id="82382-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82382-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="82382-108">Gibt an, dass alle im Vergleich übereinstimmen Assemblyfelder.</span><span class="sxs-lookup"><span data-stu-id="82382-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="82382-109">Gibt an, dass Assemblys als gleichwertig basierend auf die common Language Runtime-Version (CLR) Vereinheitlichung von Assemblyversionsnummern in .NET Framework, Version 2.0 betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="82382-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="82382-110">Gibt eine partielle Übereinstimmung der basierend auf die CLR-Vereinheitlichung der Assemblyversionsnummern in .NET Framework 2.0-Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="82382-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="82382-111">Gibt eine partielle Übereinstimmung der Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="82382-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="82382-112">Gibt eine partielle Übereinstimmung basierend auf älteren Vereinheitlichung der Versionsnummern Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="82382-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="82382-113">Gibt eine partielle Übereinstimmung von Assemblys mit einfachen Namen an.</span><span class="sxs-lookup"><span data-stu-id="82382-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="82382-114">Gibt an, dass Assemblys als gleichwertig basierend auf die CLR-Vereinheitlichung der Versionsnummern in älteren Versionen von .NET Framework betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="82382-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="82382-115">Gibt an, eine Übereinstimmung zwischen zwei Assemblys mit einfachen Namen, deren Versionsnummern ignoriert wurden.</span><span class="sxs-lookup"><span data-stu-id="82382-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="82382-116">Gibt an, dass keine Übereinstimmung zwischen den beiden Assemblys aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="82382-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="82382-117">Gibt an, dass die zwei Assemblys mit Ausnahme von deren Versionsnummern übereinstimmen, die nur teilweise übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82382-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="82382-118">Gibt an, dass die zwei Assemblys mit Ausnahme von deren Versionsnummern übereinstimmen, was die stimmen nicht überein.</span><span class="sxs-lookup"><span data-stu-id="82382-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="82382-119">Gibt an, dass die Ursache für nicht vorhandene Äquivalenz nicht bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="82382-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="82382-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82382-120">Requirements</span></span>  
 <span data-ttu-id="82382-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82382-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82382-122">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="82382-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="82382-123">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="82382-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="82382-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82382-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82382-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82382-125">See Also</span></span>  
 [<span data-ttu-id="82382-126">CompareAssemblyIdentity-Funktion</span><span class="sxs-lookup"><span data-stu-id="82382-126">CompareAssemblyIdentity Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 [<span data-ttu-id="82382-127">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="82382-127">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
