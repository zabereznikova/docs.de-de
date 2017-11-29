---
title: ISymUnmanagedWriter::SetMethodSourceRange-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.SetMethodSourceRange
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 85ed0a73b4862702895e737f2df639b8da7f7679
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="9c938-102">ISymUnmanagedWriter::SetMethodSourceRange-Methode</span><span class="sxs-lookup"><span data-stu-id="9c938-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="9c938-103">Gibt "true" Anfang und Ende einer Methode innerhalb einer Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="9c938-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="9c938-104">Verwenden Sie diese Methode, um das Ausmaß der eine Methode unabhängig von der Sequenzpunkte anzugeben, die innerhalb der Methode vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="9c938-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c938-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c938-105">Syntax</span></span>  
  
```  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c938-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9c938-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="9c938-107">[in] Ein Zeiger auf das Dokument, das die Startposition enthält.</span><span class="sxs-lookup"><span data-stu-id="9c938-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="9c938-108">[in] Die Nummer der Anfangszeile.</span><span class="sxs-lookup"><span data-stu-id="9c938-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="9c938-109">[in] Die Anfangsspalte.</span><span class="sxs-lookup"><span data-stu-id="9c938-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="9c938-110">[in] Ein Zeiger auf das Dokument, das die Endposition enthält.</span><span class="sxs-lookup"><span data-stu-id="9c938-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="9c938-111">[in] Die letzte Zeilennummer.</span><span class="sxs-lookup"><span data-stu-id="9c938-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="9c938-112">[in] Die Nummer der letzten.</span><span class="sxs-lookup"><span data-stu-id="9c938-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c938-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9c938-113">Return Value</span></span>  
 <span data-ttu-id="9c938-114">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9c938-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c938-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9c938-115">Requirements</span></span>  
 <span data-ttu-id="9c938-116">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9c938-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c938-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c938-117">See Also</span></span>  
 [<span data-ttu-id="9c938-118">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9c938-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
