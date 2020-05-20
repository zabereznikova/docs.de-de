---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset-Methode
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: 58dde2fcce3f4bf578907171e5b575c30c678cfc
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441772"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="f6669-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="f6669-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="f6669-103">Legt den IL-Offset für den vom Compiler generierten catch-Handler fest, der eine Async-Methode umschließt.</span><span class="sxs-lookup"><span data-stu-id="f6669-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="f6669-104">Der IL-Offset des generierten catch wird vom Debugger verwendet, um den catch so zu behandeln, als ob es sich um Nichtbenutzer Code handelt, auch wenn er in einer Benutzercode Methode auftreten könnte.</span><span class="sxs-lookup"><span data-stu-id="f6669-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="f6669-105">Insbesondere wird **er als Reaktion auf ein Ereignis** vom Typ "Ereignis Ereignis Ereignis-Ausnahme" verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6669-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6669-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6669-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6669-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6669-107">Parameters</span></span>  
  
|<span data-ttu-id="f6669-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6669-108">Parameter</span></span>|<span data-ttu-id="f6669-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f6669-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="f6669-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f6669-110">Return Value</span></span>  
 <span data-ttu-id="f6669-111">Gibt `HRESULT` zurück.</span><span class="sxs-lookup"><span data-stu-id="f6669-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6669-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6669-112">Requirements</span></span>  
 <span data-ttu-id="f6669-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="f6669-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6669-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6669-114">See also</span></span>

- [<span data-ttu-id="f6669-115">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6669-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
