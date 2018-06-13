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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 73d4cc609694610aead2a3bfaeed1f5cca5f33fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426416"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="940cd-102">ISymUnmanagedScope2::GetConstants-Methode</span><span class="sxs-lookup"><span data-stu-id="940cd-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="940cd-103">Ruft die lokalen Konstanten, die in diesem Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="940cd-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="940cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="940cd-104">Syntax</span></span>  
  
```  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="940cd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="940cd-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="940cd-106">[in] Die Länge des Puffers, der `pcConstants` -Parameter zeigt.</span><span class="sxs-lookup"><span data-stu-id="940cd-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="940cd-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe in Zeichen des Puffers benötigt, damit die Konstanten enthalten.</span><span class="sxs-lookup"><span data-stu-id="940cd-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="940cd-108">[out] Der Puffer, in dem die Konstanten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="940cd-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="940cd-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="940cd-109">Return Value</span></span>  
 <span data-ttu-id="940cd-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="940cd-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="940cd-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="940cd-111">Requirements</span></span>  
 <span data-ttu-id="940cd-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="940cd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="940cd-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="940cd-113">See Also</span></span>  
 [<span data-ttu-id="940cd-114">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="940cd-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
