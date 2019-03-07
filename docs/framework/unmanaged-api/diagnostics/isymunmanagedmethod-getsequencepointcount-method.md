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
ms.openlocfilehash: 3cbd0765404a6c5c4a2111d8050795acd3ab72fd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499133"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="06ada-102">ISymUnmanagedMethod::GetSequencePointCount-Methode</span><span class="sxs-lookup"><span data-stu-id="06ada-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="06ada-103">Ruft die Anzahl der Sequenzpunkte innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="06ada-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ada-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06ada-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06ada-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="06ada-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="06ada-106">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die Sequenzpunkte.</span><span class="sxs-lookup"><span data-stu-id="06ada-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06ada-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="06ada-107">Return Value</span></span>  
 <span data-ttu-id="06ada-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="06ada-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06ada-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="06ada-109">Requirements</span></span>  
 <span data-ttu-id="06ada-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="06ada-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ada-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06ada-111">See also</span></span>
- [<span data-ttu-id="06ada-112">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06ada-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
