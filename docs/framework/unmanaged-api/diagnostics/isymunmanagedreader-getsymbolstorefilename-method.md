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
ms.openlocfilehash: 147b33a3f49f9163daea776779ca26f62561a84e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170377"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="caa86-102">ISymUnmanagedReader::GetSymbolStoreFileName-Methode</span><span class="sxs-lookup"><span data-stu-id="caa86-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="caa86-103">Enthält den Namen der Datei auf dem Datenträger von den Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="caa86-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caa86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="caa86-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="caa86-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="caa86-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="caa86-106">[in] Die Größe der `szName` Puffer.</span><span class="sxs-lookup"><span data-stu-id="caa86-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="caa86-107">[out] Ein Zeiger auf die Variable, die die Länge des Namens im zurückgegebenen empfängt `szName`, einschließlich der null-Terminierung.</span><span class="sxs-lookup"><span data-stu-id="caa86-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="caa86-108">[out] Ein Zeiger auf die Variable, die den Dateinamen des Symbolspeichers empfängt.</span><span class="sxs-lookup"><span data-stu-id="caa86-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="caa86-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="caa86-109">Return Value</span></span>  
 <span data-ttu-id="caa86-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="caa86-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caa86-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="caa86-111">Requirements</span></span>  
 <span data-ttu-id="caa86-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="caa86-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa86-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="caa86-113">See also</span></span>

- [<span data-ttu-id="caa86-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="caa86-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
