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
ms.openlocfilehash: e64d644b511f7c3249c48b9642bfd3163142af3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722010"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="7fc86-102">IMetaDataEmit::Merge-Methode</span><span class="sxs-lookup"><span data-stu-id="7fc86-102">IMetaDataEmit::Merge Method</span></span>

<span data-ttu-id="7fc86-103">Fügt der Liste der zusammen zuführenden Bereiche den angegebenen importierten Bereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="7fc86-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fc86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7fc86-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fc86-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7fc86-105">Parameters</span></span>  

 `pImport`  
 <span data-ttu-id="7fc86-106">in Ein Zeiger auf ein [IMetaDataImport](imetadataimport-interface.md) -Objekt, das den importierten Bereich identifiziert, der zusammengeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7fc86-106">[in] A pointer to an [IMetaDataImport](imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="7fc86-107">in Ein Zeiger auf ein [IMapToken](imaptoken-interface.md) -Objekt, das die erneute Zuordnung des Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="7fc86-107">[in] A pointer to an [IMapToken](imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="7fc86-108">in Ein Zeiger auf ein [IUnknown](/cpp/atl/iunknown) -Objekt, das die Fehler angibt.</span><span class="sxs-lookup"><span data-stu-id="7fc86-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fc86-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7fc86-109">Remarks</span></span>  

 <span data-ttu-id="7fc86-110">Aufrufen von [IMetaDataEmit:: MergeEnd](imetadataemit-mergeend-method.md) , um die Zusammenführung von Metadaten in einem einzelnen Bereich zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="7fc86-110">Call [IMetaDataEmit::MergeEnd](imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fc86-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7fc86-111">Requirements</span></span>  

 <span data-ttu-id="7fc86-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fc86-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fc86-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7fc86-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7fc86-114">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="7fc86-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7fc86-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fc86-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fc86-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7fc86-116">See also</span></span>

- [<span data-ttu-id="7fc86-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7fc86-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7fc86-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7fc86-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
