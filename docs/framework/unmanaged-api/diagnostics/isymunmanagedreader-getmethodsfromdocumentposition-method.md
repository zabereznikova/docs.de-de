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
ms.openlocfilehash: 8c84aceb0faabd879911e9595a7f3154065e2191
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426197"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="9e55f-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="9e55f-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="9e55f-103">Gibt ein Array der Methoden, von denen jede den Haltepunkt an der angegebenen Position in einem Dokument enthält.</span><span class="sxs-lookup"><span data-stu-id="9e55f-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e55f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e55f-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="9e55f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9e55f-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="9e55f-106">[in] Das angegebene Dokument.</span><span class="sxs-lookup"><span data-stu-id="9e55f-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="9e55f-107">[in] Die Zeile des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="9e55f-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="9e55f-108">[in] Die Spalte des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="9e55f-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="9e55f-109">[in] Die Größe des `pRetVal`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="9e55f-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="9e55f-110">[out] Ein Zeiger auf eine Variable, die Anzahl der Elemente im zurückgegebenen empfängt, die `pRetVal` Array.</span><span class="sxs-lookup"><span data-stu-id="9e55f-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="9e55f-111">[out] Ein Array von Zeigern, die jeweils auf ein [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) Objekt zur Darstellung einer Methode, die den Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="9e55f-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e55f-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9e55f-112">Return Value</span></span>  
 <span data-ttu-id="9e55f-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9e55f-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e55f-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e55f-114">Requirements</span></span>  
 <span data-ttu-id="9e55f-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9e55f-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e55f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e55f-116">See Also</span></span>  
 [<span data-ttu-id="9e55f-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e55f-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
