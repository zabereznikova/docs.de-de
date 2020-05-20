---
title: ISymUnmanagedScope::GetParent-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetParent
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetParent
helpviewer_keywords:
- GetParent method [.NET Framework debugging]
- ISymUnmanagedScope::GetParent method [.NET Framework debugging]
ms.assetid: c7963c87-6ec5-49b3-a5cd-e0fe0c43f9b4
topic_type:
- apiref
ms.openlocfilehash: 95ae081d61200e4fd020609a4d23783f265d2cc6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615357"
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="4254c-102">ISymUnmanagedScope::GetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="4254c-102">ISymUnmanagedScope::GetParent Method</span></span>
<span data-ttu-id="4254c-103">Ruft den übergeordneten Gültigkeitsbereich dieses Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="4254c-103">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4254c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4254c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4254c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4254c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4254c-106">vorgenommen Ein Zeiger auf die zurückgegebene [ISymUnmanagedScope](isymunmanagedscope-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4254c-106">[out] A pointer to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4254c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4254c-107">Return Value</span></span>  
 <span data-ttu-id="4254c-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="4254c-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4254c-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4254c-109">Requirements</span></span>  
 <span data-ttu-id="4254c-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="4254c-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4254c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4254c-111">See also</span></span>

- [<span data-ttu-id="4254c-112">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4254c-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="4254c-113">GetChildren-Methode</span><span class="sxs-lookup"><span data-stu-id="4254c-113">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)
