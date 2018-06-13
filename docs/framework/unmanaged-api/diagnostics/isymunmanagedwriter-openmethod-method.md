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
ms.openlocfilehash: bc41acd6a4f2ef2557d3b39523c5e398c887c454
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427907"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="e8add-102">ISymUnmanagedWriter::OpenMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="e8add-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="e8add-103">Öffnet eine Methode, die in der, die Symbolinformationen ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e8add-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="e8add-104">Die angegebene Methode wird die aktuelle Methode für Aufrufe zum Definieren der Sequenzpunkte, Parameter und lexikalischen Gültigkeitsbereiche.</span><span class="sxs-lookup"><span data-stu-id="e8add-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="e8add-105">Es gibt ein impliziter Lexikalischer Gültigkeitsbereich die gesamte Methode.</span><span class="sxs-lookup"><span data-stu-id="e8add-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="e8add-106">Durch erneutes Öffnen einer Methode, die zuvor geschlossen wurde, löscht alle zuvor definierten Symbole für diese Methode.</span><span class="sxs-lookup"><span data-stu-id="e8add-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="e8add-107">Es können nur eine open-Methode zu einem Zeitpunkt vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="e8add-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8add-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8add-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8add-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="e8add-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="e8add-110">[in] Das Metadatentoken für die Methode, die geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="e8add-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8add-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e8add-111">Return Value</span></span>  
 <span data-ttu-id="e8add-112">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e8add-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8add-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8add-113">Requirements</span></span>  
 <span data-ttu-id="e8add-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e8add-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8add-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8add-115">See Also</span></span>  
 [<span data-ttu-id="e8add-116">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8add-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="e8add-117">CloseMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="e8add-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)  
 [<span data-ttu-id="e8add-118">OpenMethod2-Methode</span><span class="sxs-lookup"><span data-stu-id="e8add-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
