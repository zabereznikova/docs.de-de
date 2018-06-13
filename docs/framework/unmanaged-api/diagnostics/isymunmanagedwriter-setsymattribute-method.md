---
title: ISymUnmanagedWriter::SetSymAttribute-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd1a55d4100d74b769b2bc1b8fe33d2042f5e739
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428300"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="803af-102">ISymUnmanagedWriter::SetSymAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="803af-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="803af-103">Definiert ein benutzerdefiniertes Attribut anhand seines Namens.</span><span class="sxs-lookup"><span data-stu-id="803af-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="803af-104">Diese Attribute werden im Symbolspeicher, im Gegensatz zu benutzerdefinierten Metadatenattributen aufrechterhalten.</span><span class="sxs-lookup"><span data-stu-id="803af-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="803af-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="803af-105">Syntax</span></span>  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="803af-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="803af-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="803af-107">[in] Das Metadatentoken für das das Attribut definiert wird.</span><span class="sxs-lookup"><span data-stu-id="803af-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="803af-108">[in] Ein Zeiger auf eine `WCHAR` , enthält der Attributname.</span><span class="sxs-lookup"><span data-stu-id="803af-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="803af-109">[in] Ein `ULONG32` , der angibt, dass der Größe des der `data` Array.</span><span class="sxs-lookup"><span data-stu-id="803af-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="803af-110">[in] Der Attributwert.</span><span class="sxs-lookup"><span data-stu-id="803af-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="803af-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="803af-111">Return Value</span></span>  
 <span data-ttu-id="803af-112">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="803af-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="803af-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="803af-113">Requirements</span></span>  
 <span data-ttu-id="803af-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="803af-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="803af-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="803af-115">See Also</span></span>  
 [<span data-ttu-id="803af-116">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="803af-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
