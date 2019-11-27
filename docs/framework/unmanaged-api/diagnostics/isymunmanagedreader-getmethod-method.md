---
title: ISymUnmanagedReader::GetMethod-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type:
- apiref
ms.openlocfilehash: 9407942b81c5318509f2b026fa5db1cdd163e02d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448280"
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="dd821-102">ISymUnmanagedReader::GetMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="dd821-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="dd821-103">Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="dd821-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd821-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd821-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd821-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dd821-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="dd821-106">in Das Methoden Token.</span><span class="sxs-lookup"><span data-stu-id="dd821-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="dd821-107">vorgenommen Ein Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="dd821-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd821-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dd821-108">Return Value</span></span>  
 <span data-ttu-id="dd821-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="dd821-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd821-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="dd821-110">Requirements</span></span>  
 <span data-ttu-id="dd821-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="dd821-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd821-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd821-112">See also</span></span>

- [<span data-ttu-id="dd821-113">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd821-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
