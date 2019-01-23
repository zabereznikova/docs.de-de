---
title: ISymUnmanagedReader::GetSymAttribute-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d43467a0f3ff94eb7903b808e192230e6c0ff1e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561067"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="9fada-102">ISymUnmanagedReader::GetSymAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="9fada-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="9fada-103">Ruft ein benutzerdefiniertes Attribut anhand seines Namens ab.</span><span class="sxs-lookup"><span data-stu-id="9fada-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="9fada-104">Im Gegensatz zu benutzerdefinierten Metadatenattributen befinden sich diese benutzerdefinierten Attribute im Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="9fada-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fada-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fada-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9fada-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9fada-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="9fada-107">[in] Das Metadatentoken für das Objekt, das für das das Attribut angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="9fada-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="9fada-108">[in] Ein Zeiger auf die Variable, die das abzurufende Attribut angibt.</span><span class="sxs-lookup"><span data-stu-id="9fada-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="9fada-109">[in] Die Größe des `buffer`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="9fada-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="9fada-110">[out] Ein Zeiger auf die Variable, die die Länge der Attributdaten empfängt.</span><span class="sxs-lookup"><span data-stu-id="9fada-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="9fada-111">[out] Ein Zeiger auf die Variable, die Attributdaten empfängt.</span><span class="sxs-lookup"><span data-stu-id="9fada-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fada-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9fada-112">Return Value</span></span>  
 <span data-ttu-id="9fada-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode...</span><span class="sxs-lookup"><span data-stu-id="9fada-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code..</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fada-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9fada-114">Requirements</span></span>  
 <span data-ttu-id="9fada-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9fada-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fada-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fada-116">See also</span></span>
- [<span data-ttu-id="9fada-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9fada-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
