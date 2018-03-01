---
title: ISymUnmanagedReader::GetMethodFromDocumentPosition-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fa9bfa324254a48d43c4c3df5ecebb91b3f0ae1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="f8ca2-102">ISymUnmanagedReader::GetMethodFromDocumentPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="f8ca2-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="f8ca2-103">Gibt die Methode, die den Haltepunkt an der angegebenen Position in einem Dokument enthält.</span><span class="sxs-lookup"><span data-stu-id="f8ca2-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8ca2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8ca2-104">Syntax</span></span>  
  
```  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8ca2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8ca2-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="f8ca2-106">[in] Das angegebene Dokument.</span><span class="sxs-lookup"><span data-stu-id="f8ca2-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="f8ca2-107">[in] Die Zeile des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="f8ca2-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="f8ca2-108">[in] Die Spalte des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="f8ca2-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="f8ca2-109">[out] Ein Zeiger auf die Adresse einer [ISymUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) Objekt zur Darstellung der Methode, die den Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="f8ca2-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8ca2-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f8ca2-110">Return Value</span></span>  
 <span data-ttu-id="f8ca2-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="f8ca2-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8ca2-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8ca2-112">Requirements</span></span>  
 <span data-ttu-id="f8ca2-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f8ca2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ca2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8ca2-114">See Also</span></span>  
 [<span data-ttu-id="f8ca2-115">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8ca2-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
