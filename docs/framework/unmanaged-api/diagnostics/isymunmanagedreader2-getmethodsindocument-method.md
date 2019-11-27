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
ms.openlocfilehash: 70c1d87ae32fb70f8d9f6e32b527394022459526
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446432"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="43c3e-102">ISymUnmanagedReader2::GetMethodsInDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="43c3e-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="43c3e-103">Ruft jede Methode ab, die im angegebenen Dokument über Zeilen Informationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="43c3e-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c3e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43c3e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43c3e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="43c3e-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="43c3e-106">in Ein Zeiger auf das Dokument.</span><span class="sxs-lookup"><span data-stu-id="43c3e-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="43c3e-107">in Ein-`ULONG32`, der die Größe des `pRetVal` Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="43c3e-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="43c3e-108">vorgenommen Ein Zeiger auf einen `ULONG32`, der die Größe des Puffers empfängt, der zum enthalten der Methoden erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="43c3e-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="43c3e-109">vorgenommen Ein Zeiger auf den Puffer, der die Methoden empfängt.</span><span class="sxs-lookup"><span data-stu-id="43c3e-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43c3e-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="43c3e-110">Return Value</span></span>  
 <span data-ttu-id="43c3e-111">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="43c3e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43c3e-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="43c3e-112">Requirements</span></span>  
 <span data-ttu-id="43c3e-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="43c3e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c3e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43c3e-114">See also</span></span>

- [<span data-ttu-id="43c3e-115">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43c3e-115">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
