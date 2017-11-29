---
title: IMetaDataEmit::SetFieldRVA-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetFieldRVA
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 463f40b933924108378f6cf9c6109e54b01ce293
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="65bf0-102">IMetaDataEmit::SetFieldRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="65bf0-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="65bf0-103">Legt einen globalen Variablenwert für die relative virtuelle Adresse des Felds auf die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="65bf0-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65bf0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65bf0-104">Syntax</span></span>  
  
```  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65bf0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="65bf0-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="65bf0-106">[in] Das Token für das Feld "Ziel".</span><span class="sxs-lookup"><span data-stu-id="65bf0-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="65bf0-107">[in] Die Adresse eines Bereichs Code- oder Datenmenge.</span><span class="sxs-lookup"><span data-stu-id="65bf0-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65bf0-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="65bf0-108">Requirements</span></span>  
 <span data-ttu-id="65bf0-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65bf0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65bf0-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="65bf0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="65bf0-111">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="65bf0-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65bf0-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65bf0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65bf0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65bf0-113">See Also</span></span>  
 [<span data-ttu-id="65bf0-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65bf0-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="65bf0-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65bf0-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
