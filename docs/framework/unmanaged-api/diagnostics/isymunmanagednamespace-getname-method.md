---
title: ISymUnmanagedNamespace::GetName-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
ms.openlocfilehash: 84b2f1226c84713483499c7ff777838058cb0f95
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615110"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="72bad-102">ISymUnmanagedNamespace::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="72bad-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="72bad-103">Ruft den Namen dieses Namespace ab.</span><span class="sxs-lookup"><span data-stu-id="72bad-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72bad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72bad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72bad-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="72bad-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="72bad-106">in Eine `ULONG32` , die die Größe des `szName` Puffers angibt.</span><span class="sxs-lookup"><span data-stu-id="72bad-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="72bad-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers in Zeichen empfängt, der den Namespace Namen enthalten muss, einschließlich der NULL-Beendigung.</span><span class="sxs-lookup"><span data-stu-id="72bad-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="72bad-108">vorgenommen Ein Zeiger auf einen Puffer, der den Namespace Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="72bad-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72bad-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="72bad-109">Return Value</span></span>  
 <span data-ttu-id="72bad-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="72bad-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72bad-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="72bad-111">Requirements</span></span>  
 <span data-ttu-id="72bad-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="72bad-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72bad-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72bad-113">See also</span></span>

- [<span data-ttu-id="72bad-114">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="72bad-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
