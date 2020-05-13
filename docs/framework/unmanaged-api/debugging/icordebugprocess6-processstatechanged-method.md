---
title: ICorDebugProcess6::ProcessStateChanged-Methode
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 6be216741e902b15efc3a3ece95cb4a4229960e3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212845"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="ae93b-102">ICorDebugProcess6::ProcessStateChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="ae93b-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="ae93b-103">Benachrichtigt [ICorDebug](icordebug-interface.md) , dass der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ae93b-103">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae93b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae93b-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae93b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ae93b-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="ae93b-106">in Ein Member der [processstatechanged](icordebugprocess6-processstatechanged-method.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ae93b-106">[in] A member of the [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae93b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ae93b-107">Remarks</span></span>  
 <span data-ttu-id="ae93b-108">Der Debugger ruft diese Methode auf, um [ICorDebug](icordebug-interface.md) zu benachrichtigen, dass der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ae93b-108">The debugger calls this method to notify [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae93b-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ae93b-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae93b-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ae93b-110">Requirements</span></span>  
 <span data-ttu-id="ae93b-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae93b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae93b-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae93b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae93b-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae93b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae93b-114">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae93b-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae93b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae93b-115">See also</span></span>

- [<span data-ttu-id="ae93b-116">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ae93b-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="ae93b-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ae93b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
