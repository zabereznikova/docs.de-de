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
ms.openlocfilehash: 4450c262b75a73114cb7de7de98567f053bbf564
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894466"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="cd7f3-102">ISymUnmanagedWriter::SetSymAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="cd7f3-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="cd7f3-103">Definiert ein benutzerdefiniertes Attribut basierend auf seinem Namen.</span><span class="sxs-lookup"><span data-stu-id="cd7f3-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="cd7f3-104">Diese Attribute werden im Symbol Speicher gespeichert, im Gegensatz zu benutzerdefinierten Metadaten-Attributen.</span><span class="sxs-lookup"><span data-stu-id="cd7f3-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd7f3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd7f3-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd7f3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="cd7f3-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="cd7f3-107">in Das Metadatentoken, für das das Attribut definiert wird.</span><span class="sxs-lookup"><span data-stu-id="cd7f3-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="cd7f3-108">in Ein Zeiger auf einen `WCHAR` , der den Attributnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="cd7f3-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="cd7f3-109">in Ein `ULONG32` -Wert, der die Größe `data` des Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="cd7f3-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="cd7f3-110">in Der Attribut Wert.</span><span class="sxs-lookup"><span data-stu-id="cd7f3-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd7f3-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cd7f3-111">Return Value</span></span>  
 <span data-ttu-id="cd7f3-112">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="cd7f3-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd7f3-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd7f3-113">Requirements</span></span>  
 <span data-ttu-id="cd7f3-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cd7f3-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7f3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd7f3-115">See also</span></span>

- [<span data-ttu-id="cd7f3-116">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cd7f3-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
