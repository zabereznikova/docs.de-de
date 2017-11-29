---
title: ISymUnmanagedWriter::OpenMethod-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 61d63fb96635e34e07c3997c1aad838e67c70742
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="75fff-102">ISymUnmanagedWriter::OpenMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="75fff-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="75fff-103">Öffnet eine Methode, die in der, die Symbolinformationen ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="75fff-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="75fff-104">Die angegebene Methode wird die aktuelle Methode für Aufrufe zum Definieren der Sequenzpunkte, Parameter und lexikalischen Gültigkeitsbereiche.</span><span class="sxs-lookup"><span data-stu-id="75fff-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="75fff-105">Es gibt ein impliziter Lexikalischer Gültigkeitsbereich die gesamte Methode.</span><span class="sxs-lookup"><span data-stu-id="75fff-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="75fff-106">Durch erneutes Öffnen einer Methode, die zuvor geschlossen wurde, löscht alle zuvor definierten Symbole für diese Methode.</span><span class="sxs-lookup"><span data-stu-id="75fff-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="75fff-107">Es können nur eine open-Methode zu einem Zeitpunkt vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="75fff-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75fff-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="75fff-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75fff-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="75fff-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="75fff-110">[in] Das Metadatentoken für die Methode, die geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="75fff-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75fff-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="75fff-111">Return Value</span></span>  
 <span data-ttu-id="75fff-112">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="75fff-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75fff-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="75fff-113">Requirements</span></span>  
 <span data-ttu-id="75fff-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="75fff-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75fff-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75fff-115">See Also</span></span>  
 [<span data-ttu-id="75fff-116">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="75fff-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="75fff-117">CloseMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="75fff-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)  
 [<span data-ttu-id="75fff-118">OpenMethod2-Methode</span><span class="sxs-lookup"><span data-stu-id="75fff-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
