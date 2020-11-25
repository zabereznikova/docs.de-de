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
ms.openlocfilehash: ece5bd5373fed1a10e6592ff884e98b614e7991d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715989"
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="f42fe-102">CorDebugCodeInvokeKind-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="f42fe-102">CorDebugCodeInvokeKind Enumeration</span></span>

<span data-ttu-id="f42fe-103">Beschreibt, wie durch eine exportierte Funktion verwalteter Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f42fe-103">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f42fe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f42fe-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,
    CODE_INVOKE_KIND_RETURN,
    CODE_INVOKE_KIND_TAILCALL,
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="f42fe-105">Member</span><span class="sxs-lookup"><span data-stu-id="f42fe-105">Members</span></span>  
  
|<span data-ttu-id="f42fe-106">Member</span><span class="sxs-lookup"><span data-stu-id="f42fe-106">Member</span></span>|<span data-ttu-id="f42fe-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f42fe-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="f42fe-108">Wenn verwalteter Code durch diese Methode aufgerufen wird, muss diese von expliziten Ereignissen oder Haltepunkten später gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="f42fe-108">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="f42fe-109">– oder –</span><span class="sxs-lookup"><span data-stu-id="f42fe-109">--or--</span></span><br /><br /> <span data-ttu-id="f42fe-110">Man kann leicht einen Teil des verwalteten Codes, der durch diese Methode aufgerufen wird, übersehen, da gibt es keine einfache Möglichkeit gibt, diese anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="f42fe-110">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="f42fe-111">– oder –</span><span class="sxs-lookup"><span data-stu-id="f42fe-111">--or--</span></span><br /><br /> <span data-ttu-id="f42fe-112">Mit dieser Methode lässt sich verwalteter Code grundsätzlich nicht aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f42fe-112">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="f42fe-113">Mit dieser Methode wird verwalteter Code über eine Rückgabeanweisung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f42fe-113">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="f42fe-114">Mit dem Verlassen wird der nächste verwaltete Code aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f42fe-114">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="f42fe-115">Mit dieser Methode wird verwalteter Code über einen Endeaufruf aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f42fe-115">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="f42fe-116">Der verwaltete Code wird durch die Ausführung von Einzelschritten und das Überspringen von Aufrufanweisungen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f42fe-116">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f42fe-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f42fe-117">Remarks</span></span>  

 <span data-ttu-id="f42fe-118">Diese Enumeration wird von der [ICorDebugProcess6:: getexportstepinfo](icordebugprocess6-getexportstepinfo-method.md) -Methode verwendet, um Informationen über das Durchlaufen von verwaltetem Code bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f42fe-118">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f42fe-119">Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="f42fe-119">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f42fe-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f42fe-120">Requirements</span></span>  

 <span data-ttu-id="f42fe-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f42fe-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f42fe-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f42fe-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f42fe-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f42fe-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f42fe-124">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f42fe-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f42fe-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f42fe-125">See also</span></span>

- [<span data-ttu-id="f42fe-126">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="f42fe-126">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="f42fe-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f42fe-127">Debugging</span></span>](index.md)
