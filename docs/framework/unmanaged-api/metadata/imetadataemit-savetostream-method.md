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
ms.openlocfilehash: 7db27670b72a5018a03d4614b69486f67bcef155
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175680"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="0df05-102">IMetaDataEmit::SaveToStream-Methode</span><span class="sxs-lookup"><span data-stu-id="0df05-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="0df05-103">Speichert alle Metadaten im aktuellen `IStream`Bereich im angegebenen .</span><span class="sxs-lookup"><span data-stu-id="0df05-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0df05-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0df05-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0df05-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0df05-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="0df05-106">[in] Der beschreibbare Stream, in dem gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="0df05-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="0df05-107">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="0df05-107">[in] Reserved.</span></span> <span data-ttu-id="0df05-108">Muss Null sein.</span><span class="sxs-lookup"><span data-stu-id="0df05-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0df05-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0df05-109">Requirements</span></span>  
 <span data-ttu-id="0df05-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0df05-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0df05-111">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0df05-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0df05-112">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="0df05-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0df05-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0df05-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0df05-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0df05-114">See also</span></span>

- [<span data-ttu-id="0df05-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0df05-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0df05-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0df05-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
