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
ms.openlocfilehash: 7b13ca9884516e95e0bb922efc5bc1a845344e38
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427921"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="31c96-102">ISymUnmanagedWriter::OpenMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="31c96-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="31c96-103">Öffnet eine Methode, in die Symbol Informationen ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="31c96-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="31c96-104">Die angegebene Methode wird zur aktuellen Methode für Aufrufe zum Definieren von Sequenz Punkten, Parametern und lexikalischen Gültigkeitsbereichen.</span><span class="sxs-lookup"><span data-stu-id="31c96-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="31c96-105">Es gibt einen impliziten lexikalischen Gültigkeitsbereich um die gesamte Methode.</span><span class="sxs-lookup"><span data-stu-id="31c96-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="31c96-106">Durch das erneute Öffnen einer Methode, die zuvor geschlossen war, werden alle zuvor definierten Symbole für diese Methode gelöscht.</span><span class="sxs-lookup"><span data-stu-id="31c96-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="31c96-107">Es kann immer nur eine offene Methode vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="31c96-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31c96-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="31c96-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31c96-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="31c96-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="31c96-110">in Das Metadatentoken für die Methode, die geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="31c96-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31c96-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="31c96-111">Return Value</span></span>  
 <span data-ttu-id="31c96-112">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="31c96-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31c96-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="31c96-113">Requirements</span></span>  
 <span data-ttu-id="31c96-114">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="31c96-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31c96-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31c96-115">See also</span></span>

- [<span data-ttu-id="31c96-116">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31c96-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="31c96-117">CloseMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="31c96-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="31c96-118">OpenMethod2-Methode</span><span class="sxs-lookup"><span data-stu-id="31c96-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
