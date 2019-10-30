---
title: CorDebugCodeInvokePurpose-Aufzählung
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
ms.openlocfilehash: f037a28f0417f5607cd5b5637da4ca62e34e0edb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132263"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="ba3b4-102">CorDebugCodeInvokePurpose-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="ba3b4-102">CorDebugCodeInvokePurpose Enumeration</span></span>
<span data-ttu-id="ba3b4-103">Beschreibt, warum durch eine exportierte Funktion verwalteter Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ba3b4-103">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba3b4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba3b4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="ba3b4-105">Member</span><span class="sxs-lookup"><span data-stu-id="ba3b4-105">Members</span></span>  
  
|<span data-ttu-id="ba3b4-106">Member</span><span class="sxs-lookup"><span data-stu-id="ba3b4-106">Member</span></span>|<span data-ttu-id="ba3b4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba3b4-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="ba3b4-108">Keine oder unbekannt.</span><span class="sxs-lookup"><span data-stu-id="ba3b4-108">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="ba3b4-109">Der verwaltete Code führt alle verwalteten Einstiegspunkte (z. B. umgekehrte p-invoke-Punkte) auf.</span><span class="sxs-lookup"><span data-stu-id="ba3b4-109">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="ba3b4-110">Sämtliche detailliertere Zwecke sind in der Laufzeit unbekannt.</span><span class="sxs-lookup"><span data-stu-id="ba3b4-110">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="ba3b4-111">Der verwaltete Code führt einen statischen Konstruktor aus.</span><span class="sxs-lookup"><span data-stu-id="ba3b4-111">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="ba3b4-112">Der verwaltete Code führt die Implementierung für eine bestimmte Schnittstellenmethode aus, die aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba3b4-112">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba3b4-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba3b4-113">Remarks</span></span>  
 <span data-ttu-id="ba3b4-114">Diese Enumeration wird von der [ICorDebugProcess6:: getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) -Methode verwendet, um Informationen über das Durchlaufen von verwaltetem Code bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ba3b4-114">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba3b4-115">Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="ba3b4-115">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba3b4-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ba3b4-116">Requirements</span></span>  
 <span data-ttu-id="ba3b4-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba3b4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba3b4-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba3b4-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba3b4-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba3b4-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba3b4-120">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba3b4-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba3b4-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba3b4-121">See also</span></span>

- [<span data-ttu-id="ba3b4-122">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ba3b4-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="ba3b4-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ba3b4-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
