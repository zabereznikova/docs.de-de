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
ms.openlocfilehash: f2996349fd2bf1765a3de5b67d3296a25b1eaa5e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610365"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="4f312-102">ISymUnmanagedVariable::GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="4f312-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="4f312-103">Ruft den Start Offset dieser Variablen in ihrem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="4f312-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="4f312-104">Wenn dies eine lokale Variable innerhalb eines Bereichs ist, fällt der Start Offset in die für den Bereich definierten Offsets.</span><span class="sxs-lookup"><span data-stu-id="4f312-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f312-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f312-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f312-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4f312-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4f312-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der den Start Offset empfängt.</span><span class="sxs-lookup"><span data-stu-id="4f312-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f312-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4f312-108">Return Value</span></span>  
 <span data-ttu-id="4f312-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="4f312-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f312-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f312-110">Requirements</span></span>  
 <span data-ttu-id="4f312-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="4f312-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f312-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f312-112">See also</span></span>

- [<span data-ttu-id="4f312-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f312-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="4f312-114">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="4f312-114">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)
