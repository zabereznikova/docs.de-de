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
ms.openlocfilehash: df503e44f20a0b1f02e2c609cc4b52712520faea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720567"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="05b6e-102">ISymUnmanagedReader::GetSymbolStoreFileName-Methode</span><span class="sxs-lookup"><span data-stu-id="05b6e-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>

<span data-ttu-id="05b6e-103">Gibt den Dateinamen des Symbol Speicher auf dem Datenträger an.</span><span class="sxs-lookup"><span data-stu-id="05b6e-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05b6e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05b6e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05b6e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="05b6e-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="05b6e-106">in Die Größe des `szName` Puffers.</span><span class="sxs-lookup"><span data-stu-id="05b6e-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="05b6e-107">vorgenommen Ein Zeiger auf die Variable, die die Länge des in zurückgegebenen namens `szName` einschließlich der NULL-Beendigung empfängt.</span><span class="sxs-lookup"><span data-stu-id="05b6e-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="05b6e-108">vorgenommen Ein Zeiger auf die Variable, die den Dateinamen des Symbol Speicher empfängt.</span><span class="sxs-lookup"><span data-stu-id="05b6e-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05b6e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="05b6e-109">Return Value</span></span>  

 <span data-ttu-id="05b6e-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="05b6e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05b6e-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="05b6e-111">Requirements</span></span>  

 <span data-ttu-id="05b6e-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="05b6e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05b6e-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05b6e-113">See also</span></span>

- [<span data-ttu-id="05b6e-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05b6e-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
