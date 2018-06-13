---
title: ISymUnmanagedScope::GetMethod-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ebef54baf4e560b364845a521e4b4444ed359395
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426119"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="17ac9-102">ISymUnmanagedScope::GetMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="17ac9-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="17ac9-103">Ruft die Methode ab, die dieser Bereich enthält.</span><span class="sxs-lookup"><span data-stu-id="17ac9-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17ac9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17ac9-104">Syntax</span></span>  
  
```  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17ac9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="17ac9-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="17ac9-106">[out] Ein Zeiger auf das zurückgegebene [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="17ac9-106">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17ac9-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17ac9-107">Return Value</span></span>  
 <span data-ttu-id="17ac9-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="17ac9-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17ac9-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17ac9-109">Requirements</span></span>  
 <span data-ttu-id="17ac9-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="17ac9-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17ac9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17ac9-111">See Also</span></span>  
 [<span data-ttu-id="17ac9-112">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17ac9-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
