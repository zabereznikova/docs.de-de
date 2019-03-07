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
ms.openlocfilehash: c343810db3d714367f84f5394c0251b9ade0e18e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487420"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="b240c-102">ISymUnmanagedScope2::GetConstants-Methode</span><span class="sxs-lookup"><span data-stu-id="b240c-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="b240c-103">Ruft ab, die lokalen Konstanten, die innerhalb dieses Bereichs definiert.</span><span class="sxs-lookup"><span data-stu-id="b240c-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b240c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b240c-104">Syntax</span></span>  
  
```  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b240c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b240c-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="b240c-106">[in] Die Länge des Puffers, der die `pcConstants` -Parameter zeigt.</span><span class="sxs-lookup"><span data-stu-id="b240c-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="b240c-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe in Zeichen des Puffers erforderlich, um die Konstanten enthalten.</span><span class="sxs-lookup"><span data-stu-id="b240c-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="b240c-108">[out] Der Puffer, der die Konstanten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b240c-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b240c-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b240c-109">Return Value</span></span>  
 <span data-ttu-id="b240c-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="b240c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b240c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b240c-111">Requirements</span></span>  
 <span data-ttu-id="b240c-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b240c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b240c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b240c-113">See also</span></span>
- [<span data-ttu-id="b240c-114">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b240c-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
