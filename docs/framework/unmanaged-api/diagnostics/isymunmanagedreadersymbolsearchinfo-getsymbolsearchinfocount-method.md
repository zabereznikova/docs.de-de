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
ms.openlocfilehash: a193c4e9e87616217efc90286032944d05d766c0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446397"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="dadf8-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount-Methode</span><span class="sxs-lookup"><span data-stu-id="dadf8-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="dadf8-103">Ruft die Anzahl der Symbol Suchinformationen ab.</span><span class="sxs-lookup"><span data-stu-id="dadf8-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dadf8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dadf8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dadf8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dadf8-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="dadf8-106">] out] ein Zeiger auf eine `ULONG32`, die die Größe des Puffers empfängt, der zum enthalten der Suchinformationen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="dadf8-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dadf8-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dadf8-107">Return Value</span></span>  
 <span data-ttu-id="dadf8-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="dadf8-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dadf8-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="dadf8-109">Requirements</span></span>  
 <span data-ttu-id="dadf8-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="dadf8-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dadf8-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dadf8-111">See also</span></span>

- [<span data-ttu-id="dadf8-112">ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dadf8-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
