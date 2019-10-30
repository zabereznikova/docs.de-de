---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset-Methode
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: b108c8c87d3afdbfacb569ab501274e5c45c2e2e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129186"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="959c6-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="959c6-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="959c6-103">Legt den IL-Offset für den vom Compiler generierten catch-Handler fest, der eine Async-Methode umschließt.</span><span class="sxs-lookup"><span data-stu-id="959c6-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="959c6-104">Der IL-Offset des generierten catch wird vom Debugger verwendet, um den catch so zu behandeln, als ob es sich um Nichtbenutzer Code handelt, auch wenn er in einer Benutzercode Methode auftreten könnte.</span><span class="sxs-lookup"><span data-stu-id="959c6-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="959c6-105">Insbesondere wird **er als Reaktion auf ein Ereignis** vom Typ "Ereignis Ereignis Ereignis-Ausnahme" verwendet.</span><span class="sxs-lookup"><span data-stu-id="959c6-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="959c6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="959c6-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="959c6-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="959c6-107">Parameters</span></span>  
  
|<span data-ttu-id="959c6-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="959c6-108">Parameter</span></span>|<span data-ttu-id="959c6-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="959c6-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="959c6-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="959c6-110">Return Value</span></span>  
 <span data-ttu-id="959c6-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="959c6-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="959c6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="959c6-112">Requirements</span></span>  
 <span data-ttu-id="959c6-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="959c6-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="959c6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="959c6-114">See also</span></span>

- [<span data-ttu-id="959c6-115">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="959c6-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
