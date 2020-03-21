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
ms.openlocfilehash: 9662a14b4ea97aed16968083489324d46c38dda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177509"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="aa2c3-102">IMetaDataEmit::SetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="aa2c3-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="aa2c3-103">Legt das Feature einer Methode fest, die an der angegebenen relativen virtuellen Adresse gespeichert ist, und wird von einer Methode, die durch einen vorherigen Aufruf von [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="aa2c3-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa2c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa2c3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodProps (
    [in]  mdMethodDef md,
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,
    [in]  DWORD       dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa2c3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa2c3-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="aa2c3-106">[in] Das Token für die zu ändernde Methode.</span><span class="sxs-lookup"><span data-stu-id="aa2c3-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="aa2c3-107">[in] Die Memberattribute.</span><span class="sxs-lookup"><span data-stu-id="aa2c3-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="aa2c3-108">[in] Die Adresse des Codes.</span><span class="sxs-lookup"><span data-stu-id="aa2c3-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="aa2c3-109">[in] Die Implementierungsflags für die Methode.</span><span class="sxs-lookup"><span data-stu-id="aa2c3-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa2c3-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="aa2c3-110">Requirements</span></span>  
 <span data-ttu-id="aa2c3-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa2c3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa2c3-112">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aa2c3-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa2c3-113">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="aa2c3-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa2c3-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa2c3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa2c3-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa2c3-115">See also</span></span>

- [<span data-ttu-id="aa2c3-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa2c3-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="aa2c3-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa2c3-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
