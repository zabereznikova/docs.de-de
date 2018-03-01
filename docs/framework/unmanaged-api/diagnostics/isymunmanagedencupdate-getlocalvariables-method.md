---
title: ISymUnmanagedENCUpdate::GetLocalVariables-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eefd64441221a7e6e00689d6be272540f9c2423c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="992c9-102">ISymUnmanagedENCUpdate::GetLocalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="992c9-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="992c9-103">Ruft die lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="992c9-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="992c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="992c9-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="992c9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="992c9-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="992c9-106">[in] Das Metadatentoken der Methode.</span><span class="sxs-lookup"><span data-stu-id="992c9-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="992c9-107">[in] Ein `ULONG` , der angibt, dass der Größe des der `rgLocals` Parameter.</span><span class="sxs-lookup"><span data-stu-id="992c9-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="992c9-108">[out] Das zurückgegebene Array von <!--zz<xref:ISymUnmanagedVariable>--> `ISymUnmanagedVariable` Instanzen.</span><span class="sxs-lookup"><span data-stu-id="992c9-108">[out] The returned array of <!--zz<xref:ISymUnmanagedVariable>--> `ISymUnmanagedVariable`  instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="992c9-109">[out] Ein Zeiger auf eine `ULONG` , empfängt die Größe der `rgLocals` Puffer erforderlich, um die "lokal" enthalten.</span><span class="sxs-lookup"><span data-stu-id="992c9-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="992c9-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="992c9-110">Return Value</span></span>  
 <span data-ttu-id="992c9-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="992c9-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="992c9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="992c9-112">Requirements</span></span>  
 <span data-ttu-id="992c9-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="992c9-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="992c9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="992c9-114">See Also</span></span>  
 [<span data-ttu-id="992c9-115">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="992c9-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
