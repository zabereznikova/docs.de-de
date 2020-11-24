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
ms.openlocfilehash: 3f0d0e060bba832080dd8fbfab62f3115fec0aab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689640"
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="20ab6-102">ISymUnmanagedReader::GetMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="20ab6-102">ISymUnmanagedReader::GetMethod Method</span></span>

<span data-ttu-id="20ab6-103">Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="20ab6-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20ab6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20ab6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20ab6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="20ab6-105">Parameters</span></span>  

 `token`  
 <span data-ttu-id="20ab6-106">in Das Methoden Token.</span><span class="sxs-lookup"><span data-stu-id="20ab6-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="20ab6-107">vorgenommen Ein Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="20ab6-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20ab6-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="20ab6-108">Return Value</span></span>  

 <span data-ttu-id="20ab6-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="20ab6-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20ab6-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="20ab6-110">Requirements</span></span>  

 <span data-ttu-id="20ab6-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="20ab6-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20ab6-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20ab6-112">See also</span></span>

- [<span data-ttu-id="20ab6-113">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20ab6-113">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
