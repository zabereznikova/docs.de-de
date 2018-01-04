---
title: ISymUnmanagedReader::GetSymbolStoreFileName-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetSymbolStoreFileName
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1646e8fa5f04da56e4489dca9581e9dc56e01d0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="06657-102">ISymUnmanagedReader::GetSymbolStoreFileName-Methode</span><span class="sxs-lookup"><span data-stu-id="06657-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="06657-103">Enthält den Namen der Datei auf dem Datenträger für den Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="06657-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06657-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06657-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="06657-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="06657-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="06657-106">[in] Die Größe der `szName` Puffer.</span><span class="sxs-lookup"><span data-stu-id="06657-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="06657-107">[out] Ein Zeiger auf die Variable, die die Länge des Namens im zurückgegebenen empfängt `szName`, einschließlich der null-Terminierung.</span><span class="sxs-lookup"><span data-stu-id="06657-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="06657-108">[out] Ein Zeiger auf die Variable, die den Dateinamen der Symbolspeicher empfängt.</span><span class="sxs-lookup"><span data-stu-id="06657-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06657-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="06657-109">Return Value</span></span>  
 <span data-ttu-id="06657-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="06657-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06657-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="06657-111">Requirements</span></span>  
 <span data-ttu-id="06657-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="06657-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06657-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06657-113">See Also</span></span>  
 [<span data-ttu-id="06657-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06657-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
