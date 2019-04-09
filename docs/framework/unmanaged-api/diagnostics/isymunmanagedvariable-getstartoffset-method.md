---
title: ISymUnmanagedVariable::GetStartOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6a30dff869075a201a669d1e703bc003b011fc3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196280"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="bd7cf-102">ISymUnmanagedVariable::GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="bd7cf-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="bd7cf-103">Ruft den Anfangsoffset dieser Variablen in seinem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="bd7cf-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="bd7cf-104">Wenn dies eine lokale Variable innerhalb eines Bereichs ist, greift der Anfangsoffset innerhalb der Offsets für den Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="bd7cf-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd7cf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd7cf-105">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd7cf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd7cf-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="bd7cf-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt den Anfangsoffset.</span><span class="sxs-lookup"><span data-stu-id="bd7cf-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd7cf-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bd7cf-108">Return Value</span></span>  
 <span data-ttu-id="bd7cf-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="bd7cf-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd7cf-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd7cf-110">Requirements</span></span>  
 <span data-ttu-id="bd7cf-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bd7cf-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd7cf-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd7cf-112">See also</span></span>

- [<span data-ttu-id="bd7cf-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd7cf-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="bd7cf-114">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="bd7cf-114">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)
