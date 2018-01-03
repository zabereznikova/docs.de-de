---
title: ISymUnmanagedNamespace::GetName-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedNamespace.GetName
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 37b29e71a9a1185a7080f71b1621a07dd7ae41a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="7b0bf-102">ISymUnmanagedNamespace::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="7b0bf-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="7b0bf-103">Ruft den Namen dieses Namespaces ab.</span><span class="sxs-lookup"><span data-stu-id="7b0bf-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b0bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b0bf-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b0bf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7b0bf-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="7b0bf-106">[in] Ein `ULONG32` , der angibt, dass der Größe des der `szName` Puffer.</span><span class="sxs-lookup"><span data-stu-id="7b0bf-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="7b0bf-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des für den Namespacenamen, einschließlich der null-Terminierung enthalten die erforderlichen Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="7b0bf-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="7b0bf-108">[out] Ein Zeiger auf einen Puffer, der Name des Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="7b0bf-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b0bf-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7b0bf-109">Return Value</span></span>  
 <span data-ttu-id="7b0bf-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="7b0bf-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b0bf-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b0bf-111">Requirements</span></span>  
 <span data-ttu-id="7b0bf-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7b0bf-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b0bf-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b0bf-113">See Also</span></span>  
 [<span data-ttu-id="7b0bf-114">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b0bf-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
