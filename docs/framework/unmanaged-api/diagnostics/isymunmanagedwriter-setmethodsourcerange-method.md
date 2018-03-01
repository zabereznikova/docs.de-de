---
title: ISymUnmanagedWriter::SetMethodSourceRange-Methode
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
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 09f82be130dba8087cf649d3e89bec8afc065e86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="7844d-102">ISymUnmanagedWriter::SetMethodSourceRange-Methode</span><span class="sxs-lookup"><span data-stu-id="7844d-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="7844d-103">Gibt "true" Anfang und Ende einer Methode innerhalb einer Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="7844d-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="7844d-104">Verwenden Sie diese Methode, um das Ausmaß der eine Methode unabhängig von der Sequenzpunkte anzugeben, die innerhalb der Methode vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="7844d-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7844d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7844d-105">Syntax</span></span>  
  
```  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7844d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7844d-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="7844d-107">[in] Ein Zeiger auf das Dokument, das die Startposition enthält.</span><span class="sxs-lookup"><span data-stu-id="7844d-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="7844d-108">[in] Die Nummer der Anfangszeile.</span><span class="sxs-lookup"><span data-stu-id="7844d-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="7844d-109">[in] Die Anfangsspalte.</span><span class="sxs-lookup"><span data-stu-id="7844d-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="7844d-110">[in] Ein Zeiger auf das Dokument, das die Endposition enthält.</span><span class="sxs-lookup"><span data-stu-id="7844d-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="7844d-111">[in] Die letzte Zeilennummer.</span><span class="sxs-lookup"><span data-stu-id="7844d-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="7844d-112">[in] Die Nummer der letzten.</span><span class="sxs-lookup"><span data-stu-id="7844d-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7844d-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7844d-113">Return Value</span></span>  
 <span data-ttu-id="7844d-114">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="7844d-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7844d-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7844d-115">Requirements</span></span>  
 <span data-ttu-id="7844d-116">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7844d-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7844d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7844d-117">See Also</span></span>  
 [<span data-ttu-id="7844d-118">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7844d-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
