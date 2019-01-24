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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e8e919c546df93a2023858c31ebc4d2dec507513
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730138"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="d4d18-102">ISymUnmanagedMethod::GetSequencePointCount-Methode</span><span class="sxs-lookup"><span data-stu-id="d4d18-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="d4d18-103">Ruft die Anzahl der Sequenzpunkte innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="d4d18-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4d18-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4d18-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4d18-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4d18-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d4d18-106">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die Sequenzpunkte.</span><span class="sxs-lookup"><span data-stu-id="d4d18-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4d18-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d4d18-107">Return Value</span></span>  
 <span data-ttu-id="d4d18-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d4d18-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4d18-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4d18-109">Requirements</span></span>  
 <span data-ttu-id="d4d18-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d4d18-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4d18-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4d18-111">See also</span></span>
- [<span data-ttu-id="d4d18-112">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4d18-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
