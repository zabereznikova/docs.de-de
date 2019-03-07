---
title: ISymUnmanagedReader::GetMethodsFromDocumentPosition-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f15e4c9b2421b9d2cafdbabf5f9ca12d1b8b9493
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492699"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="0ef94-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="0ef94-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="0ef94-103">Gibt ein Array der Methoden, von denen jede den Haltepunkt an der angegebenen Position in einem Dokument enthält.</span><span class="sxs-lookup"><span data-stu-id="0ef94-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ef94-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ef94-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ef94-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ef94-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="0ef94-106">[in] Das angegebene Dokument.</span><span class="sxs-lookup"><span data-stu-id="0ef94-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="0ef94-107">[in] Die Zeile des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="0ef94-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="0ef94-108">[in] Die Spalte des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="0ef94-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="0ef94-109">[in] Die Größe des `pRetVal`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="0ef94-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="0ef94-110">[out] Ein Zeiger auf eine Variable, die Anzahl der Elemente, die in zurückgegebenen empfängt, die `pRetVal` Array.</span><span class="sxs-lookup"><span data-stu-id="0ef94-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0ef94-111">[out] Ein Array von Zeigern, die jeweils auf eine [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) -Objekt, das eine Methode, die mit den Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="0ef94-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ef94-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0ef94-112">Return Value</span></span>  
 <span data-ttu-id="0ef94-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0ef94-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ef94-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ef94-114">Requirements</span></span>  
 <span data-ttu-id="0ef94-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0ef94-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef94-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ef94-116">See also</span></span>
- [<span data-ttu-id="0ef94-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ef94-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
