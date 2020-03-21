---
title: IMetaDataEmit2::SaveDeltaToStream-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
ms.openlocfilehash: 7e8376f3a029b0e3ec51a1e7587dd14b3e7530ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177428"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="cc818-102">IMetaDataEmit2::SaveDeltaToStream-Methode</span><span class="sxs-lookup"><span data-stu-id="cc818-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="cc818-103">Speichert Änderungen aus der aktuellen Edit-and-Continue-Sitzung im angegebenen Stream.</span><span class="sxs-lookup"><span data-stu-id="cc818-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc818-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc818-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc818-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cc818-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="cc818-106">[in] Ein Schnittstellenzeiger auf den beschreibbaren Stream, in dem Änderungen gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cc818-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="cc818-107">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="cc818-107">[in] Reserved.</span></span> <span data-ttu-id="cc818-108">Dieser Wert muss null (0) sein.</span><span class="sxs-lookup"><span data-stu-id="cc818-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc818-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cc818-109">Requirements</span></span>  
 <span data-ttu-id="cc818-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc818-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc818-111">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cc818-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc818-112">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="cc818-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cc818-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc818-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc818-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc818-114">See also</span></span>

- [<span data-ttu-id="cc818-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cc818-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="cc818-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cc818-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
