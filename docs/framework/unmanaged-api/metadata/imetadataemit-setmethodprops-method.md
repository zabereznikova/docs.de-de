---
title: IMetaDataEmit::SetMethodProps-Methode
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
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 28ec0ba45a83ccf51cc84ee9deb2c658b9b106bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="cfa07-102">IMetaDataEmit::SetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="cfa07-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="cfa07-103">Legt fest oder aktualisiert das Feature "" an der angegebenen relativen virtuellen Adresse, einer Methode, die durch einen vorherigen Aufruf definierten gespeicherte [DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="cfa07-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfa07-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cfa07-104">Syntax</span></span>  
  
```  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cfa07-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cfa07-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="cfa07-106">[in] Das Token für die Methode geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cfa07-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="cfa07-107">[in] Die Attribute des Elements.</span><span class="sxs-lookup"><span data-stu-id="cfa07-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="cfa07-108">[in] Die Adresse des Codes.</span><span class="sxs-lookup"><span data-stu-id="cfa07-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="cfa07-109">[in] Die Implementierungsflags für die Methode.</span><span class="sxs-lookup"><span data-stu-id="cfa07-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfa07-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cfa07-110">Requirements</span></span>  
 <span data-ttu-id="cfa07-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfa07-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfa07-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cfa07-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cfa07-113">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="cfa07-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cfa07-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfa07-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa07-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfa07-115">See Also</span></span>  
 [<span data-ttu-id="cfa07-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfa07-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="cfa07-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfa07-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
