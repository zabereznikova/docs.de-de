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
ms.openlocfilehash: a931c15b1c4a9f099d11c43edd324cfcc2793090
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722270"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="e016d-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT-Methode</span><span class="sxs-lookup"><span data-stu-id="e016d-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>

<span data-ttu-id="e016d-103">Ruft das HRESULT ab.</span><span class="sxs-lookup"><span data-stu-id="e016d-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e016d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e016d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e016d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e016d-105">Parameters</span></span>  

 `phr`  
 <span data-ttu-id="e016d-106">vorgenommen Ein Zeiger auf das HRESULT.</span><span class="sxs-lookup"><span data-stu-id="e016d-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e016d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e016d-107">Return Value</span></span>  

 <span data-ttu-id="e016d-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e016d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e016d-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e016d-109">Requirements</span></span>  

 <span data-ttu-id="e016d-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="e016d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e016d-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e016d-111">See also</span></span>

- [<span data-ttu-id="e016d-112">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e016d-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
