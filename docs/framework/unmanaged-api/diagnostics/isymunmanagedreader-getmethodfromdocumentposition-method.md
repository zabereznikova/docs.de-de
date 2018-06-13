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
ms.openlocfilehash: f756a6e80eee0998398b4955d1d091d97b2ad73f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426158"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="ca890-102">ISymUnmanagedReader::GetMethodFromDocumentPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="ca890-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="ca890-103">Gibt die Methode, die den Haltepunkt an der angegebenen Position in einem Dokument enthält.</span><span class="sxs-lookup"><span data-stu-id="ca890-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca890-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca890-104">Syntax</span></span>  
  
```  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca890-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca890-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="ca890-106">[in] Das angegebene Dokument.</span><span class="sxs-lookup"><span data-stu-id="ca890-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="ca890-107">[in] Die Zeile des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="ca890-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="ca890-108">[in] Die Spalte des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="ca890-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="ca890-109">[out] Ein Zeiger auf die Adresse einer [ISymUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) Objekt zur Darstellung der Methode, die den Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="ca890-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca890-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ca890-110">Return Value</span></span>  
 <span data-ttu-id="ca890-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ca890-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca890-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca890-112">Requirements</span></span>  
 <span data-ttu-id="ca890-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ca890-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca890-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca890-114">See Also</span></span>  
 [<span data-ttu-id="ca890-115">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca890-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
