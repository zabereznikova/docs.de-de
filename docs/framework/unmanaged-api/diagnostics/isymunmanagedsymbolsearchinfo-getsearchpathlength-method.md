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
ms.openlocfilehash: 319ba58b5d012cbc0f9ddac0b83e5f3ae2ae062a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446180"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="a78f4-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength-Methode</span><span class="sxs-lookup"><span data-stu-id="a78f4-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="a78f4-103">Ruft die Länge des Suchpfads ab.</span><span class="sxs-lookup"><span data-stu-id="a78f4-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a78f4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a78f4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a78f4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a78f4-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="a78f4-106">vorgenommen Ein Zeiger auf einen `ULONG32`, der die Größe des Puffers, der die Länge des Suchpfads enthalten muss, in Zeichen empfängt.</span><span class="sxs-lookup"><span data-stu-id="a78f4-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a78f4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a78f4-107">Return Value</span></span>  
 <span data-ttu-id="a78f4-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a78f4-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a78f4-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a78f4-109">Requirements</span></span>  
 <span data-ttu-id="a78f4-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="a78f4-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a78f4-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a78f4-111">See also</span></span>

- [<span data-ttu-id="a78f4-112">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a78f4-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
