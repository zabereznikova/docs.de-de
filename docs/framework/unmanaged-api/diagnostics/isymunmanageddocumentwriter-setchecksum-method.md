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
ms.openlocfilehash: 3b9b77b94e466a4aab4a575501ac6922293b3410
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424143"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="3fc6d-102">ISymUnmanagedDocumentWriter::SetCheckSum-Methode</span><span class="sxs-lookup"><span data-stu-id="3fc6d-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="3fc6d-103">Legt Prüfsummeninformationen fest.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fc6d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3fc6d-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fc6d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3fc6d-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="3fc6d-106">[in] Die GUID, die die Algorithmus-ID darstellt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="3fc6d-107">[in] Ein `ULONG32` gibt, die die Größe in Bytes, der die `checkSum` Puffer.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="3fc6d-108">[in] Der Puffer, in dem die Prüfsummeninformationen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fc6d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3fc6d-109">Return Value</span></span>  
 <span data-ttu-id="3fc6d-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fc6d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3fc6d-111">Requirements</span></span>  
 <span data-ttu-id="3fc6d-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3fc6d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc6d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fc6d-113">See Also</span></span>  
 [<span data-ttu-id="3fc6d-114">ISymUnmanagedDocumentWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3fc6d-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
