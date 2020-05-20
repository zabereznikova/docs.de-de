---
title: ISymUnmanagedScope::GetLocalCount-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
ms.openlocfilehash: 9ffba23e3821c48c9b0708e4b6b617db4ddc5959
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83611262"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="a7818-102">ISymUnmanagedScope::GetLocalCount-Methode</span><span class="sxs-lookup"><span data-stu-id="a7818-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="a7818-103">Ruft die Anzahl der in diesem Bereich definierten lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="a7818-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7818-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7818-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7818-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7818-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a7818-106">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Anzahl der lokalen Variablen empfängt.</span><span class="sxs-lookup"><span data-stu-id="a7818-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7818-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a7818-107">Return Value</span></span>  
 <span data-ttu-id="a7818-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a7818-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7818-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7818-109">Requirements</span></span>  
 <span data-ttu-id="a7818-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="a7818-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7818-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7818-111">See also</span></span>

- [<span data-ttu-id="a7818-112">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7818-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
