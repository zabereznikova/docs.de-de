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
ms.openlocfilehash: 3dbe5b4e57f21970b518e4974707175f4bdcf02a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778228"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="04c3e-102">ISymUnmanagedVariable::GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="04c3e-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="04c3e-103">Ruft den Anfangsoffset dieser Variablen in seinem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="04c3e-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="04c3e-104">Wenn dies eine lokale Variable innerhalb eines Bereichs ist, greift der Anfangsoffset innerhalb der Offsets für den Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="04c3e-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04c3e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="04c3e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04c3e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="04c3e-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="04c3e-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt den Anfangsoffset.</span><span class="sxs-lookup"><span data-stu-id="04c3e-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04c3e-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="04c3e-108">Return Value</span></span>  
 <span data-ttu-id="04c3e-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="04c3e-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04c3e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="04c3e-110">Requirements</span></span>  
 <span data-ttu-id="04c3e-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="04c3e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04c3e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04c3e-112">See also</span></span>

- [<span data-ttu-id="04c3e-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04c3e-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="04c3e-114">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="04c3e-114">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)
