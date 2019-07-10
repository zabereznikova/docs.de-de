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
ms.openlocfilehash: 50cd6d1e3666dd1f15c1e6a6b4f7dcb931b79d8d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777064"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="66fd1-102">ISymUnmanagedReader::GetSymbolStoreFileName-Methode</span><span class="sxs-lookup"><span data-stu-id="66fd1-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="66fd1-103">Enthält den Namen der Datei auf dem Datenträger von den Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="66fd1-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66fd1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="66fd1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66fd1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="66fd1-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="66fd1-106">[in] Die Größe der `szName` Puffer.</span><span class="sxs-lookup"><span data-stu-id="66fd1-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="66fd1-107">[out] Ein Zeiger auf die Variable, die die Länge des Namens im zurückgegebenen empfängt `szName`, einschließlich der null-Terminierung.</span><span class="sxs-lookup"><span data-stu-id="66fd1-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="66fd1-108">[out] Ein Zeiger auf die Variable, die den Dateinamen des Symbolspeichers empfängt.</span><span class="sxs-lookup"><span data-stu-id="66fd1-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66fd1-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="66fd1-109">Return Value</span></span>  
 <span data-ttu-id="66fd1-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="66fd1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66fd1-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66fd1-111">Requirements</span></span>  
 <span data-ttu-id="66fd1-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="66fd1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66fd1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66fd1-113">See also</span></span>

- [<span data-ttu-id="66fd1-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66fd1-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
