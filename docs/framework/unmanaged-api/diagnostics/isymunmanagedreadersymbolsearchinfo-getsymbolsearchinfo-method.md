---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
helpviewer_keywords:
- GetSymbolSearchInfo method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo method [.NET Framework debugging]
ms.assetid: 40fcdbc5-3bb2-41e9-b995-40984c209a7f
topic_type:
- apiref
ms.openlocfilehash: 2b5a42c89e0e3efed61b1b471c227e0df85a51aa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614902"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="28f77-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="28f77-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="28f77-103">Ruft Symbol Suchinformationen ab.</span><span class="sxs-lookup"><span data-stu-id="28f77-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28f77-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28f77-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28f77-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="28f77-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="28f77-106">in Eine `ULONG32` , die die Größe von angibt `rgpSearchInfo` .</span><span class="sxs-lookup"><span data-stu-id="28f77-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="28f77-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der zum enthalten der Suchinformationen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="28f77-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="28f77-108">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="28f77-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28f77-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="28f77-109">Return Value</span></span>  
 <span data-ttu-id="28f77-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="28f77-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28f77-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="28f77-111">Requirements</span></span>  
 <span data-ttu-id="28f77-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="28f77-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f77-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28f77-113">See also</span></span>

- [<span data-ttu-id="28f77-114">ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28f77-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)
