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
ms.openlocfilehash: df42e58a9bb3bf00b3fa4df45086dc2219658e25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725845"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="8edd5-102">ISymUnmanagedScope2::GetConstants-Methode</span><span class="sxs-lookup"><span data-stu-id="8edd5-102">ISymUnmanagedScope2::GetConstants Method</span></span>

<span data-ttu-id="8edd5-103">Ruft die in diesem Bereich definierten lokalen Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="8edd5-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8edd5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8edd5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8edd5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8edd5-105">Parameters</span></span>  

 `cConstants`  
 <span data-ttu-id="8edd5-106">in Die Länge des Puffers, auf den der- `pcConstants` Parameter verweist.</span><span class="sxs-lookup"><span data-stu-id="8edd5-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="8edd5-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers in Zeichen empfängt, der zum enthalten der Konstanten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8edd5-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="8edd5-108">vorgenommen Der Puffer, in dem die Konstanten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="8edd5-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8edd5-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8edd5-109">Return Value</span></span>  

 <span data-ttu-id="8edd5-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8edd5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8edd5-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8edd5-111">Requirements</span></span>  

 <span data-ttu-id="8edd5-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="8edd5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8edd5-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8edd5-113">See also</span></span>

- [<span data-ttu-id="8edd5-114">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8edd5-114">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
