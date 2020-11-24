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
ms.openlocfilehash: a918b5c2334683348adc6a7382527faedb52d7b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683536"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="c107e-102">ISymUnmanagedWriter::SetMethodSourceRange-Methode</span><span class="sxs-lookup"><span data-stu-id="c107e-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>

<span data-ttu-id="c107e-103">Gibt den tatsächlichen Anfang und das tatsächliche Ende einer Methode in einer Quelldatei an.</span><span class="sxs-lookup"><span data-stu-id="c107e-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="c107e-104">Verwenden Sie diese Methode, um den Umfang einer Methode unabhängig von den Sequenz Punkten anzugeben, die in der Methode vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c107e-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c107e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c107e-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c107e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c107e-106">Parameters</span></span>  

 `startDoc`  
 <span data-ttu-id="c107e-107">in Ein Zeiger auf das Dokument, das die Anfangsposition enthält.</span><span class="sxs-lookup"><span data-stu-id="c107e-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="c107e-108">in Die Anfangs Zeilennummer.</span><span class="sxs-lookup"><span data-stu-id="c107e-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="c107e-109">in Die Anfangs Spalte.</span><span class="sxs-lookup"><span data-stu-id="c107e-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="c107e-110">in Ein Zeiger auf das Dokument, das die Endposition enthält.</span><span class="sxs-lookup"><span data-stu-id="c107e-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="c107e-111">in Die Endzeilennummer.</span><span class="sxs-lookup"><span data-stu-id="c107e-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="c107e-112">in Die Nummer der Endspalte.</span><span class="sxs-lookup"><span data-stu-id="c107e-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c107e-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c107e-113">Return Value</span></span>  

 <span data-ttu-id="c107e-114">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="c107e-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c107e-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c107e-115">Requirements</span></span>  

 <span data-ttu-id="c107e-116">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="c107e-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c107e-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c107e-117">See also</span></span>

- [<span data-ttu-id="c107e-118">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c107e-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
