---
title: ISymUnmanagedReader::GetSymbolStoreFileName-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymbolStoreFileName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6199a0d0444f07c57e88d0369f192684755d301c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705270"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="9ea33-102">ISymUnmanagedReader::GetSymbolStoreFileName-Methode</span><span class="sxs-lookup"><span data-stu-id="9ea33-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="9ea33-103">Enthält den Namen der Datei auf dem Datenträger von den Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="9ea33-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea33-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ea33-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ea33-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9ea33-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="9ea33-106">[in] Die Größe der `szName` Puffer.</span><span class="sxs-lookup"><span data-stu-id="9ea33-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9ea33-107">[out] Ein Zeiger auf die Variable, die die Länge des Namens im zurückgegebenen empfängt `szName`, einschließlich der null-Terminierung.</span><span class="sxs-lookup"><span data-stu-id="9ea33-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="9ea33-108">[out] Ein Zeiger auf die Variable, die den Dateinamen des Symbolspeichers empfängt.</span><span class="sxs-lookup"><span data-stu-id="9ea33-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ea33-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9ea33-109">Return Value</span></span>  
 <span data-ttu-id="9ea33-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9ea33-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ea33-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ea33-111">Requirements</span></span>  
 <span data-ttu-id="9ea33-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9ea33-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea33-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ea33-113">See also</span></span>
- [<span data-ttu-id="9ea33-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ea33-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
