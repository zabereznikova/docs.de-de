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
ms.openlocfilehash: e17f88cf7f0d8572e65d00d8500a1fd83aa44eeb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663913"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="f757e-102">ESymbolReadingPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f757e-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="f757e-103">Enthält Werte, die die Richtlinie für das Lesen von Programmdatenbankdateien (PDB) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f757e-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f757e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f757e-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="f757e-105">Member</span><span class="sxs-lookup"><span data-stu-id="f757e-105">Members</span></span>  
  
|<span data-ttu-id="f757e-106">Member</span><span class="sxs-lookup"><span data-stu-id="f757e-106">Member</span></span>|<span data-ttu-id="f757e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f757e-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="f757e-108">Gibt an, dass der Debugger die PDB-Dateien immer lesen soll.</span><span class="sxs-lookup"><span data-stu-id="f757e-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="f757e-109">Gibt an, dass der Debugger nur PDB-Dateien gelesen werden soll, die mit vollständig vertrauenswürdigen Assemblys verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="f757e-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="f757e-110">Gibt an, dass der Debugger keine PDB-Dateien lesen soll.</span><span class="sxs-lookup"><span data-stu-id="f757e-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f757e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f757e-111">Remarks</span></span>  
 <span data-ttu-id="f757e-112">Die `ESymbolReadingPolicy` Enumeration wird zusammen mit den [ICLRDebugManager:: SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f757e-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f757e-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f757e-113">Requirements</span></span>  
 <span data-ttu-id="f757e-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f757e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f757e-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f757e-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f757e-116">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f757e-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f757e-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f757e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f757e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f757e-118">See also</span></span>
- [<span data-ttu-id="f757e-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="f757e-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
