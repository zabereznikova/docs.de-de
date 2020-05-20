---
title: ISymUnmanagedWriter::OpenMethod-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
ms.openlocfilehash: d2d16ab0a29fadd3a64d906a64fc46c422e01c45
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610040"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="c789d-102">ISymUnmanagedWriter::OpenMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="c789d-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="c789d-103">Öffnet eine Methode, in die Symbol Informationen ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c789d-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="c789d-104">Die angegebene Methode wird zur aktuellen Methode für Aufrufe zum Definieren von Sequenz Punkten, Parametern und lexikalischen Gültigkeitsbereichen.</span><span class="sxs-lookup"><span data-stu-id="c789d-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="c789d-105">Es gibt einen impliziten lexikalischen Gültigkeitsbereich um die gesamte Methode.</span><span class="sxs-lookup"><span data-stu-id="c789d-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="c789d-106">Durch das erneute Öffnen einer Methode, die zuvor geschlossen war, werden alle zuvor definierten Symbole für diese Methode gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c789d-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="c789d-107">Es kann immer nur eine offene Methode vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="c789d-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c789d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c789d-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c789d-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="c789d-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="c789d-110">in Das Metadatentoken für die Methode, die geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c789d-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c789d-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c789d-111">Return Value</span></span>  
 <span data-ttu-id="c789d-112">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="c789d-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c789d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c789d-113">Requirements</span></span>  
 <span data-ttu-id="c789d-114">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="c789d-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c789d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c789d-115">See also</span></span>

- [<span data-ttu-id="c789d-116">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c789d-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="c789d-117">CloseMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="c789d-117">CloseMethod Method</span></span>](isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="c789d-118">OpenMethod2-Methode</span><span class="sxs-lookup"><span data-stu-id="c789d-118">OpenMethod2 Method</span></span>](isymunmanagedwriter3-openmethod2-method.md)
