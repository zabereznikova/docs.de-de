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
ms.openlocfilehash: d9431a533a32fd15931072cfbabd10bbc0e6d4ad
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610677"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="6e579-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath-Methode</span><span class="sxs-lookup"><span data-stu-id="6e579-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="6e579-103">Ruft den Suchpfad ab.</span><span class="sxs-lookup"><span data-stu-id="6e579-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e579-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e579-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e579-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6e579-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="6e579-106">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers in Zeichen empfängt, der den Suchpfad enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="6e579-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e579-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6e579-107">Return Value</span></span>  
 <span data-ttu-id="6e579-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="6e579-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e579-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6e579-109">Requirements</span></span>  
 <span data-ttu-id="6e579-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="6e579-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e579-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e579-111">See also</span></span>

- [<span data-ttu-id="6e579-112">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e579-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
