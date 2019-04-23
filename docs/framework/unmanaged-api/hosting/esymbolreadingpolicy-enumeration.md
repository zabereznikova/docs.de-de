---
title: ESymbolReadingPolicy-Enumeration
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ba29952fe4a6edfc6e9e80ec02f82de65ef0064
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208422"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="84ce5-102">ESymbolReadingPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="84ce5-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="84ce5-103">Enthält Werte, die die Richtlinie für das Lesen von Programmdatenbankdateien (PDB) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="84ce5-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84ce5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84ce5-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="84ce5-105">Member</span><span class="sxs-lookup"><span data-stu-id="84ce5-105">Members</span></span>  
  
|<span data-ttu-id="84ce5-106">Member</span><span class="sxs-lookup"><span data-stu-id="84ce5-106">Member</span></span>|<span data-ttu-id="84ce5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84ce5-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="84ce5-108">Gibt an, dass der Debugger die PDB-Dateien immer lesen soll.</span><span class="sxs-lookup"><span data-stu-id="84ce5-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="84ce5-109">Gibt an, dass der Debugger nur PDB-Dateien gelesen werden soll, die mit vollständig vertrauenswürdigen Assemblys verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="84ce5-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="84ce5-110">Gibt an, dass der Debugger keine PDB-Dateien lesen soll.</span><span class="sxs-lookup"><span data-stu-id="84ce5-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84ce5-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84ce5-111">Remarks</span></span>  
 <span data-ttu-id="84ce5-112">Die `ESymbolReadingPolicy` Enumeration wird zusammen mit den [ICLRDebugManager:: SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="84ce5-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84ce5-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84ce5-113">Requirements</span></span>  
 <span data-ttu-id="84ce5-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84ce5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84ce5-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="84ce5-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84ce5-116">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="84ce5-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84ce5-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84ce5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84ce5-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84ce5-118">See also</span></span>

- [<span data-ttu-id="84ce5-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="84ce5-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
