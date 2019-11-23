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
ms.openlocfilehash: 8a4d205586921b377147eeab80754e1a0d9e52b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427842"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="dd8e2-102">ISymUnmanagedWriter::SetSymAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="dd8e2-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="dd8e2-103">Defines a custom attribute based upon its name.</span><span class="sxs-lookup"><span data-stu-id="dd8e2-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="dd8e2-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span><span class="sxs-lookup"><span data-stu-id="dd8e2-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd8e2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd8e2-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd8e2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="dd8e2-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="dd8e2-107">[in] The metadata token for which the attribute is being defined.</span><span class="sxs-lookup"><span data-stu-id="dd8e2-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="dd8e2-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span><span class="sxs-lookup"><span data-stu-id="dd8e2-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="dd8e2-109">[in] A `ULONG32` that indicates the size of the `data` array.</span><span class="sxs-lookup"><span data-stu-id="dd8e2-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="dd8e2-110">[in] The attribute value.</span><span class="sxs-lookup"><span data-stu-id="dd8e2-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd8e2-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dd8e2-111">Return Value</span></span>  
 <span data-ttu-id="dd8e2-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="dd8e2-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd8e2-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dd8e2-113">Requirements</span></span>  
 <span data-ttu-id="dd8e2-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dd8e2-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd8e2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd8e2-115">See also</span></span>

- [<span data-ttu-id="dd8e2-116">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd8e2-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
