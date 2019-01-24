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
ms.openlocfilehash: 15f85a6f5ab418692d747cc9ad415c637d7b96e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614366"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="a264e-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT-Methode</span><span class="sxs-lookup"><span data-stu-id="a264e-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="a264e-103">Ruft HRESULT ab.</span><span class="sxs-lookup"><span data-stu-id="a264e-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a264e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a264e-104">Syntax</span></span>  
  
```  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a264e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a264e-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="a264e-106">[out] Ein Zeiger auf den HRESULT-Wert.</span><span class="sxs-lookup"><span data-stu-id="a264e-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a264e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a264e-107">Return Value</span></span>  
 <span data-ttu-id="a264e-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a264e-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a264e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a264e-109">Requirements</span></span>  
 <span data-ttu-id="a264e-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a264e-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a264e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a264e-111">See also</span></span>
- [<span data-ttu-id="a264e-112">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a264e-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
