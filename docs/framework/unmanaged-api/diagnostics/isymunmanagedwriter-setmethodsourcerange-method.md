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
ms.openlocfilehash: 4ba3f31ae6d6b67d7beaa2f709bf6174b721136d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609520"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="908cb-102">ISymUnmanagedWriter::SetMethodSourceRange-Methode</span><span class="sxs-lookup"><span data-stu-id="908cb-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="908cb-103">Gibt den tatsächlichen Anfang und das tatsächliche Ende einer Methode in einer Quelldatei an.</span><span class="sxs-lookup"><span data-stu-id="908cb-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="908cb-104">Verwenden Sie diese Methode, um den Umfang einer Methode unabhängig von den Sequenz Punkten anzugeben, die in der Methode vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="908cb-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="908cb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="908cb-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="908cb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="908cb-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="908cb-107">in Ein Zeiger auf das Dokument, das die Anfangsposition enthält.</span><span class="sxs-lookup"><span data-stu-id="908cb-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="908cb-108">in Die Anfangs Zeilennummer.</span><span class="sxs-lookup"><span data-stu-id="908cb-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="908cb-109">in Die Anfangs Spalte.</span><span class="sxs-lookup"><span data-stu-id="908cb-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="908cb-110">in Ein Zeiger auf das Dokument, das die Endposition enthält.</span><span class="sxs-lookup"><span data-stu-id="908cb-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="908cb-111">in Die Endzeilennummer.</span><span class="sxs-lookup"><span data-stu-id="908cb-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="908cb-112">in Die Nummer der Endspalte.</span><span class="sxs-lookup"><span data-stu-id="908cb-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="908cb-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="908cb-113">Return Value</span></span>  
 <span data-ttu-id="908cb-114">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="908cb-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="908cb-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="908cb-115">Requirements</span></span>  
 <span data-ttu-id="908cb-116">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="908cb-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="908cb-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="908cb-117">See also</span></span>

- [<span data-ttu-id="908cb-118">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="908cb-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
