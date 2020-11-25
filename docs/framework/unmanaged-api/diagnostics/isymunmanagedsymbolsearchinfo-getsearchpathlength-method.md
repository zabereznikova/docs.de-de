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
ms.openlocfilehash: 9803094753dee27318af9981bd2e2ad196d434e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729069"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="91b8a-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength-Methode</span><span class="sxs-lookup"><span data-stu-id="91b8a-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>

<span data-ttu-id="91b8a-103">Ruft die Länge des Suchpfads ab.</span><span class="sxs-lookup"><span data-stu-id="91b8a-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91b8a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91b8a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91b8a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="91b8a-105">Parameters</span></span>  

 `pcchPath`  
 <span data-ttu-id="91b8a-106">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers, der die Länge des Suchpfads enthalten muss, in Zeichen empfängt.</span><span class="sxs-lookup"><span data-stu-id="91b8a-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91b8a-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="91b8a-107">Return Value</span></span>  

 <span data-ttu-id="91b8a-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="91b8a-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91b8a-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="91b8a-109">Requirements</span></span>  

 <span data-ttu-id="91b8a-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="91b8a-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91b8a-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91b8a-111">See also</span></span>

- [<span data-ttu-id="91b8a-112">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91b8a-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
