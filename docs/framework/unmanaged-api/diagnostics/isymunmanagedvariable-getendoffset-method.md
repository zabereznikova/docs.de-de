---
title: ISymUnmanagedVariable::GetEndOffset-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetEndOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b7a2dac8425cd852c6c17ee1674710f6798d3b1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="a0e9d-102">ISymUnmanagedVariable::GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="a0e9d-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="a0e9d-103">Ruft den Endoffset dieser Variablen in seinem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="a0e9d-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="a0e9d-104">Wenn dies eine lokale Variable innerhalb eines Bereichs ist, fällt der Endoffset innerhalb der Offsets für den Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="a0e9d-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0e9d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0e9d-105">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0e9d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0e9d-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a0e9d-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt den Endoffset.</span><span class="sxs-lookup"><span data-stu-id="a0e9d-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0e9d-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a0e9d-108">Return Value</span></span>  
 <span data-ttu-id="a0e9d-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a0e9d-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0e9d-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0e9d-110">Requirements</span></span>  
 <span data-ttu-id="a0e9d-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a0e9d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0e9d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0e9d-112">See Also</span></span>  
 [<span data-ttu-id="a0e9d-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0e9d-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="a0e9d-114">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="a0e9d-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
