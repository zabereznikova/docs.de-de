---
title: ISymUnmanagedDocumentWriter::SetCheckSum-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac3daccfade4f5ae10fe2ebbf83a7a11af34b89b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196982"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="3ba3b-102">ISymUnmanagedDocumentWriter::SetCheckSum-Methode</span><span class="sxs-lookup"><span data-stu-id="3ba3b-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="3ba3b-103">Legt Prüfsummeninformationen fest.</span><span class="sxs-lookup"><span data-stu-id="3ba3b-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ba3b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ba3b-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ba3b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ba3b-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="3ba3b-106">[in] Die GUID, die den Algorithmusbezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="3ba3b-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="3ba3b-107">[in] Ein `ULONG32` , die Größe in Bytes angibt, der die `checkSum` Puffer.</span><span class="sxs-lookup"><span data-stu-id="3ba3b-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="3ba3b-108">[in] Der Puffer, in dem die Prüfsummeninformationen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3ba3b-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ba3b-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3ba3b-109">Return Value</span></span>  
 <span data-ttu-id="3ba3b-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3ba3b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ba3b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ba3b-111">Requirements</span></span>  
 <span data-ttu-id="3ba3b-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3ba3b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ba3b-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ba3b-113">See also</span></span>

- [<span data-ttu-id="3ba3b-114">ISymUnmanagedDocumentWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ba3b-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
