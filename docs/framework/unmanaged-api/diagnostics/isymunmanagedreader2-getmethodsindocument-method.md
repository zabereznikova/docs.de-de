---
title: ISymUnmanagedReader2::GetMethodsInDocument-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28b240159c36b03b2c476f56f7e6ad7b33f20649
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142342"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="fbbb5-102">ISymUnmanagedReader2::GetMethodsInDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="fbbb5-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="fbbb5-103">Ruft jede Methode, die in das angegebene Dokument über Zeileninformationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="fbbb5-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbbb5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fbbb5-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbbb5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fbbb5-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="fbbb5-106">[in] Ein Zeiger auf das Dokument.</span><span class="sxs-lookup"><span data-stu-id="fbbb5-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="fbbb5-107">[in] Ein `ULONG32` , der angibt, dass der Größe des der `pRetVal` Array.</span><span class="sxs-lookup"><span data-stu-id="fbbb5-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="fbbb5-108">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die Methoden enthalten.</span><span class="sxs-lookup"><span data-stu-id="fbbb5-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="fbbb5-109">[out] Ein Zeiger auf den Puffer, der die Methoden empfängt.</span><span class="sxs-lookup"><span data-stu-id="fbbb5-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbbb5-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fbbb5-110">Return Value</span></span>  
 <span data-ttu-id="fbbb5-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="fbbb5-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbbb5-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fbbb5-112">Requirements</span></span>  
 <span data-ttu-id="fbbb5-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fbbb5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbbb5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbbb5-114">See also</span></span>

- [<span data-ttu-id="fbbb5-115">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fbbb5-115">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
