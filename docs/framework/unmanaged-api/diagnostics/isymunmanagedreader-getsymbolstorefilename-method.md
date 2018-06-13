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
ms.openlocfilehash: b36f4007f286938169cc5d583908493916b9e6f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425339"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="7a2c3-102">ISymUnmanagedReader::GetSymbolStoreFileName-Methode</span><span class="sxs-lookup"><span data-stu-id="7a2c3-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="7a2c3-103">Enthält den Namen der Datei auf dem Datenträger für den Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="7a2c3-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a2c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a2c3-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a2c3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7a2c3-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="7a2c3-106">[in] Die Größe der `szName` Puffer.</span><span class="sxs-lookup"><span data-stu-id="7a2c3-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="7a2c3-107">[out] Ein Zeiger auf die Variable, die die Länge des Namens im zurückgegebenen empfängt `szName`, einschließlich der null-Terminierung.</span><span class="sxs-lookup"><span data-stu-id="7a2c3-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="7a2c3-108">[out] Ein Zeiger auf die Variable, die den Dateinamen der Symbolspeicher empfängt.</span><span class="sxs-lookup"><span data-stu-id="7a2c3-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a2c3-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7a2c3-109">Return Value</span></span>  
 <span data-ttu-id="7a2c3-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="7a2c3-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a2c3-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7a2c3-111">Requirements</span></span>  
 <span data-ttu-id="7a2c3-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7a2c3-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a2c3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a2c3-113">See Also</span></span>  
 [<span data-ttu-id="7a2c3-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a2c3-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
