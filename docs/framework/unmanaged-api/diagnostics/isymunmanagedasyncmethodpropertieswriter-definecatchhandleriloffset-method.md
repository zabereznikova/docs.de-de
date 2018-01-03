---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54cc369b309d1ffe20d0f3e6a2d4ae4e0443c85f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="800c4-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="800c4-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="800c4-103">Legt fest, die IL-offset für den vom Compiler generierte Catch-Handler, der eine asynchrone Methode umschließt.</span><span class="sxs-lookup"><span data-stu-id="800c4-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="800c4-104">Der IL-Offset des generierten Catch wird vom Debugger verwendet, an um den Catch zu behandeln, als wäre er Nichtbenutzercode, obwohl es in einer Benutzer-Codemethode auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="800c4-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="800c4-105">Insbesondere, dient er als Antwort auf eine **CatchHandlerFound** Ausnahmeereignisses.</span><span class="sxs-lookup"><span data-stu-id="800c4-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="800c4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="800c4-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="800c4-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="800c4-107">Parameters</span></span>  
  
|<span data-ttu-id="800c4-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="800c4-108">Parameter</span></span>|<span data-ttu-id="800c4-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="800c4-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="800c4-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="800c4-110">Return Value</span></span>  
 <span data-ttu-id="800c4-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="800c4-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="800c4-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="800c4-112">Requirements</span></span>  
 <span data-ttu-id="800c4-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="800c4-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="800c4-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="800c4-114">See Also</span></span>  
 [<span data-ttu-id="800c4-115">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="800c4-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
