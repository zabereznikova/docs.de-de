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
ms.openlocfilehash: 6ffab3b2f81680404f870cfd63ae5125173a346c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615513"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="82bf4-102">ISymUnmanagedReader::GetSymbolStoreFileName-Methode</span><span class="sxs-lookup"><span data-stu-id="82bf4-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="82bf4-103">Gibt den Dateinamen des Symbol Speicher auf dem Datenträger an.</span><span class="sxs-lookup"><span data-stu-id="82bf4-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82bf4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82bf4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82bf4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="82bf4-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="82bf4-106">in Die Größe des `szName` Puffers.</span><span class="sxs-lookup"><span data-stu-id="82bf4-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="82bf4-107">vorgenommen Ein Zeiger auf die Variable, die die Länge des in zurückgegebenen namens `szName` einschließlich der NULL-Beendigung empfängt.</span><span class="sxs-lookup"><span data-stu-id="82bf4-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="82bf4-108">vorgenommen Ein Zeiger auf die Variable, die den Dateinamen des Symbol Speicher empfängt.</span><span class="sxs-lookup"><span data-stu-id="82bf4-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82bf4-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="82bf4-109">Return Value</span></span>  
 <span data-ttu-id="82bf4-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="82bf4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82bf4-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82bf4-111">Requirements</span></span>  
 <span data-ttu-id="82bf4-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="82bf4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82bf4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82bf4-113">See also</span></span>

- [<span data-ttu-id="82bf4-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82bf4-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
