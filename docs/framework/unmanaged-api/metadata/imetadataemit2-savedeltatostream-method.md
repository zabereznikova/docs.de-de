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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 270fdecb6afbf252b7d0531cab0f18dded44298d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777120"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="2161c-102">IMetaDataEmit2::SaveDeltaToStream-Methode</span><span class="sxs-lookup"><span data-stu-id="2161c-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="2161c-103">Speichert Änderungen aus der aktuellen Sitzung mit bearbeiten und fortfahren, in den angegebenen Stream.</span><span class="sxs-lookup"><span data-stu-id="2161c-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2161c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2161c-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2161c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2161c-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="2161c-106">[in] Ein Schnittstellenzeiger auf den schreibbaren Datenstrom an, um Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2161c-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="2161c-107">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="2161c-107">[in] Reserved.</span></span> <span data-ttu-id="2161c-108">Dieser Wert muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="2161c-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2161c-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2161c-109">Requirements</span></span>  
 <span data-ttu-id="2161c-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2161c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2161c-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2161c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2161c-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2161c-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2161c-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2161c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2161c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2161c-114">See also</span></span>

- [<span data-ttu-id="2161c-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2161c-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="2161c-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2161c-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
