---
title: ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
ms.openlocfilehash: db065357e22ac576600a3ca61dda0882b9206a86
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129155"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="98834-102">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98834-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="98834-103">Ermöglicht das definieren Optionaler Async-Methoden Informationen für jedes Methoden Symbol.</span><span class="sxs-lookup"><span data-stu-id="98834-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="98834-104">Immer mit einer geöffneten Methode verwenden; Das heißt, zwischen Aufrufen der [OpenMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) und der [CloseMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="98834-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98834-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="98834-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="98834-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="98834-106">Methods</span></span>  
 <span data-ttu-id="98834-107">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="98834-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="98834-108">Methode</span><span class="sxs-lookup"><span data-stu-id="98834-108">Method</span></span>|<span data-ttu-id="98834-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98834-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98834-110">DefineAsyncStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="98834-110">DefineAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="98834-111">Definieren Sie eine Gruppe von asynchronen warte Vorgängen in der aktuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="98834-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="98834-112">Jeder yield-Offset entspricht der Return-Anweisung, die eine mögliche Rendite identifiziert.</span><span class="sxs-lookup"><span data-stu-id="98834-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="98834-113">Jede `breakpointMethod`/`breakpointOffset` Paars identifiziert, wo der asynchrone Vorgang fortgesetzt wird. Sie kann sich in einer anderen Methode befinden.</span><span class="sxs-lookup"><span data-stu-id="98834-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="98834-114">DefineCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="98834-114">DefineCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="98834-115">Legt den IL-Offset für den vom Compiler generierten catch-Handler fest, der eine Async-Methode umschließt.</span><span class="sxs-lookup"><span data-stu-id="98834-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="98834-116">Der IL-Offset des generierten catch wird vom Debugger verwendet, um den catch so zu behandeln, als ob es sich um Nichtbenutzer Code handelt, auch wenn er in einer Benutzercode Methode auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="98834-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="98834-117">Insbesondere wird **er als Reaktion auf ein Ereignis** vom Typ "Ereignis Ereignis Ereignis-Ausnahme" verwendet.</span><span class="sxs-lookup"><span data-stu-id="98834-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="98834-118">DefineKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="98834-118">DefineKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="98834-119">Legt die Anfangs Methode fest, die den asynchronen Vorgang initiiert.</span><span class="sxs-lookup"><span data-stu-id="98834-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98834-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="98834-120">Requirements</span></span>  
 <span data-ttu-id="98834-121">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="98834-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98834-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98834-122">See also</span></span>

- [<span data-ttu-id="98834-123">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="98834-123">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
