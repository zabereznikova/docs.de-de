---
title: IMetaDataEmit::SetMethodProps-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7406a6118a9cca7087f913b3b2dd6f37a2d9238c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599893"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="ce3f2-102">IMetaDataEmit::SetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="ce3f2-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="ce3f2-103">Legt fest oder aktualisiert die Funktion, die an der angegebenen relativen virtuellen Adresse, einer Methode, die von einem vorherigen Aufruf von definiert gespeicherte [IMetaDataEmit:: DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="ce3f2-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce3f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce3f2-104">Syntax</span></span>  
  
```  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce3f2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ce3f2-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="ce3f2-106">[in] Das Token für die Methode, die geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ce3f2-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="ce3f2-107">[in] Die Elementattribute.</span><span class="sxs-lookup"><span data-stu-id="ce3f2-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="ce3f2-108">[in] Die Adresse des Codes.</span><span class="sxs-lookup"><span data-stu-id="ce3f2-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="ce3f2-109">[in] Die Implementierungsflags für die Methode.</span><span class="sxs-lookup"><span data-stu-id="ce3f2-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce3f2-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ce3f2-110">Requirements</span></span>  
 <span data-ttu-id="ce3f2-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce3f2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce3f2-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ce3f2-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce3f2-113">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="ce3f2-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce3f2-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce3f2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce3f2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce3f2-115">See also</span></span>
- [<span data-ttu-id="ce3f2-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce3f2-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ce3f2-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce3f2-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
