---
title: ISymUnmanagedReader::GetSymAttribute-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetSymAttribute
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f57d2c4541945d90b1695850311928884fdc9cc5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="68796-102">ISymUnmanagedReader::GetSymAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="68796-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="68796-103">Ruft ein benutzerdefiniertes Attribut anhand seines Namens ab.</span><span class="sxs-lookup"><span data-stu-id="68796-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="68796-104">Diese benutzerdefinierten Attribute sind im Gegensatz zu benutzerdefinierten Metadatenattributen im Symbolspeicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="68796-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68796-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="68796-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="68796-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="68796-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="68796-107">[in] Das Metadatentoken für das Objekt, für das das Attribut angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="68796-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="68796-108">[in] Ein Zeiger auf die Variable, die die abzurufenden Attributs angibt.</span><span class="sxs-lookup"><span data-stu-id="68796-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="68796-109">[in] Die Größe des `buffer`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="68796-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="68796-110">[out] Ein Zeiger auf die Variable, die die Länge der Attributdaten empfängt.</span><span class="sxs-lookup"><span data-stu-id="68796-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="68796-111">[out] Ein Zeiger auf die Variable, die Attributdaten empfängt.</span><span class="sxs-lookup"><span data-stu-id="68796-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68796-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="68796-112">Return Value</span></span>  
 <span data-ttu-id="68796-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode...</span><span class="sxs-lookup"><span data-stu-id="68796-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code..</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68796-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68796-114">Requirements</span></span>  
 <span data-ttu-id="68796-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="68796-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68796-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68796-116">See Also</span></span>  
 [<span data-ttu-id="68796-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68796-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
