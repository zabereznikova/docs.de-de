---
title: ISymUnmanagedScope::GetParent-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetParent
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetParent
helpviewer_keywords:
- GetParent method [.NET Framework debugging]
- ISymUnmanagedScope::GetParent method [.NET Framework debugging]
ms.assetid: c7963c87-6ec5-49b3-a5cd-e0fe0c43f9b4
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 68215224467170962e897964483a4ce13d7b6366
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="f2bf7-102">ISymUnmanagedScope::GetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="f2bf7-102">ISymUnmanagedScope::GetParent Method</span></span>
<span data-ttu-id="f2bf7-103">Ruft den übergeordneten Bereich dieses Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="f2bf7-103">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2bf7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2bf7-104">Syntax</span></span>  
  
```  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2bf7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2bf7-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f2bf7-106">[out] Ein Zeiger auf das zurückgegebene [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f2bf7-106">[out] A pointer to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2bf7-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f2bf7-107">Return Value</span></span>  
 <span data-ttu-id="f2bf7-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="f2bf7-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2bf7-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f2bf7-109">Requirements</span></span>  
 <span data-ttu-id="f2bf7-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f2bf7-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2bf7-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2bf7-111">See Also</span></span>  
 [<span data-ttu-id="f2bf7-112">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2bf7-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="f2bf7-113">GetChildren-Methode</span><span class="sxs-lookup"><span data-stu-id="f2bf7-113">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)
