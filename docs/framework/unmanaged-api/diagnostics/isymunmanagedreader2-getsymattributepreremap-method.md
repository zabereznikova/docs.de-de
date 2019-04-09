---
title: ISymUnmanagedReader2::GetSymAttributePreRemap-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 543a8015e944333942b619060059273577902a74
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110291"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a><span data-ttu-id="0002c-102">ISymUnmanagedReader2::GetSymAttributePreRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="0002c-102">ISymUnmanagedReader2::GetSymAttributePreRemap Method</span></span>
<span data-ttu-id="0002c-103">Ruft ein benutzerdefiniertes Attribut anhand seines Namens ab.</span><span class="sxs-lookup"><span data-stu-id="0002c-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="0002c-104">Im Gegensatz zu benutzerdefinierten Metadatenattribute werden diese Attribute im Symbolspeicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0002c-104">Unlike metadata custom attributes, these attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0002c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0002c-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0002c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0002c-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="0002c-107">[in] Das Metadatentoken des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="0002c-107">[in] The metadata token of the parent.</span></span>  
  
 `name`  
 <span data-ttu-id="0002c-108">[in] Ein Zeiger auf eine `WCHAR` , die den Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="0002c-108">[in] A pointer to a `WCHAR` that contains the name.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="0002c-109">[in] Ein `ULONG32` , der angibt, dass der Größe des der `buffer` Array.</span><span class="sxs-lookup"><span data-stu-id="0002c-109">[in] A `ULONG32` that indicates the size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="0002c-110">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die Attribut-Bytes enthalten.</span><span class="sxs-lookup"><span data-stu-id="0002c-110">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the attribute bytes.</span></span>  
  
 `buffer`  
 <span data-ttu-id="0002c-111">[out] Ein Zeiger auf den Puffer, der die Attributdaten empfängt.</span><span class="sxs-lookup"><span data-stu-id="0002c-111">[out] A pointer to the buffer that receives the attribute bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0002c-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0002c-112">Return Value</span></span>  
 <span data-ttu-id="0002c-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0002c-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0002c-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0002c-114">Requirements</span></span>  
 <span data-ttu-id="0002c-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0002c-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0002c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0002c-116">See also</span></span>

- [<span data-ttu-id="0002c-117">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0002c-117">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
