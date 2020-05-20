---
title: ISymUnmanagedVariable::GetAttributes-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
ms.openlocfilehash: 29869abdd39f61c6c9cb51d6b2be50fa462c5b70
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615253"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="14825-102">ISymUnmanagedVariable::GetAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="14825-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="14825-103">Ruft die Attributflags für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="14825-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14825-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14825-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14825-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="14825-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="14825-106">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Attribute empfängt.</span><span class="sxs-lookup"><span data-stu-id="14825-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="14825-107">Der zurückgegebene Wert ist einer der Werte, die in der [CorSymVarFlag](corsymvarflag-enumeration.md) -Enumeration definiert sind.</span><span class="sxs-lookup"><span data-stu-id="14825-107">The returned value will be one of the values defined in the [CorSymVarFlag](corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14825-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="14825-108">Return Value</span></span>  
 <span data-ttu-id="14825-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="14825-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14825-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="14825-110">Requirements</span></span>  
 <span data-ttu-id="14825-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="14825-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14825-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14825-112">See also</span></span>

- [<span data-ttu-id="14825-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14825-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
