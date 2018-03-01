---
title: ISymUnmanagedDocumentWriter::SetCheckSum-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedDocumentWriter.SetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0e4f653ab7b2a1341af8917c6932ea8bdfd64d83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="9a0ab-102">ISymUnmanagedDocumentWriter::SetCheckSum-Methode</span><span class="sxs-lookup"><span data-stu-id="9a0ab-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="9a0ab-103">Legt Prüfsummeninformationen fest.</span><span class="sxs-lookup"><span data-stu-id="9a0ab-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a0ab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a0ab-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a0ab-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a0ab-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="9a0ab-106">[in] Die GUID, die die Algorithmus-ID darstellt.</span><span class="sxs-lookup"><span data-stu-id="9a0ab-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="9a0ab-107">[in] Ein `ULONG32` gibt, die die Größe in Bytes, der die `checkSum` Puffer.</span><span class="sxs-lookup"><span data-stu-id="9a0ab-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="9a0ab-108">[in] Der Puffer, in dem die Prüfsummeninformationen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9a0ab-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a0ab-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9a0ab-109">Return Value</span></span>  
 <span data-ttu-id="9a0ab-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9a0ab-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a0ab-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a0ab-111">Requirements</span></span>  
 <span data-ttu-id="9a0ab-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9a0ab-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a0ab-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a0ab-113">See Also</span></span>  
 [<span data-ttu-id="9a0ab-114">ISymUnmanagedDocumentWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a0ab-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
