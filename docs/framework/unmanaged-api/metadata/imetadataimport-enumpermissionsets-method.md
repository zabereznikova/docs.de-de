---
title: IMetaDataImport::EnumPermissionSets-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 759b2a9a419989cfec1020b1a6662bd6f8416739
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501190"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="d9625-102">IMetaDataImport::EnumPermissionSets-Methode</span><span class="sxs-lookup"><span data-stu-id="d9625-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="d9625-103">Zählt Berechtigungen für die Objekte in einem angegebenen Metadatenbereich auf.</span><span class="sxs-lookup"><span data-stu-id="d9625-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9625-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9625-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="d9625-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d9625-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d9625-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="d9625-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="d9625-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="d9625-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="d9625-108">[in] Ein Metadatentoken, das den Bereich der Suche oder NULL, um den größtmöglichen Bereich Suchen einschränkt.</span><span class="sxs-lookup"><span data-stu-id="d9625-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="d9625-109">[in] Flags zur Darstellung der <xref:System.Security.Permissions.SecurityAction> in aufzunehmenden Werte `rPermission`, oder 0 (null), um alle Aktionen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d9625-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="d9625-110">[out] Das Array zum Speichern der Berechtigung-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d9625-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d9625-111">[in] Die maximale Größe des `rPermission`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="d9625-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d9625-112">[out] Die Anzahl der in zurückgegebenen Berechtigung Token `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="d9625-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9625-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d9625-113">Return Value</span></span>  
  
|<span data-ttu-id="d9625-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9625-114">HRESULT</span></span>|<span data-ttu-id="d9625-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9625-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d9625-116">`EnumPermissionSets` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d9625-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d9625-117">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="d9625-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="d9625-118">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="d9625-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9625-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9625-119">Requirements</span></span>  
 <span data-ttu-id="d9625-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9625-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9625-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d9625-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9625-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d9625-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9625-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9625-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9625-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9625-124">See also</span></span>
- [<span data-ttu-id="d9625-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9625-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d9625-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9625-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
