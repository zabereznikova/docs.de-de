---
title: ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
ms.openlocfilehash: 779b737da43f61d1023a0a640dce936e11c4704c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707034"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="b408b-102">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b408b-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>

<span data-ttu-id="b408b-103">Ermöglicht das definieren Optionaler Async-Methoden Informationen für jedes Methoden Symbol.</span><span class="sxs-lookup"><span data-stu-id="b408b-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="b408b-104">Immer mit einer geöffneten Methode verwenden; Das heißt, zwischen Aufrufen der [OpenMethod-Methode](isymunmanagedwriter-openmethod-method.md) und der [CloseMethod-Methode](isymunmanagedwriter-closemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="b408b-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b408b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b408b-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="b408b-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="b408b-106">Methods</span></span>  

 <span data-ttu-id="b408b-107">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="b408b-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="b408b-108">Methode</span><span class="sxs-lookup"><span data-stu-id="b408b-108">Method</span></span>|<span data-ttu-id="b408b-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b408b-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b408b-110">DefineAsyncStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="b408b-110">DefineAsyncStepInfo Method</span></span>](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="b408b-111">Definieren Sie eine Gruppe von asynchronen warte Vorgängen in der aktuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="b408b-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="b408b-112">Jeder yield-Offset entspricht der Return-Anweisung, die eine mögliche Rendite identifiziert.</span><span class="sxs-lookup"><span data-stu-id="b408b-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="b408b-113">Jedes `breakpointMethod` / `breakpointOffset` paar gibt an, wo der asynchrone Vorgang fortgesetzt wird. er kann sich in einer anderen Methode befinden.</span><span class="sxs-lookup"><span data-stu-id="b408b-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="b408b-114">DefineCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="b408b-114">DefineCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="b408b-115">Legt den IL-Offset für den vom Compiler generierten catch-Handler fest, der eine Async-Methode umschließt.</span><span class="sxs-lookup"><span data-stu-id="b408b-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="b408b-116">Der IL-Offset des generierten catch wird vom Debugger verwendet, um den catch so zu behandeln, als ob es sich um Nichtbenutzer Code handelt, auch wenn er in einer Benutzercode Methode auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="b408b-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="b408b-117">Insbesondere wird **er als Reaktion auf ein Ereignis** vom Typ "Ereignis Ereignis Ereignis-Ausnahme" verwendet.</span><span class="sxs-lookup"><span data-stu-id="b408b-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="b408b-118">DefineKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="b408b-118">DefineKickoffMethod Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="b408b-119">Legt die Anfangs Methode fest, die den asynchronen Vorgang initiiert.</span><span class="sxs-lookup"><span data-stu-id="b408b-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b408b-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b408b-120">Requirements</span></span>  

 <span data-ttu-id="b408b-121">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="b408b-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b408b-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b408b-122">See also</span></span>

- [<span data-ttu-id="b408b-123">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b408b-123">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
