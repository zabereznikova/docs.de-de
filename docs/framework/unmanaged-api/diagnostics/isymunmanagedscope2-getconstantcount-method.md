---
title: ISymUnmanagedScope2::GetConstantCount-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
ms.openlocfilehash: 88fc6b7d6076bca42050ca87533062557e6a7b50
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610950"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="eb0c1-102">ISymUnmanagedScope2::GetConstantCount-Methode</span><span class="sxs-lookup"><span data-stu-id="eb0c1-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="eb0c1-103">Ruft die Anzahl der in diesem Bereich definierten Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="eb0c1-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb0c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb0c1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb0c1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb0c1-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="eb0c1-106">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers in Zeichen empfängt, der zum enthalten der Konstanten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="eb0c1-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb0c1-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="eb0c1-107">Return Value</span></span>  
 <span data-ttu-id="eb0c1-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="eb0c1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb0c1-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eb0c1-109">Requirements</span></span>  
 <span data-ttu-id="eb0c1-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="eb0c1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb0c1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb0c1-111">See also</span></span>

- [<span data-ttu-id="eb0c1-112">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb0c1-112">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
