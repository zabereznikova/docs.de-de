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
ms.openlocfilehash: dbf876a514ce106c566a168f688eb3a22d3a1ea2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449045"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="3a447-102">ISymUnmanagedDocumentWriter::SetCheckSum-Methode</span><span class="sxs-lookup"><span data-stu-id="3a447-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="3a447-103">Legt Prüfsummeninformationen fest.</span><span class="sxs-lookup"><span data-stu-id="3a447-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a447-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a447-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a447-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3a447-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="3a447-106">in Die GUID, die den Algorithmusbezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="3a447-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="3a447-107">in Ein-`ULONG32`, der die Größe des `checkSum` Puffers in Bytes angibt.</span><span class="sxs-lookup"><span data-stu-id="3a447-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="3a447-108">in Der Puffer, der die Prüfsummeninformationen speichert.</span><span class="sxs-lookup"><span data-stu-id="3a447-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a447-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3a447-109">Return Value</span></span>  
 <span data-ttu-id="3a447-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3a447-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a447-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3a447-111">Requirements</span></span>  
 <span data-ttu-id="3a447-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="3a447-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a447-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a447-113">See also</span></span>

- [<span data-ttu-id="3a447-114">ISymUnmanagedDocumentWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a447-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
