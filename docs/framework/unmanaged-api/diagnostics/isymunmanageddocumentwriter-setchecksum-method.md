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
ms.openlocfilehash: 06a331e24622e0a155d974ca869818a6532baa1f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615539"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="d26c9-102">ISymUnmanagedDocumentWriter::SetCheckSum-Methode</span><span class="sxs-lookup"><span data-stu-id="d26c9-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="d26c9-103">Legt Prüfsummeninformationen fest.</span><span class="sxs-lookup"><span data-stu-id="d26c9-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d26c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d26c9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d26c9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d26c9-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="d26c9-106">in Die GUID, die den Algorithmusbezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="d26c9-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="d26c9-107">in Eine `ULONG32` , die die Größe des Puffers in Bytes angibt `checkSum` .</span><span class="sxs-lookup"><span data-stu-id="d26c9-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="d26c9-108">in Der Puffer, der die Prüfsummeninformationen speichert.</span><span class="sxs-lookup"><span data-stu-id="d26c9-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d26c9-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d26c9-109">Return Value</span></span>  
 <span data-ttu-id="d26c9-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d26c9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d26c9-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d26c9-111">Requirements</span></span>  
 <span data-ttu-id="d26c9-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="d26c9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d26c9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d26c9-113">See also</span></span>

- [<span data-ttu-id="d26c9-114">ISymUnmanagedDocumentWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d26c9-114">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
