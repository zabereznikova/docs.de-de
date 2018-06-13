---
title: CorDebugMappingResult-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ca3f5a6af6ea19ec81af3f6ac0a028440f80d56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407958"
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="e7d70-102">CorDebugMappingResult-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e7d70-102">CorDebugMappingResult Enumeration</span></span>
<span data-ttu-id="e7d70-103">Stellt Details darüber bereit, wie der Wert des Anweisungszeigers (IP) abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="e7d70-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7d70-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7d70-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a><span data-ttu-id="e7d70-105">Member</span><span class="sxs-lookup"><span data-stu-id="e7d70-105">Members</span></span>  
  
|<span data-ttu-id="e7d70-106">Member</span><span class="sxs-lookup"><span data-stu-id="e7d70-106">Member</span></span>|<span data-ttu-id="e7d70-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7d70-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="e7d70-108">Der systemeigene Code ist im Prolog, damit der Wert der IP-0 ist.</span><span class="sxs-lookup"><span data-stu-id="e7d70-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="e7d70-109">Der systemeigene Code ist in einem Epilog, daher ist der Wert, der die IP-Adresse die Adresse der letzten Anweisung der Methode.</span><span class="sxs-lookup"><span data-stu-id="e7d70-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="e7d70-110">Keine Informationen über die Zuordnung ist für die Methode verfügbar, damit der Wert der IP-0 ist.</span><span class="sxs-lookup"><span data-stu-id="e7d70-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="e7d70-111">Zwar Zuordnungsinformationen für die Methode, kann die aktuelle Adresse Microsoft intermediate Language (MSIL)-Code zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="e7d70-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="e7d70-112">Der Wert, der die IP-Adresse ist 0.</span><span class="sxs-lookup"><span data-stu-id="e7d70-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="e7d70-113">Ordnet die Methode genau MSIL-Code oder der Rahmen hat interpretiert, sodass der Wert, der die IP-Adresse korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="e7d70-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="e7d70-114">Die Methode wurde erfolgreich zugeordnet, aber möglicherweise ist der Wert der IP-ungefähre.</span><span class="sxs-lookup"><span data-stu-id="e7d70-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7d70-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7d70-115">Remarks</span></span>  
 <span data-ttu-id="e7d70-116">Sie können die [ICorDebugILFrame:: GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) Methode, um den Wert des Anweisungszeigers abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e7d70-116">You can use the [ICorDebugILFrame::GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7d70-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7d70-117">Requirements</span></span>  
 <span data-ttu-id="e7d70-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7d70-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7d70-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7d70-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7d70-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7d70-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7d70-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7d70-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7d70-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7d70-122">See Also</span></span>  
 [<span data-ttu-id="e7d70-123">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e7d70-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
