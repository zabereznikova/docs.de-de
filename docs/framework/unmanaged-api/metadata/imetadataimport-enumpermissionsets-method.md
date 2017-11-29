---
title: IMetaDataImport::EnumPermissionSets-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumPermissionSets
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 031e97ad1b8180a64bc789ae52e141932d600782
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="fd7a5-102">IMetaDataImport::EnumPermissionSets-Methode</span><span class="sxs-lookup"><span data-stu-id="fd7a5-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="fd7a5-103">Zählt Berechtigungen für die Objekte in einem angegebenen Metadatenbereich auf.</span><span class="sxs-lookup"><span data-stu-id="fd7a5-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd7a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd7a5-104">Syntax</span></span>  
  
```  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd7a5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd7a5-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fd7a5-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="fd7a5-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="fd7a5-107">Dies muss für den ersten Aufruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="fd7a5-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="fd7a5-108">[in] Ein Metadatentoken, das schränkt den Bereich der Suche oder NULL, um den größtmöglichen Bereich zu suchen.</span><span class="sxs-lookup"><span data-stu-id="fd7a5-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="fd7a5-109">[in] Flags zur Darstellung der <xref:System.Security.Permissions.SecurityAction> in aufzunehmenden Werte `rPermission`, oder 0 (null), um alle Aktionen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="fd7a5-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="fd7a5-110">[out] Das Array zum Speichern der Berechtigung-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fd7a5-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fd7a5-111">[in] Die maximale Größe des `rPermission`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="fd7a5-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="fd7a5-112">[out] Die Anzahl der Permission-Token im zurückgegebenen `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="fd7a5-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd7a5-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fd7a5-113">Return Value</span></span>  
  
|<span data-ttu-id="fd7a5-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd7a5-114">HRESULT</span></span>|<span data-ttu-id="fd7a5-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd7a5-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fd7a5-116">`EnumPermissionSets`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fd7a5-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fd7a5-117">Es sind keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="fd7a5-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="fd7a5-118">In diesem Fall `pcTokens` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="fd7a5-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fd7a5-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd7a5-119">Requirements</span></span>  
 <span data-ttu-id="fd7a5-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd7a5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd7a5-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fd7a5-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd7a5-122">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fd7a5-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd7a5-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd7a5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd7a5-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd7a5-124">See Also</span></span>  
 [<span data-ttu-id="fd7a5-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd7a5-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="fd7a5-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd7a5-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
