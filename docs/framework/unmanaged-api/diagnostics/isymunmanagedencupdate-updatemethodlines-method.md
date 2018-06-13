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
ms.openlocfilehash: 50d9ac08b01a67df68ff077721ff5421fbc27707
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424273"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="12827-102">ISymUnmanagedENCUpdate::UpdateMethodLines-Methode</span><span class="sxs-lookup"><span data-stu-id="12827-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="12827-103">Ermöglicht das Aktualisieren der Zeile für eine Methode, die nicht kompiliert wurde, aber, deren Zeilen verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="12827-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="12827-104">Eine Delta für jede Anweisung ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="12827-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12827-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="12827-105">Syntax</span></span>  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12827-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="12827-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="12827-107">[in] Die Metadaten der Methodentoken.</span><span class="sxs-lookup"><span data-stu-id="12827-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="12827-108">[in] Ein Array von `INT32` Werte, die Deltas für jeden Sequenzpunkt in der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="12827-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="12827-109">[in] Ein `ULONG` , enthält die Größe der `pDeltas` Parameter.</span><span class="sxs-lookup"><span data-stu-id="12827-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12827-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="12827-110">Return Value</span></span>  
 <span data-ttu-id="12827-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="12827-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12827-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="12827-112">Requirements</span></span>  
 <span data-ttu-id="12827-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="12827-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12827-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12827-114">See Also</span></span>  
 [<span data-ttu-id="12827-115">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12827-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
