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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 775f5a2129a635c79a48d5218d5eb91ee83ee779
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427882"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="fb940-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT-Methode</span><span class="sxs-lookup"><span data-stu-id="fb940-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="fb940-103">Ruft HRESULT ab.</span><span class="sxs-lookup"><span data-stu-id="fb940-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb940-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb940-104">Syntax</span></span>  
  
```  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb940-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fb940-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="fb940-106">[out] Ein Zeiger auf das HRESULT.</span><span class="sxs-lookup"><span data-stu-id="fb940-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb940-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fb940-107">Return Value</span></span>  
 <span data-ttu-id="fb940-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="fb940-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb940-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb940-109">Requirements</span></span>  
 <span data-ttu-id="fb940-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fb940-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb940-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb940-111">See Also</span></span>  
 [<span data-ttu-id="fb940-112">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb940-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
