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
ms.openlocfilehash: 45268929b6e9ad6ac6423aa0fa2b7b5022bc9179
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176616"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="f6cd3-102">ISymUnmanagedScope2::GetConstants-Methode</span><span class="sxs-lookup"><span data-stu-id="f6cd3-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="f6cd3-103">Ruft die in diesem Bereich definierten lokalen Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="f6cd3-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6cd3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6cd3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6cd3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6cd3-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="f6cd3-106">[in] Die Länge des Puffers, auf den der `pcConstants` Parameter zeigt.</span><span class="sxs-lookup"><span data-stu-id="f6cd3-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="f6cd3-107">[out] Ein Zeiger auf `ULONG32` eine, der die Größe des Puffers in Zeichen empfängt, der erforderlich ist, um die Konstanten zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="f6cd3-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="f6cd3-108">[out] Der Puffer, der die Konstanten speichert.</span><span class="sxs-lookup"><span data-stu-id="f6cd3-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6cd3-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f6cd3-109">Return Value</span></span>  
 <span data-ttu-id="f6cd3-110">S_OK, ob die Methode erfolgreich ist. andernfalls E_FAIL oder einem anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="f6cd3-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6cd3-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f6cd3-111">Requirements</span></span>  
 <span data-ttu-id="f6cd3-112">**Kopfzeile:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f6cd3-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6cd3-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6cd3-113">See also</span></span>

- [<span data-ttu-id="f6cd3-114">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6cd3-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
