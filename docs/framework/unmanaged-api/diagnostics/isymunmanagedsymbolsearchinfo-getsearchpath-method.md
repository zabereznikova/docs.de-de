---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPath-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 649f44bd7966b9ca89d2d040b7eede662404aa0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638605"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="138d4-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath-Methode</span><span class="sxs-lookup"><span data-stu-id="138d4-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="138d4-103">Ruft den Pfad für die Suche.</span><span class="sxs-lookup"><span data-stu-id="138d4-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="138d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="138d4-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="138d4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="138d4-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="138d4-106">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des für den Suchpfad enthalten die erforderlichen Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="138d4-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="138d4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="138d4-107">Return Value</span></span>  
 <span data-ttu-id="138d4-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="138d4-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="138d4-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="138d4-109">Requirements</span></span>  
 <span data-ttu-id="138d4-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="138d4-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="138d4-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="138d4-111">See also</span></span>

- [<span data-ttu-id="138d4-112">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="138d4-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
