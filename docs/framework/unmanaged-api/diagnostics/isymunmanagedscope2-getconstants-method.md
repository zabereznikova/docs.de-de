---
title: ISymUnmanagedScope2::GetConstants-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
ms.openlocfilehash: f558d209d13fae93bd3a6f5e0e653afb91371a6a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615331"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="cd0b9-102">ISymUnmanagedScope2::GetConstants-Methode</span><span class="sxs-lookup"><span data-stu-id="cd0b9-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="cd0b9-103">Ruft die in diesem Bereich definierten lokalen Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="cd0b9-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd0b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd0b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd0b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cd0b9-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="cd0b9-106">in Die Länge des Puffers, auf den der- `pcConstants` Parameter verweist.</span><span class="sxs-lookup"><span data-stu-id="cd0b9-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="cd0b9-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers in Zeichen empfängt, der zum enthalten der Konstanten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="cd0b9-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="cd0b9-108">vorgenommen Der Puffer, in dem die Konstanten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="cd0b9-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd0b9-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cd0b9-109">Return Value</span></span>  
 <span data-ttu-id="cd0b9-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="cd0b9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd0b9-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd0b9-111">Requirements</span></span>  
 <span data-ttu-id="cd0b9-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="cd0b9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd0b9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd0b9-113">See also</span></span>

- [<span data-ttu-id="cd0b9-114">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cd0b9-114">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
