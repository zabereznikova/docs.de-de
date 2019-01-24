---
title: ISymUnmanagedWriter::SetMethodSourceRange-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 40d05ee60d0183337e67b1f36722dff29ae9beaf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663543"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="0d338-102">ISymUnmanagedWriter::SetMethodSourceRange-Methode</span><span class="sxs-lookup"><span data-stu-id="0d338-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="0d338-103">Gibt an, den tatsächlichen Anfang und Ende einer Methode innerhalb einer Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="0d338-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="0d338-104">Verwenden Sie diese Methode, um die Reichweite einer Methode unabhängig von der Sequenzpunkte anzugeben, die innerhalb der Methode vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="0d338-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d338-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d338-105">Syntax</span></span>  
  
```  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d338-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0d338-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="0d338-107">[in] Ein Zeiger auf das Dokument, das die Anfangsposition enthält.</span><span class="sxs-lookup"><span data-stu-id="0d338-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="0d338-108">[in] Die Nummer der Anfangszeile.</span><span class="sxs-lookup"><span data-stu-id="0d338-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="0d338-109">[in] Die Anfangsspalte.</span><span class="sxs-lookup"><span data-stu-id="0d338-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="0d338-110">[in] Ein Zeiger auf das Dokument, das die Endposition enthält.</span><span class="sxs-lookup"><span data-stu-id="0d338-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="0d338-111">[in] Die Nummer der Endzeile.</span><span class="sxs-lookup"><span data-stu-id="0d338-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="0d338-112">[in] Die Nummer der Endspalte.</span><span class="sxs-lookup"><span data-stu-id="0d338-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d338-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0d338-113">Return Value</span></span>  
 <span data-ttu-id="0d338-114">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0d338-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d338-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0d338-115">Requirements</span></span>  
 <span data-ttu-id="0d338-116">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0d338-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d338-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d338-117">See also</span></span>
- [<span data-ttu-id="0d338-118">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d338-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
