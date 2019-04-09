---
title: CorDebugCodeInvokeKind-Aufzählung
ms.date: 03/30/2017
api_name:
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3b4906f988d09f7b01aee40e8f63b589da5f33d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086415"
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="c6d72-102">CorDebugCodeInvokeKind-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="c6d72-102">CorDebugCodeInvokeKind Enumeration</span></span>
<span data-ttu-id="c6d72-103">Beschreibt, wie durch eine exportierte Funktion verwalteter Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c6d72-103">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6d72-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6d72-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="c6d72-105">Member</span><span class="sxs-lookup"><span data-stu-id="c6d72-105">Members</span></span>  
  
|<span data-ttu-id="c6d72-106">Member</span><span class="sxs-lookup"><span data-stu-id="c6d72-106">Member</span></span>|<span data-ttu-id="c6d72-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6d72-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="c6d72-108">Wenn verwalteter Code durch diese Methode aufgerufen wird, muss diese von expliziten Ereignissen oder Haltepunkten später gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="c6d72-108">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="c6d72-109">– oder –</span><span class="sxs-lookup"><span data-stu-id="c6d72-109">--or--</span></span><br /><br /> <span data-ttu-id="c6d72-110">Man kann leicht einen Teil des verwalteten Codes, der durch diese Methode aufgerufen wird, übersehen, da gibt es keine einfache Möglichkeit gibt, diese anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="c6d72-110">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="c6d72-111">– oder –</span><span class="sxs-lookup"><span data-stu-id="c6d72-111">--or--</span></span><br /><br /> <span data-ttu-id="c6d72-112">Mit dieser Methode lässt sich verwalteter Code grundsätzlich nicht aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c6d72-112">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="c6d72-113">Mit dieser Methode wird verwalteter Code über eine Rückgabeanweisung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c6d72-113">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="c6d72-114">Mit dem Verlassen wird der nächste verwaltete Code aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c6d72-114">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="c6d72-115">Mit dieser Methode wird verwalteter Code über einen Endeaufruf aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c6d72-115">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="c6d72-116">Der verwaltete Code wird durch die Ausführung von Einzelschritten und das Überspringen von Aufrufanweisungen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c6d72-116">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6d72-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6d72-117">Remarks</span></span>  
 <span data-ttu-id="c6d72-118">Diese Enumeration wird verwendet, durch die [icordebugprocess6:: Getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) Methode zum Bereitstellen von Informationen zum schrittweisen Durchlaufen von verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="c6d72-118">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6d72-119">Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="c6d72-119">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6d72-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6d72-120">Requirements</span></span>  
 <span data-ttu-id="c6d72-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6d72-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6d72-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6d72-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6d72-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6d72-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c6d72-124">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="c6d72-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c6d72-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6d72-125">See also</span></span>

- [<span data-ttu-id="c6d72-126">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="c6d72-126">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="c6d72-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c6d72-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
