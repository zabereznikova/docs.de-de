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
ms.openlocfilehash: 25178b5ea27aac7229ab51a167283d955b89addc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777265"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="4ac47-102">ISymUnmanagedWriter::OpenMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="4ac47-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="4ac47-103">Öffnet eine Methode, die in der, die Symbolinformationen ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4ac47-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="4ac47-104">Die angegebene Methode wird die aktuelle Methode für Aufrufe zum Definieren der Sequenzpunkte, Parameter und lexikalischen Gültigkeitsbereiche.</span><span class="sxs-lookup"><span data-stu-id="4ac47-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="4ac47-105">Es gibt ein implizite Lexikalischer Gültigkeitsbereich die gesamte Methode aus.</span><span class="sxs-lookup"><span data-stu-id="4ac47-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="4ac47-106">Öffnen eine Methode, die bereits geschlossen wurde, löscht alle zuvor definierten Symbole für diese Methode.</span><span class="sxs-lookup"><span data-stu-id="4ac47-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="4ac47-107">Es kann nur eine open-Methode zu einem Zeitpunkt vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="4ac47-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ac47-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ac47-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ac47-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="4ac47-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="4ac47-110">[in] Das Metadatentoken für die Methode, die geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="4ac47-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ac47-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4ac47-111">Return Value</span></span>  
 <span data-ttu-id="4ac47-112">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="4ac47-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ac47-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4ac47-113">Requirements</span></span>  
 <span data-ttu-id="4ac47-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4ac47-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ac47-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ac47-115">See also</span></span>

- [<span data-ttu-id="4ac47-116">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4ac47-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="4ac47-117">CloseMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="4ac47-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="4ac47-118">OpenMethod2-Methode</span><span class="sxs-lookup"><span data-stu-id="4ac47-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
