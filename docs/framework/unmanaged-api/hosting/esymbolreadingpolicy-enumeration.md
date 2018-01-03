---
title: ESymbolReadingPolicy-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ESymbolReadingPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ESymbolReadingPolicy
helpviewer_keywords: ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fdb18a343f91e85619f6d62e466fdd558044727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="78337-102">ESymbolReadingPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="78337-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="78337-103">Enthält Werte, die die Richtlinie für das Lesen der Programmdatenbankdateien (PDB) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="78337-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78337-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="78337-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="78337-105">Member</span><span class="sxs-lookup"><span data-stu-id="78337-105">Members</span></span>  
  
|<span data-ttu-id="78337-106">Member</span><span class="sxs-lookup"><span data-stu-id="78337-106">Member</span></span>|<span data-ttu-id="78337-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="78337-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="78337-108">Gibt an, dass der Debugger immer PDB-Dateien lesen sollten.</span><span class="sxs-lookup"><span data-stu-id="78337-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="78337-109">Gibt an, dass der Debugger nur PDB-Dateien gelesen werden soll, die vollständig vertrauenswürdige Assemblys zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="78337-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="78337-110">Gibt an, dass der Debugger niemals PDB-Dateien lesen soll.</span><span class="sxs-lookup"><span data-stu-id="78337-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78337-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="78337-111">Remarks</span></span>  
 <span data-ttu-id="78337-112">Die `ESymbolReadingPolicy` Enumeration wird zusammen mit den [ICLRDebugManager:: SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="78337-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78337-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="78337-113">Requirements</span></span>  
 <span data-ttu-id="78337-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78337-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78337-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="78337-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78337-116">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="78337-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78337-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78337-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78337-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78337-118">See Also</span></span>  
 [<span data-ttu-id="78337-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="78337-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
