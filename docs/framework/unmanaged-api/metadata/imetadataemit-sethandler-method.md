---
title: IMetaDataEmit::SetHandler-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetHandler
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d4a56db43f932a155b4251f019e39dc5640eb014
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="5dd2b-102">IMetaDataEmit::SetHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="5dd2b-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="5dd2b-103">Legt die Methode, die auf die verwiesen wird durch das angegebene `IUnknown` Zeiger als eines Rückrufs für token neue Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="5dd2b-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dd2b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5dd2b-104">Syntax</span></span>  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5dd2b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5dd2b-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="5dd2b-106">[in] Der Handler registriert.</span><span class="sxs-lookup"><span data-stu-id="5dd2b-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5dd2b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5dd2b-107">Remarks</span></span>  
 <span data-ttu-id="5dd2b-108">Das Metadatenmodul sendet Benachrichtigung mithilfe der Methode, die von bereitgestellte `SetHandler`, Compiler, die Datensätze nicht auf optimierte Weise generieren und die gespeicherte Datensätze optimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="5dd2b-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="5dd2b-109">Wenn die Rückrufmethode nicht über die bereitgestellten `SetHandler`, keine Optimierung erfolgt auf speichern es sei denn, in denen mehrere importtypen Bereiche zusammengeführt wurden mit `IMapToken` auf "Zusammenführen" für die einzelnen Bereiche.</span><span class="sxs-lookup"><span data-stu-id="5dd2b-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dd2b-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5dd2b-110">Requirements</span></span>  
 <span data-ttu-id="5dd2b-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dd2b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dd2b-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5dd2b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5dd2b-113">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="5dd2b-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5dd2b-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dd2b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd2b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5dd2b-115">See Also</span></span>  
 [<span data-ttu-id="5dd2b-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5dd2b-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="5dd2b-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5dd2b-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
