---
title: ISymUnmanagedENCUpdate::UpdateMethodLines-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate.UpdateMethodLines
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e8ffecba62b6531c852e6510013ba56b9258b64
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="c6d6b-102">ISymUnmanagedENCUpdate::UpdateMethodLines-Methode</span><span class="sxs-lookup"><span data-stu-id="c6d6b-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="c6d6b-103">Ermöglicht das Aktualisieren der Zeile für eine Methode, die nicht kompiliert wurde, aber, deren Zeilen verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="c6d6b-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="c6d6b-104">Eine Delta für jede Anweisung ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="c6d6b-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6d6b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6d6b-105">Syntax</span></span>  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6d6b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6d6b-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="c6d6b-107">[in] Die Metadaten der Methodentoken.</span><span class="sxs-lookup"><span data-stu-id="c6d6b-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="c6d6b-108">[in] Ein Array von `INT32` Werte, die Deltas für jeden Sequenzpunkt in der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="c6d6b-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="c6d6b-109">[in] Ein `ULONG` , enthält die Größe der `pDeltas` Parameter.</span><span class="sxs-lookup"><span data-stu-id="c6d6b-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6d6b-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c6d6b-110">Return Value</span></span>  
 <span data-ttu-id="c6d6b-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="c6d6b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6d6b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6d6b-112">Requirements</span></span>  
 <span data-ttu-id="c6d6b-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c6d6b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d6b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6d6b-114">See Also</span></span>  
 [<span data-ttu-id="c6d6b-115">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6d6b-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
