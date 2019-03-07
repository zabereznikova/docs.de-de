---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset-Methode
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d000e61736f3250c677014cce50a2b7dcdecf1b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491686"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="f8f62-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="f8f62-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="f8f62-103">Legt fest, die IL-offset für den vom Compiler generierter Catch-Handler, der eine asynchrone Methode umschließt.</span><span class="sxs-lookup"><span data-stu-id="f8f62-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="f8f62-104">Der IL-Offset des generierten Catch wird vom Debugger verwendet, an die um Catch zu behandeln, als wäre es nicht benutzerseitiger Code, obwohl es in einer Code-Methode für Benutzer auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="f8f62-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="f8f62-105">Es wird insbesondere verwendet, als Reaktion auf eine **CatchHandlerFound** Ausnahmeereignisses.</span><span class="sxs-lookup"><span data-stu-id="f8f62-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8f62-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8f62-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8f62-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8f62-107">Parameters</span></span>  
  
|<span data-ttu-id="f8f62-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8f62-108">Parameter</span></span>|<span data-ttu-id="f8f62-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8f62-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="f8f62-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f8f62-110">Return Value</span></span>  
 <span data-ttu-id="f8f62-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="f8f62-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8f62-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8f62-112">Requirements</span></span>  
 <span data-ttu-id="f8f62-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f8f62-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f62-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8f62-114">See also</span></span>
- [<span data-ttu-id="f8f62-115">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8f62-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
