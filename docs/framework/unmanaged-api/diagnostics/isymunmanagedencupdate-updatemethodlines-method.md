---
title: ISymUnmanagedENCUpdate::UpdateMethodLines-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
ms.openlocfilehash: 9aace77c4b3549c033433d4c305b07daa1f7a8c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448991"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="5c01a-102">ISymUnmanagedENCUpdate::UpdateMethodLines-Methode</span><span class="sxs-lookup"><span data-stu-id="5c01a-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="5c01a-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span><span class="sxs-lookup"><span data-stu-id="5c01a-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="5c01a-104">A delta for each statement is allowed.</span><span class="sxs-lookup"><span data-stu-id="5c01a-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c01a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c01a-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c01a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5c01a-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="5c01a-107">[in] The metadata of the method token.</span><span class="sxs-lookup"><span data-stu-id="5c01a-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="5c01a-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span><span class="sxs-lookup"><span data-stu-id="5c01a-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="5c01a-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span><span class="sxs-lookup"><span data-stu-id="5c01a-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c01a-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5c01a-110">Return Value</span></span>  
 <span data-ttu-id="5c01a-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="5c01a-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c01a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5c01a-112">Requirements</span></span>  
 <span data-ttu-id="5c01a-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5c01a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c01a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c01a-114">See also</span></span>

- [<span data-ttu-id="5c01a-115">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5c01a-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
