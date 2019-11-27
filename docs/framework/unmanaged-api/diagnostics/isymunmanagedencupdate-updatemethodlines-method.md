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
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="88b1d-102">ISymUnmanagedENCUpdate::UpdateMethodLines-Methode</span><span class="sxs-lookup"><span data-stu-id="88b1d-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="88b1d-103">Ermöglicht das Aktualisieren der Zeilen Informationen für eine Methode, die nicht erneut kompiliert wurde, deren Zeilen jedoch unabhängig voneinander verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="88b1d-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="88b1d-104">Ein Delta für jede Anweisung ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="88b1d-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88b1d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="88b1d-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88b1d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="88b1d-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="88b1d-107">in Die Metadaten des Methoden Tokens.</span><span class="sxs-lookup"><span data-stu-id="88b1d-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="88b1d-108">in Ein Array von `INT32` Werten, das für jeden Sequenz Punkt in der Methode Delta-Werte angibt.</span><span class="sxs-lookup"><span data-stu-id="88b1d-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="88b1d-109">in Ein-`ULONG`, der die Größe des `pDeltas`-Parameters enthält.</span><span class="sxs-lookup"><span data-stu-id="88b1d-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88b1d-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="88b1d-110">Return Value</span></span>  
 <span data-ttu-id="88b1d-111">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="88b1d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88b1d-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="88b1d-112">Requirements</span></span>  
 <span data-ttu-id="88b1d-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="88b1d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88b1d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88b1d-114">See also</span></span>

- [<span data-ttu-id="88b1d-115">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="88b1d-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
