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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208422"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="aba11-102">ESymbolReadingPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="aba11-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="aba11-103">Enthält Werte, die die Richtlinie für das Lesen von Programmdatenbankdateien (PDB) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="aba11-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aba11-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aba11-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="aba11-105">Member</span><span class="sxs-lookup"><span data-stu-id="aba11-105">Members</span></span>  
  
|<span data-ttu-id="aba11-106">Member</span><span class="sxs-lookup"><span data-stu-id="aba11-106">Member</span></span>|<span data-ttu-id="aba11-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aba11-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="aba11-108">Gibt an, dass der Debugger die PDB-Dateien immer lesen soll.</span><span class="sxs-lookup"><span data-stu-id="aba11-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="aba11-109">Gibt an, dass der Debugger nur PDB-Dateien gelesen werden soll, die mit vollständig vertrauenswürdigen Assemblys verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="aba11-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="aba11-110">Gibt an, dass der Debugger keine PDB-Dateien lesen soll.</span><span class="sxs-lookup"><span data-stu-id="aba11-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aba11-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aba11-111">Remarks</span></span>  
 <span data-ttu-id="aba11-112">Die `ESymbolReadingPolicy` Enumeration wird zusammen mit den [ICLRDebugManager:: SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="aba11-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aba11-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aba11-113">Requirements</span></span>  
 <span data-ttu-id="aba11-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aba11-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aba11-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aba11-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aba11-116">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aba11-116">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="aba11-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="aba11-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aba11-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aba11-118">See also</span></span>

- [<span data-ttu-id="aba11-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="aba11-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
