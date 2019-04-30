---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset-Methode
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 923c85a9dff11753a338fcfd3673d3590fca607a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940126"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="319db-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="319db-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="319db-103">Legt fest, die IL-offset für den vom Compiler generierter Catch-Handler, der eine asynchrone Methode umschließt.</span><span class="sxs-lookup"><span data-stu-id="319db-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="319db-104">Der IL-Offset des generierten Catch wird vom Debugger verwendet, an die um Catch zu behandeln, als wäre es nicht benutzerseitiger Code, obwohl es in einer Code-Methode für Benutzer auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="319db-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="319db-105">Es wird insbesondere verwendet, als Reaktion auf eine **CatchHandlerFound** Ausnahmeereignisses.</span><span class="sxs-lookup"><span data-stu-id="319db-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="319db-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="319db-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="319db-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="319db-107">Parameters</span></span>  
  
|<span data-ttu-id="319db-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="319db-108">Parameter</span></span>|<span data-ttu-id="319db-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="319db-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="319db-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="319db-110">Return Value</span></span>  
 <span data-ttu-id="319db-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="319db-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="319db-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="319db-112">Requirements</span></span>  
 <span data-ttu-id="319db-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="319db-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="319db-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="319db-114">See also</span></span>

- [<span data-ttu-id="319db-115">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="319db-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
