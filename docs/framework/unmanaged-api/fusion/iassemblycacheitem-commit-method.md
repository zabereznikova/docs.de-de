---
title: IAssemblyCacheItem::Commit-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCacheItem.Commit
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a5a25f24fd1f09ebc1cda0442e41fde9eef059d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="e032d-102">IAssemblyCacheItem::Commit-Methode</span><span class="sxs-lookup"><span data-stu-id="e032d-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="e032d-103">Führt einen Commit für den Assemblyverweis zwischengespeicherte Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="e032d-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e032d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e032d-104">Syntax</span></span>  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e032d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e032d-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="e032d-106">[in] Flags, die in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e032d-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="e032d-107">[out, optional] Ein Wert, der das Ergebnis des Vorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e032d-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e032d-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e032d-108">Requirements</span></span>  
 <span data-ttu-id="e032d-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e032d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e032d-110">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e032d-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e032d-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e032d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e032d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e032d-112">See Also</span></span>  
 [<span data-ttu-id="e032d-113">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e032d-113">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
