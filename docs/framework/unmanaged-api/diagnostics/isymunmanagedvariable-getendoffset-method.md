---
title: ISymUnmanagedVariable::GetEndOffset-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 325db05cc322d85e836ca9ba62b6a169e8965241
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766356"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="ccc51-102">ISymUnmanagedVariable::GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="ccc51-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="ccc51-103">Ruft den Endoffset des dieser Variablen in seinem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="ccc51-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="ccc51-104">Wenn dies eine lokale Variable innerhalb eines Bereichs ist, fällt der Endoffset innerhalb der Offsets für den Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="ccc51-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccc51-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ccc51-105">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccc51-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ccc51-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ccc51-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt den Endoffset.</span><span class="sxs-lookup"><span data-stu-id="ccc51-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccc51-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ccc51-108">Return Value</span></span>  
 <span data-ttu-id="ccc51-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ccc51-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccc51-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ccc51-110">Requirements</span></span>  
 <span data-ttu-id="ccc51-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ccc51-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc51-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccc51-112">See also</span></span>

- [<span data-ttu-id="ccc51-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccc51-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="ccc51-114">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="ccc51-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
