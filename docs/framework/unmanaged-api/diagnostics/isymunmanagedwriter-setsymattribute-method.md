---
title: ISymUnmanagedWriter::SetSymAttribute-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.SetSymAttribute
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90360d6fe5a1a95719a9bb09e5e0b6b2a70675a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="9b95f-102">ISymUnmanagedWriter::SetSymAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="9b95f-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="9b95f-103">Definiert ein benutzerdefiniertes Attribut anhand seines Namens.</span><span class="sxs-lookup"><span data-stu-id="9b95f-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="9b95f-104">Diese Attribute werden im Symbolspeicher, im Gegensatz zu benutzerdefinierten Metadatenattributen aufrechterhalten.</span><span class="sxs-lookup"><span data-stu-id="9b95f-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b95f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b95f-105">Syntax</span></span>  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b95f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b95f-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="9b95f-107">[in] Das Metadatentoken für das das Attribut definiert wird.</span><span class="sxs-lookup"><span data-stu-id="9b95f-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="9b95f-108">[in] Ein Zeiger auf eine `WCHAR` , enthält der Attributname.</span><span class="sxs-lookup"><span data-stu-id="9b95f-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="9b95f-109">[in] Ein `ULONG32` , der angibt, dass der Größe des der `data` Array.</span><span class="sxs-lookup"><span data-stu-id="9b95f-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="9b95f-110">[in] Der Attributwert.</span><span class="sxs-lookup"><span data-stu-id="9b95f-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b95f-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9b95f-111">Return Value</span></span>  
 <span data-ttu-id="9b95f-112">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9b95f-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b95f-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b95f-113">Requirements</span></span>  
 <span data-ttu-id="9b95f-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9b95f-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b95f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b95f-115">See Also</span></span>  
 [<span data-ttu-id="9b95f-116">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b95f-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
