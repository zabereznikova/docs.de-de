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
ms.openlocfilehash: 59f4d85f1d8f24724a2d7eef332ac3b3387b7c91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725858"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="a78de-102">ISymUnmanagedScope2::GetConstantCount-Methode</span><span class="sxs-lookup"><span data-stu-id="a78de-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>

<span data-ttu-id="a78de-103">Ruft die Anzahl der in diesem Bereich definierten Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="a78de-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a78de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a78de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a78de-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a78de-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="a78de-106">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers in Zeichen empfängt, der zum enthalten der Konstanten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a78de-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a78de-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a78de-107">Return Value</span></span>  

 <span data-ttu-id="a78de-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a78de-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a78de-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a78de-109">Requirements</span></span>  

 <span data-ttu-id="a78de-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="a78de-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a78de-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a78de-111">See also</span></span>

- [<span data-ttu-id="a78de-112">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a78de-112">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
