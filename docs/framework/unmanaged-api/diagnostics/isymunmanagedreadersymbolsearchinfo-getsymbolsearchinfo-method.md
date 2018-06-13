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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 628d6fac45b046d9e8f26ad8777c38450da27a1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427417"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="39c76-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="39c76-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="39c76-103">Ruft die Symbolinformationen für die Suche ab.</span><span class="sxs-lookup"><span data-stu-id="39c76-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39c76-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="39c76-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39c76-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="39c76-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="39c76-106">[in] Ein `ULONG32` , der angibt, dass der Größe des `rgpSearchInfo`.</span><span class="sxs-lookup"><span data-stu-id="39c76-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="39c76-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers benötigt, um die Suchinformationen aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="39c76-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="39c76-108">[out] Ein Zeiger, der festgelegt wird, wird auf das zurückgegebene [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="39c76-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39c76-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="39c76-109">Return Value</span></span>  
 <span data-ttu-id="39c76-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="39c76-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39c76-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="39c76-111">Requirements</span></span>  
 <span data-ttu-id="39c76-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="39c76-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c76-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39c76-113">See Also</span></span>  
 [<span data-ttu-id="39c76-114">ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39c76-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
