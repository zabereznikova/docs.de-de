---
title: ISymUnmanagedSymbolSearchInfo::GetHRESULT-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type:
- apiref
ms.openlocfilehash: 9dcd8282adf200932e86c950bee0b073780ce02d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615305"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="1c97f-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT-Methode</span><span class="sxs-lookup"><span data-stu-id="1c97f-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="1c97f-103">Ruft das HRESULT ab.</span><span class="sxs-lookup"><span data-stu-id="1c97f-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c97f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c97f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c97f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c97f-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="1c97f-106">vorgenommen Ein Zeiger auf das HRESULT.</span><span class="sxs-lookup"><span data-stu-id="1c97f-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c97f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1c97f-107">Return Value</span></span>  
 <span data-ttu-id="1c97f-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="1c97f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c97f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c97f-109">Requirements</span></span>  
 <span data-ttu-id="1c97f-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="1c97f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c97f-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c97f-111">See also</span></span>

- [<span data-ttu-id="1c97f-112">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c97f-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
