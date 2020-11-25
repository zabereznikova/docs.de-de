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
ms.openlocfilehash: 0e7afa386af1bd2eebc2b58592d01b764660248f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704694"
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="6e07e-102">CorDebugMappingResult-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6e07e-102">CorDebugMappingResult Enumeration</span></span>

<span data-ttu-id="6e07e-103">Stellt Details darüber bereit, wie der Wert des Anweisungszeigers (IP) abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="6e07e-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e07e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e07e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a><span data-ttu-id="6e07e-105">Member</span><span class="sxs-lookup"><span data-stu-id="6e07e-105">Members</span></span>  
  
|<span data-ttu-id="6e07e-106">Member</span><span class="sxs-lookup"><span data-stu-id="6e07e-106">Member</span></span>|<span data-ttu-id="6e07e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6e07e-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="6e07e-108">Der Native Code befindet sich im Prolog, sodass der Wert der IP-Adresse 0 ist.</span><span class="sxs-lookup"><span data-stu-id="6e07e-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="6e07e-109">Der Native Code befindet sich in einem Epilog, sodass der Wert der IP-Adresse die Adresse der letzten Anweisung der Methode ist.</span><span class="sxs-lookup"><span data-stu-id="6e07e-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="6e07e-110">Es sind keine Mapping-Informationen für die-Methode verfügbar, daher ist der Wert der IP-Adresse 0.</span><span class="sxs-lookup"><span data-stu-id="6e07e-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="6e07e-111">Obwohl die-Methode Zuordnungsinformationen enthält, kann die aktuelle Adresse nicht dem MSIL-Code (Microsoft Intermediate Language) zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="6e07e-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="6e07e-112">Der Wert der IP-Adresse ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="6e07e-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="6e07e-113">Entweder wird die-Methode exakt dem MSIL-Code zugeordnet, oder der Frame wurde interpretiert, sodass der Wert der IP-Adresse korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="6e07e-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="6e07e-114">Die Methode wurde erfolgreich zugeordnet, aber der Wert der IP-Adresse kann ungefähre Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6e07e-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e07e-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e07e-115">Remarks</span></span>  

 <span data-ttu-id="6e07e-116">Sie können die [ICorDebugILFrame:: GetIP](icordebugilframe-getip-method.md) -Methode verwenden, um den Wert des Anweisungs Zeigers zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6e07e-116">You can use the [ICorDebugILFrame::GetIP](icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e07e-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6e07e-117">Requirements</span></span>  

 <span data-ttu-id="6e07e-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e07e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e07e-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e07e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e07e-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e07e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e07e-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e07e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e07e-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e07e-122">See also</span></span>

- [<span data-ttu-id="6e07e-123">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="6e07e-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
