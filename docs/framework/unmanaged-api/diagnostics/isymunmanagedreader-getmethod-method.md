---
title: ISymUnmanagedReader::GetMethod-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7af3f56bc258ba48abba5cba4230de3ca6904ec0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="acb46-102">ISymUnmanagedReader::GetMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="acb46-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="acb46-103">Ruft ein Methodenobjekt des Symbolreaders, mit dem ein Token für die Methode ab.</span><span class="sxs-lookup"><span data-stu-id="acb46-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acb46-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="acb46-104">Syntax</span></span>  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="acb46-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="acb46-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="acb46-106">[in] Das Token der Methode.</span><span class="sxs-lookup"><span data-stu-id="acb46-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="acb46-107">[out] Ein Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="acb46-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acb46-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="acb46-108">Return Value</span></span>  
 <span data-ttu-id="acb46-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="acb46-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acb46-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="acb46-110">Requirements</span></span>  
 <span data-ttu-id="acb46-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="acb46-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb46-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acb46-112">See Also</span></span>  
 [<span data-ttu-id="acb46-113">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="acb46-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
