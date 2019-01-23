---
title: ISymUnmanagedReader::GetMethodFromDocumentPosition-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ebb1a13848b1c1336287413cdd7246da748ec864
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503958"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="82b6e-102">ISymUnmanagedReader::GetMethodFromDocumentPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="82b6e-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="82b6e-103">Gibt die Methode, die den Haltepunkt an der angegebenen Position in einem Dokument enthält.</span><span class="sxs-lookup"><span data-stu-id="82b6e-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82b6e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82b6e-104">Syntax</span></span>  
  
```  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82b6e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="82b6e-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="82b6e-106">[in] Das angegebene Dokument.</span><span class="sxs-lookup"><span data-stu-id="82b6e-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="82b6e-107">[in] Die Zeile des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="82b6e-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="82b6e-108">[in] Die Spalte des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="82b6e-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="82b6e-109">[out] Ein Zeiger auf die Adresse einer [ISymUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) Objekt, das die Methode, die mit den Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="82b6e-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82b6e-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="82b6e-110">Return Value</span></span>  
 <span data-ttu-id="82b6e-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="82b6e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82b6e-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82b6e-112">Requirements</span></span>  
 <span data-ttu-id="82b6e-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="82b6e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82b6e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82b6e-114">See also</span></span>
- [<span data-ttu-id="82b6e-115">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82b6e-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
