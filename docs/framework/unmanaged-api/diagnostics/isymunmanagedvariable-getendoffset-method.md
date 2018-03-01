---
title: ISymUnmanagedVariable::GetEndOffset-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f91c2b0f4ecb4cc901a0389d15f4d69e926cf8f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="57acd-102">ISymUnmanagedVariable::GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="57acd-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="57acd-103">Ruft den Endoffset dieser Variablen in seinem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="57acd-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="57acd-104">Wenn dies eine lokale Variable innerhalb eines Bereichs ist, fällt der Endoffset innerhalb der Offsets für den Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="57acd-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57acd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="57acd-105">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57acd-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="57acd-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="57acd-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt den Endoffset.</span><span class="sxs-lookup"><span data-stu-id="57acd-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57acd-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="57acd-108">Return Value</span></span>  
 <span data-ttu-id="57acd-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="57acd-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57acd-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="57acd-110">Requirements</span></span>  
 <span data-ttu-id="57acd-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="57acd-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57acd-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57acd-112">See Also</span></span>  
 [<span data-ttu-id="57acd-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57acd-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="57acd-114">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="57acd-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
