---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ad2167ab26eaa8164233ab9566854417f78df29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427869"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="2d9f4-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength-Methode</span><span class="sxs-lookup"><span data-stu-id="2d9f4-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="2d9f4-103">Ruft die Länge des Suchpfads ab.</span><span class="sxs-lookup"><span data-stu-id="2d9f4-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d9f4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d9f4-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d9f4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d9f4-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="2d9f4-106">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe Puffers in Zeichen, die benötigt, um die Länge des Suchpfads aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="2d9f4-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d9f4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2d9f4-107">Return Value</span></span>  
 <span data-ttu-id="2d9f4-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="2d9f4-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d9f4-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d9f4-109">Requirements</span></span>  
 <span data-ttu-id="2d9f4-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2d9f4-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d9f4-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d9f4-111">See Also</span></span>  
 [<span data-ttu-id="2d9f4-112">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d9f4-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
