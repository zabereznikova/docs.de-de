---
title: ISymUnmanagedMethod::GetScopeFromOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
ms.openlocfilehash: cf2784ce0ac6e614e75a341660808b9fe03ada0e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699442"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="e4524-102">ISymUnmanagedMethod::GetScopeFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="e4524-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>

<span data-ttu-id="e4524-103">Ruft den am weitesten schließenden lexikalischen Gültigkeitsbereich innerhalb dieser Methode ab, der den angegebenen Offset einschließt.</span><span class="sxs-lookup"><span data-stu-id="e4524-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="e4524-104">Hiermit können lokale Variablen suchen gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="e4524-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4524-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4524-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4524-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4524-106">Parameters</span></span>  

 `offset`  
 <span data-ttu-id="e4524-107">in Ein-Wert `ULONG` , der den Offset enthält.</span><span class="sxs-lookup"><span data-stu-id="e4524-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e4524-108">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedScope](isymunmanagedscope-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e4524-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4524-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e4524-109">Return Value</span></span>  

 <span data-ttu-id="e4524-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e4524-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4524-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e4524-111">Requirements</span></span>  

 <span data-ttu-id="e4524-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="e4524-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4524-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e4524-113">See also</span></span>

- [<span data-ttu-id="e4524-114">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4524-114">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
