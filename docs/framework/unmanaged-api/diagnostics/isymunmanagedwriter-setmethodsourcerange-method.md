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
ms.openlocfilehash: 85e65f6a3ec13c2acc31b8f87dbe4b4476ffc2a5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427867"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="05322-102">ISymUnmanagedWriter::SetMethodSourceRange-Methode</span><span class="sxs-lookup"><span data-stu-id="05322-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="05322-103">Gibt den tatsächlichen Start und das Ende einer Methode in einer Quelldatei an.</span><span class="sxs-lookup"><span data-stu-id="05322-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="05322-104">Verwenden Sie diese Methode, um den Umfang einer Methode unabhängig von den Sequenz Punkten anzugeben, die in der Methode vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="05322-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05322-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="05322-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05322-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="05322-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="05322-107">in Ein Zeiger auf das Dokument, das die Anfangsposition enthält.</span><span class="sxs-lookup"><span data-stu-id="05322-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="05322-108">in Die Anfangs Zeilennummer.</span><span class="sxs-lookup"><span data-stu-id="05322-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="05322-109">in Die Anfangs Spalte.</span><span class="sxs-lookup"><span data-stu-id="05322-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="05322-110">in Ein Zeiger auf das Dokument, das die Endposition enthält.</span><span class="sxs-lookup"><span data-stu-id="05322-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="05322-111">in Die Endzeilennummer.</span><span class="sxs-lookup"><span data-stu-id="05322-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="05322-112">in Die Nummer der Endspalte.</span><span class="sxs-lookup"><span data-stu-id="05322-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05322-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="05322-113">Return Value</span></span>  
 <span data-ttu-id="05322-114">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="05322-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05322-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="05322-115">Requirements</span></span>  
 <span data-ttu-id="05322-116">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="05322-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05322-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05322-117">See also</span></span>

- [<span data-ttu-id="05322-118">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05322-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
