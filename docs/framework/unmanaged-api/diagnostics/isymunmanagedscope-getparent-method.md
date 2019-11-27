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
ms.openlocfilehash: 512dd4055a0aad8498db6ef2241c9363aecee9c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446288"
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="27a41-102">ISymUnmanagedScope::GetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="27a41-102">ISymUnmanagedScope::GetParent Method</span></span>
<span data-ttu-id="27a41-103">Ruft den übergeordneten Gültigkeitsbereich dieses Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="27a41-103">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27a41-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27a41-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27a41-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="27a41-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="27a41-106">vorgenommen Ein Zeiger auf die zurückgegebene [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="27a41-106">[out] A pointer to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27a41-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="27a41-107">Return Value</span></span>  
 <span data-ttu-id="27a41-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="27a41-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27a41-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="27a41-109">Requirements</span></span>  
 <span data-ttu-id="27a41-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="27a41-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a41-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27a41-111">See also</span></span>

- [<span data-ttu-id="27a41-112">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27a41-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="27a41-113">GetChildren-Methode</span><span class="sxs-lookup"><span data-stu-id="27a41-113">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)
