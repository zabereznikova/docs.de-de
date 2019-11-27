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
ms.openlocfilehash: 06894f238f9fda3111d5484bb1b2add183a5abb2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448055"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="20639-102">IMetaDataEmit::Merge-Methode</span><span class="sxs-lookup"><span data-stu-id="20639-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="20639-103">Fügt der Liste der zusammen zuführenden Bereiche den angegebenen importierten Bereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="20639-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20639-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20639-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20639-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="20639-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="20639-106">in Ein Zeiger auf ein [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -Objekt, das den importierten Bereich identifiziert, der zusammengeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="20639-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="20639-107">in Ein Zeiger auf ein [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) -Objekt, das die erneute Zuordnung des Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="20639-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="20639-108">in Ein Zeiger auf ein [IUnknown](/cpp/atl/iunknown) -Objekt, das die Fehler angibt.</span><span class="sxs-lookup"><span data-stu-id="20639-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20639-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20639-109">Remarks</span></span>  
 <span data-ttu-id="20639-110">Aufrufen von [IMetaDataEmit:: MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) , um die Zusammenführung von Metadaten in einem einzelnen Bereich zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="20639-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20639-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="20639-111">Requirements</span></span>  
 <span data-ttu-id="20639-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20639-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20639-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="20639-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="20639-114">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="20639-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20639-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20639-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20639-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20639-116">See also</span></span>

- [<span data-ttu-id="20639-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20639-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="20639-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20639-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
