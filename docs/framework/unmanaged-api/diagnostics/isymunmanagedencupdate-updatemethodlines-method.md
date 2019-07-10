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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54789003f7454a65449e55ea4d990edd672d9c1b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774684"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="35dc6-102">ISymUnmanagedENCUpdate::UpdateMethodLines-Methode</span><span class="sxs-lookup"><span data-stu-id="35dc6-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="35dc6-103">Ermöglicht das Aktualisieren der Zeile für eine Methode, wurde nicht neu kompiliert, aber, deren Zeilen verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="35dc6-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="35dc6-104">Es ist eine Delta für jede Anweisung zulässig.</span><span class="sxs-lookup"><span data-stu-id="35dc6-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35dc6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="35dc6-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35dc6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="35dc6-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="35dc6-107">[in] Die Metadaten des Methodentokens.</span><span class="sxs-lookup"><span data-stu-id="35dc6-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="35dc6-108">[in] Ein Array von `INT32` Werte, die Deltas für jede Sequenzpunkt in der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="35dc6-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="35dc6-109">[in] Ein `ULONG` mit der Größe der `pDeltas` Parameter.</span><span class="sxs-lookup"><span data-stu-id="35dc6-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35dc6-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="35dc6-110">Return Value</span></span>  
 <span data-ttu-id="35dc6-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="35dc6-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35dc6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="35dc6-112">Requirements</span></span>  
 <span data-ttu-id="35dc6-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="35dc6-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35dc6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35dc6-114">See also</span></span>

- [<span data-ttu-id="35dc6-115">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35dc6-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
