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
ms.openlocfilehash: 889fd4ec3332cbe80a035e13a5145421dc0ed5a9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448893"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="624c1-102">ISymUnmanagedMethod::GetSequencePointCount-Methode</span><span class="sxs-lookup"><span data-stu-id="624c1-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="624c1-103">Ruft die Anzahl von Sequenz Punkten innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="624c1-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="624c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="624c1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="624c1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="624c1-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="624c1-106">vorgenommen Ein Zeiger auf einen `ULONG32`, der die Größe des Puffers empfängt, der die Sequenz Punkte enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="624c1-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="624c1-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="624c1-107">Return Value</span></span>  
 <span data-ttu-id="624c1-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="624c1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="624c1-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="624c1-109">Requirements</span></span>  
 <span data-ttu-id="624c1-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="624c1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="624c1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="624c1-111">See also</span></span>

- [<span data-ttu-id="624c1-112">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="624c1-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
