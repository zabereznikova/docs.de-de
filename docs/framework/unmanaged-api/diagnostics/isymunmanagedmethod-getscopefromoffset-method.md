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
ms.openlocfilehash: 4eefd019280f501a6ce194e5ce84388e32cc66e1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615136"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="0da20-102">ISymUnmanagedMethod::GetScopeFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="0da20-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="0da20-103">Ruft den am weitesten schließenden lexikalischen Gültigkeitsbereich innerhalb dieser Methode ab, der den angegebenen Offset einschließt.</span><span class="sxs-lookup"><span data-stu-id="0da20-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="0da20-104">Hiermit können lokale Variablen suchen gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="0da20-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da20-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0da20-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0da20-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0da20-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="0da20-107">in Ein-Wert `ULONG` , der den Offset enthält.</span><span class="sxs-lookup"><span data-stu-id="0da20-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0da20-108">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedScope](isymunmanagedscope-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0da20-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0da20-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0da20-109">Return Value</span></span>  
 <span data-ttu-id="0da20-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0da20-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0da20-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0da20-111">Requirements</span></span>  
 <span data-ttu-id="0da20-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="0da20-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0da20-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0da20-113">See also</span></span>

- [<span data-ttu-id="0da20-114">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0da20-114">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
