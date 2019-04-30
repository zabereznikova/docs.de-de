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
ms.openlocfilehash: 37e9926c8f9677e3b38202c5fb3c43f7b1159edf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61953568"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="83f75-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength-Methode</span><span class="sxs-lookup"><span data-stu-id="83f75-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="83f75-103">Ruft die Länge des Suchpfads ab.</span><span class="sxs-lookup"><span data-stu-id="83f75-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83f75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="83f75-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83f75-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="83f75-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="83f75-106">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe in Zeichen des Puffers erforderlich, um die Länge des Suchpfads enthalten.</span><span class="sxs-lookup"><span data-stu-id="83f75-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83f75-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="83f75-107">Return Value</span></span>  
 <span data-ttu-id="83f75-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="83f75-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83f75-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83f75-109">Requirements</span></span>  
 <span data-ttu-id="83f75-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="83f75-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83f75-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83f75-111">See also</span></span>

- [<span data-ttu-id="83f75-112">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83f75-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
