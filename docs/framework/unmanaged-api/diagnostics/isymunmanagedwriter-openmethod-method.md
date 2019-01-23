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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a5e50327e74e0b893bd5f8e6f716827f2168e37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557954"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="77953-102">ISymUnmanagedWriter::OpenMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="77953-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="77953-103">Öffnet eine Methode, die in der, die Symbolinformationen ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="77953-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="77953-104">Die angegebene Methode wird die aktuelle Methode für Aufrufe zum Definieren der Sequenzpunkte, Parameter und lexikalischen Gültigkeitsbereiche.</span><span class="sxs-lookup"><span data-stu-id="77953-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="77953-105">Es gibt ein implizite Lexikalischer Gültigkeitsbereich die gesamte Methode aus.</span><span class="sxs-lookup"><span data-stu-id="77953-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="77953-106">Öffnen eine Methode, die bereits geschlossen wurde, löscht alle zuvor definierten Symbole für diese Methode.</span><span class="sxs-lookup"><span data-stu-id="77953-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="77953-107">Es kann nur eine open-Methode zu einem Zeitpunkt vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="77953-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77953-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="77953-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77953-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="77953-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="77953-110">[in] Das Metadatentoken für die Methode, die geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="77953-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77953-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="77953-111">Return Value</span></span>  
 <span data-ttu-id="77953-112">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="77953-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77953-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="77953-113">Requirements</span></span>  
 <span data-ttu-id="77953-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="77953-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77953-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77953-115">See also</span></span>
- [<span data-ttu-id="77953-116">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77953-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="77953-117">CloseMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="77953-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="77953-118">OpenMethod2-Methode</span><span class="sxs-lookup"><span data-stu-id="77953-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
