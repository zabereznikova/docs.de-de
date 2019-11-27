---
title: IMetaDataEmit::SaveToStream-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
ms.openlocfilehash: 23f6186b2561cbcd52db767616d986084f33860b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435928"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="41e8c-102">IMetaDataEmit::SaveToStream-Methode</span><span class="sxs-lookup"><span data-stu-id="41e8c-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="41e8c-103">Speichert alle Metadaten im aktuellen Gültigkeitsbereich in der angegebenen `IStream`.</span><span class="sxs-lookup"><span data-stu-id="41e8c-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41e8c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41e8c-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41e8c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="41e8c-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="41e8c-106">in Der beschreibbare Stream, in dem gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="41e8c-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="41e8c-107">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="41e8c-107">[in] Reserved.</span></span> <span data-ttu-id="41e8c-108">Muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="41e8c-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41e8c-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="41e8c-109">Requirements</span></span>  
 <span data-ttu-id="41e8c-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41e8c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41e8c-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="41e8c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41e8c-112">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="41e8c-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="41e8c-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41e8c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e8c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41e8c-114">See also</span></span>

- [<span data-ttu-id="41e8c-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41e8c-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="41e8c-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41e8c-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
