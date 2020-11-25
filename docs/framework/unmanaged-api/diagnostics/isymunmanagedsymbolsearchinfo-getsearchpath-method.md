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
ms.openlocfilehash: eda8a7ff1d8b3031173bf5f73a8b8a8355e6a62c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705526"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="d2cae-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath-Methode</span><span class="sxs-lookup"><span data-stu-id="d2cae-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>

<span data-ttu-id="d2cae-103">Ruft den Suchpfad ab.</span><span class="sxs-lookup"><span data-stu-id="d2cae-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2cae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2cae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2cae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2cae-105">Parameters</span></span>  

 `pcchPath`  
 <span data-ttu-id="d2cae-106">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers in Zeichen empfängt, der den Suchpfad enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="d2cae-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2cae-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d2cae-107">Return Value</span></span>  

 <span data-ttu-id="d2cae-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d2cae-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2cae-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d2cae-109">Requirements</span></span>  

 <span data-ttu-id="d2cae-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="d2cae-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2cae-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2cae-111">See also</span></span>

- [<span data-ttu-id="d2cae-112">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2cae-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
