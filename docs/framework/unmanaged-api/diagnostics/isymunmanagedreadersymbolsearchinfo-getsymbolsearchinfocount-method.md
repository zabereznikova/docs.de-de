---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfoCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount
helpviewer_keywords:
- GetSymbolSearchInfoCount method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount method [.NET Framework debugging]
ms.assetid: 4068b6ec-525f-4446-8818-0296178cbd19
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b59d85227f21bb230333456eda9130416563111
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180530"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="6019b-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount-Methode</span><span class="sxs-lookup"><span data-stu-id="6019b-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="6019b-103">Ruft die Anzahl der Symbolinformationen für die Suche ab.</span><span class="sxs-lookup"><span data-stu-id="6019b-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6019b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6019b-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6019b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6019b-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="6019b-106">], out] ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die Suchinformationen.</span><span class="sxs-lookup"><span data-stu-id="6019b-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6019b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6019b-107">Return Value</span></span>  
 <span data-ttu-id="6019b-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="6019b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6019b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6019b-109">Requirements</span></span>  
 <span data-ttu-id="6019b-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6019b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6019b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6019b-111">See also</span></span>

- [<span data-ttu-id="6019b-112">ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6019b-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
