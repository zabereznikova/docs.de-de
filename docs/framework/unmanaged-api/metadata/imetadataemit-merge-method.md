---
title: IMetaDataEmit::Merge-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98997bfbb7d3c9343f78438b1195222565c5b9ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444550"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="40e36-102">IMetaDataEmit::Merge-Methode</span><span class="sxs-lookup"><span data-stu-id="40e36-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="40e36-103">Die Liste der zusammenzuführenden Bereiche hinzugefügt im angegebenen importierten Bereich.</span><span class="sxs-lookup"><span data-stu-id="40e36-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40e36-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40e36-104">Syntax</span></span>  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40e36-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="40e36-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="40e36-106">[in] Ein Zeiger auf ein [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -Objekt, das die importierten Bereichs zusammengeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="40e36-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="40e36-107">[in] Ein Zeiger auf ein [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) Objekt, das das token erneut zuordnen angibt.</span><span class="sxs-lookup"><span data-stu-id="40e36-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandleer`  
 <span data-ttu-id="40e36-108">[in] Ein Zeiger auf ein <!--<<!--zzxref:IUnknown --> `IUnknown` >-->  `IUnknown` Objekt, das den Fehler angibt.</span><span class="sxs-lookup"><span data-stu-id="40e36-108">[in] A pointer to an <!--<<!--zzxref:IUnknown --> `IUnknown`>--> `IUnknown` object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40e36-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40e36-109">Remarks</span></span>  
 <span data-ttu-id="40e36-110">Rufen Sie [IMetaDataEmit:: MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) die Zusammenführung von Metadaten in den Gültigkeitsbereich einer einzelnen auslösen.</span><span class="sxs-lookup"><span data-stu-id="40e36-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40e36-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="40e36-111">Requirements</span></span>  
 <span data-ttu-id="40e36-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40e36-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40e36-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="40e36-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="40e36-114">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="40e36-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40e36-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40e36-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40e36-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40e36-116">See Also</span></span>  
 [<span data-ttu-id="40e36-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40e36-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="40e36-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40e36-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
