---
title: ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 99d61fdb9f7e3eb2bc10de7584061d8922bf9285
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="9d98f-102">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9d98f-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="9d98f-103">Können Sie Informationen zu optionalen Async-Methode für jedes Symbol Methode definieren.</span><span class="sxs-lookup"><span data-stu-id="9d98f-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="9d98f-104">Verwenden Sie immer mit einer geöffneten Methode; d. h. zwischen den Aufrufen der [OpenMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) und [CloseMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="9d98f-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d98f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d98f-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="9d98f-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="9d98f-106">Methods</span></span>  
 <span data-ttu-id="9d98f-107">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="9d98f-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="9d98f-108">Methode</span><span class="sxs-lookup"><span data-stu-id="9d98f-108">Method</span></span>|<span data-ttu-id="9d98f-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d98f-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d98f-110">DefineAsyncStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="9d98f-110">DefineAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="9d98f-111">Definieren Sie eine Gruppe von asynchronen Vorgängen in der aktuellen Methode erwarten.</span><span class="sxs-lookup"><span data-stu-id="9d98f-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="9d98f-112">Jede Yield-Offset entspricht eine "await" return-Anweisung, einen potenziellen Rendite identifizieren.</span><span class="sxs-lookup"><span data-stu-id="9d98f-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="9d98f-113">Jede `breakpointMethod` / `breakpointOffset` Paar identifiziert, in dem der asynchrone Vorgang fortgesetzt wird, möglicherweise in einer anderen Methode.</span><span class="sxs-lookup"><span data-stu-id="9d98f-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="9d98f-114">DefineCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="9d98f-114">DefineCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="9d98f-115">Legt fest, die IL-offset für den vom Compiler generierte Catch-Handler, der eine asynchrone Methode umschließt.</span><span class="sxs-lookup"><span data-stu-id="9d98f-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="9d98f-116">Der IL-Offset des generierten Catch wird vom Debugger verwendet, Catch behandelt, als handele es sich um nicht-benutzerseitigen Code, obwohl es in einer Code Benutzermethode auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="9d98f-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="9d98f-117">Insbesondere, dient er als Antwort auf eine **CatchHandlerFound** Ausnahmeereignisses.</span><span class="sxs-lookup"><span data-stu-id="9d98f-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="9d98f-118">DefineKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="9d98f-118">DefineKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="9d98f-119">Legt die Start-Methode, die den asynchronen Vorgang initiiert.</span><span class="sxs-lookup"><span data-stu-id="9d98f-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d98f-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d98f-120">Requirements</span></span>  
 <span data-ttu-id="9d98f-121">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9d98f-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d98f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d98f-122">See Also</span></span>  
 [<span data-ttu-id="9d98f-123">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9d98f-123">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
