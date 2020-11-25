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
ms.openlocfilehash: 68d20c33c5ccd554554cae57ee55f6f51d5d980c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733307"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="c7b57-102">ISymUnmanagedVariable::GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="c7b57-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>

<span data-ttu-id="c7b57-103">Ruft den Start Offset dieser Variablen in ihrem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="c7b57-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="c7b57-104">Wenn dies eine lokale Variable innerhalb eines Bereichs ist, fällt der Start Offset in die für den Bereich definierten Offsets.</span><span class="sxs-lookup"><span data-stu-id="c7b57-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7b57-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7b57-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7b57-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7b57-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="c7b57-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der den Start Offset empfängt.</span><span class="sxs-lookup"><span data-stu-id="c7b57-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7b57-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c7b57-108">Return Value</span></span>  

 <span data-ttu-id="c7b57-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="c7b57-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7b57-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c7b57-110">Requirements</span></span>  

 <span data-ttu-id="c7b57-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="c7b57-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7b57-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c7b57-112">See also</span></span>

- [<span data-ttu-id="c7b57-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7b57-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="c7b57-114">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="c7b57-114">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)
