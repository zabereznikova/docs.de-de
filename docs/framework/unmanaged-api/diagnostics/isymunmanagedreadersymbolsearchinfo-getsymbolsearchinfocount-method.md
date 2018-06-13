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
ms.openlocfilehash: 103444e0b4b17b6384473eac714fba025cee9a55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426541"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="4c067-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount-Methode</span><span class="sxs-lookup"><span data-stu-id="4c067-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="4c067-103">Ruft die Anzahl der Symbolinformationen für die Suche ab.</span><span class="sxs-lookup"><span data-stu-id="4c067-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c067-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c067-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4c067-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4c067-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="4c067-106">[] out] ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers benötigt, um die Suchinformationen aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="4c067-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c067-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4c067-107">Return Value</span></span>  
 <span data-ttu-id="4c067-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="4c067-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c067-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c067-109">Requirements</span></span>  
 <span data-ttu-id="4c067-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4c067-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c067-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c067-111">See Also</span></span>  
 [<span data-ttu-id="4c067-112">ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4c067-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
