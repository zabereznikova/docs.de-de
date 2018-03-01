---
title: IMetaDataImport::GetRVA-Methode
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
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6c055afaa129b52c67cd0463a5d44afec5cde103
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="defce-102">IMetaDataImport::GetRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="defce-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="defce-103">Ruft die relative virtuelle Adresse (RVA) sowie die Implementierung der Methode oder des Felds, die durch das angegebene Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="defce-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="defce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="defce-104">Syntax</span></span>  
  
```  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="defce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="defce-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="defce-106">[in] Ein MethodDef oder FieldDef Metadatentoken, das die RVA für zurückzugebenden Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="defce-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="defce-107">Wenn das Token ein FieldDef ist, muss das Feld eine globale Variable sein.</span><span class="sxs-lookup"><span data-stu-id="defce-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="defce-108">[out] Ein Zeiger auf die relative virtuelle Adresse des vom Token dargestellten Codeobjekts.</span><span class="sxs-lookup"><span data-stu-id="defce-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="defce-109">[out] Ein Zeiger auf die Implementierungsflags für die Methode.</span><span class="sxs-lookup"><span data-stu-id="defce-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="defce-110">Dieser Wert ist eine Bitmaske aus der [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="defce-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="defce-111">Der Wert der `pdwImplFlags` gilt nur, wenn `tk` ist ein MethodDef-Token.</span><span class="sxs-lookup"><span data-stu-id="defce-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="defce-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="defce-112">Requirements</span></span>  
 <span data-ttu-id="defce-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="defce-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="defce-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="defce-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="defce-115">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="defce-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="defce-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="defce-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="defce-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="defce-117">See Also</span></span>  
 [<span data-ttu-id="defce-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="defce-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="defce-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="defce-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
