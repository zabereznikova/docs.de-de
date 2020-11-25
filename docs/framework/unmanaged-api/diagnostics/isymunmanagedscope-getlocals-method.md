---
title: ISymUnmanagedScope::GetLocals-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
ms.openlocfilehash: 3a2045466340f92dd8421090c74a442068e8bfaf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731409"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="07f63-102">ISymUnmanagedScope::GetLocals-Methode</span><span class="sxs-lookup"><span data-stu-id="07f63-102">ISymUnmanagedScope::GetLocals Method</span></span>

<span data-ttu-id="07f63-103">Ruft die in diesem Bereich definierten lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="07f63-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07f63-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07f63-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07f63-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="07f63-105">Parameters</span></span>  

 `cLocals`  
 <span data-ttu-id="07f63-106">in Ein-Wert `ULONG32` , der die Größe des `locals` Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="07f63-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="07f63-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der zum enthalten der lokalen Variablen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="07f63-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="07f63-108">vorgenommen Das Array, das die lokalen Variablen empfängt.</span><span class="sxs-lookup"><span data-stu-id="07f63-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07f63-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="07f63-109">Return Value</span></span>  

 <span data-ttu-id="07f63-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="07f63-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07f63-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="07f63-111">Requirements</span></span>  

 <span data-ttu-id="07f63-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="07f63-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07f63-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07f63-113">See also</span></span>

- [<span data-ttu-id="07f63-114">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07f63-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
