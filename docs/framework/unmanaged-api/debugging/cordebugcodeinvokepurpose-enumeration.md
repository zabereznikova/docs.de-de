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
ms.openlocfilehash: cb65663ec1c1562009d0281c2e176b628b6366b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732176"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="5c6df-102">CorDebugCodeInvokePurpose-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="5c6df-102">CorDebugCodeInvokePurpose Enumeration</span></span>

<span data-ttu-id="5c6df-103">Beschreibt, warum durch eine exportierte Funktion verwalteter Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5c6df-103">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c6df-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c6df-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="5c6df-105">Member</span><span class="sxs-lookup"><span data-stu-id="5c6df-105">Members</span></span>  
  
|<span data-ttu-id="5c6df-106">Member</span><span class="sxs-lookup"><span data-stu-id="5c6df-106">Member</span></span>|<span data-ttu-id="5c6df-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c6df-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="5c6df-108">Keine oder unbekannt.</span><span class="sxs-lookup"><span data-stu-id="5c6df-108">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="5c6df-109">Der verwaltete Code führt alle verwalteten Einstiegspunkte (z. B. umgekehrte p-invoke-Punkte) auf.</span><span class="sxs-lookup"><span data-stu-id="5c6df-109">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="5c6df-110">Sämtliche detailliertere Zwecke sind in der Laufzeit unbekannt.</span><span class="sxs-lookup"><span data-stu-id="5c6df-110">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="5c6df-111">Der verwaltete Code führt einen statischen Konstruktor aus.</span><span class="sxs-lookup"><span data-stu-id="5c6df-111">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="5c6df-112">Der verwaltete Code führt die Implementierung für eine bestimmte Schnittstellenmethode aus, die aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="5c6df-112">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c6df-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5c6df-113">Remarks</span></span>  

 <span data-ttu-id="5c6df-114">Diese Enumeration wird von der [ICorDebugProcess6:: getexportstepinfo](icordebugprocess6-getexportstepinfo-method.md) -Methode verwendet, um Informationen über das Durchlaufen von verwaltetem Code bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5c6df-114">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c6df-115">Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="5c6df-115">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c6df-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5c6df-116">Requirements</span></span>  

 <span data-ttu-id="5c6df-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c6df-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c6df-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c6df-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c6df-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c6df-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c6df-120">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c6df-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c6df-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c6df-121">See also</span></span>

- [<span data-ttu-id="5c6df-122">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="5c6df-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="5c6df-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5c6df-123">Debugging</span></span>](index.md)
