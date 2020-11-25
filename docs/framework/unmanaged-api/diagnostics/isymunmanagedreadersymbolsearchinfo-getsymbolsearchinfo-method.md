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
ms.openlocfilehash: 69e05fc33b3489f535f1d051da0294fe59e11e00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708958"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="90c8c-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="90c8c-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>

<span data-ttu-id="90c8c-103">Ruft Symbol Suchinformationen ab.</span><span class="sxs-lookup"><span data-stu-id="90c8c-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90c8c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90c8c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90c8c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="90c8c-105">Parameters</span></span>  

 `cSearchInfo`  
 <span data-ttu-id="90c8c-106">in Eine `ULONG32` , die die Größe von angibt `rgpSearchInfo` .</span><span class="sxs-lookup"><span data-stu-id="90c8c-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="90c8c-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der zum enthalten der Suchinformationen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="90c8c-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="90c8c-108">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="90c8c-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90c8c-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="90c8c-109">Return Value</span></span>  

 <span data-ttu-id="90c8c-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="90c8c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90c8c-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="90c8c-111">Requirements</span></span>  

 <span data-ttu-id="90c8c-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="90c8c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90c8c-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90c8c-113">See also</span></span>

- [<span data-ttu-id="90c8c-114">ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90c8c-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)
