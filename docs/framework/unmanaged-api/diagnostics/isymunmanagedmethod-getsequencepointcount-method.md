---
title: ISymUnmanagedMethod::GetSequencePointCount-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePointCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePointCount
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePointCount method [.NET Framework debugging]
- GetSequencePointCount method [.NET Framework debugging]
ms.assetid: 836133e8-6108-4b9b-b0a9-bce4e08dccda
topic_type:
- apiref
ms.openlocfilehash: 44472c7beff72d24853b7fb9865071a9b15ef0e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699429"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="6b191-102">ISymUnmanagedMethod::GetSequencePointCount-Methode</span><span class="sxs-lookup"><span data-stu-id="6b191-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>

<span data-ttu-id="6b191-103">Ruft die Anzahl von Sequenz Punkten innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="6b191-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b191-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b191-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b191-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b191-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="6b191-106">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der die Sequenz Punkte enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="6b191-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b191-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6b191-107">Return Value</span></span>  

 <span data-ttu-id="6b191-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="6b191-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b191-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6b191-109">Requirements</span></span>  

 <span data-ttu-id="6b191-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="6b191-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b191-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b191-111">See also</span></span>

- [<span data-ttu-id="6b191-112">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b191-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
