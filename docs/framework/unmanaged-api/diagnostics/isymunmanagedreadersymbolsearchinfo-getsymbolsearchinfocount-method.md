---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c87ef1b3ce185c2a92813f231abe6a9ef14ac055
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="8f984-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount-Methode</span><span class="sxs-lookup"><span data-stu-id="8f984-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="8f984-103">Ruft die Anzahl der Symbolinformationen für die Suche ab.</span><span class="sxs-lookup"><span data-stu-id="8f984-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f984-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f984-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f984-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f984-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="8f984-106">[] out] ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers benötigt, um die Suchinformationen aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="8f984-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f984-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8f984-107">Return Value</span></span>  
 <span data-ttu-id="8f984-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8f984-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f984-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f984-109">Requirements</span></span>  
 <span data-ttu-id="8f984-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8f984-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f984-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f984-111">See Also</span></span>  
 [<span data-ttu-id="8f984-112">ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f984-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
