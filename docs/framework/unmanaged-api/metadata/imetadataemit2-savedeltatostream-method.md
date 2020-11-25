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
ms.openlocfilehash: dad916d74c4e754d8fd3ffb62024e49617f5de05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702016"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="53a5f-102">IMetaDataEmit2::SaveDeltaToStream-Methode</span><span class="sxs-lookup"><span data-stu-id="53a5f-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>

<span data-ttu-id="53a5f-103">Speichert Änderungen aus der aktuellen Edit-and-Continue-Sitzung in den angegebenen Stream.</span><span class="sxs-lookup"><span data-stu-id="53a5f-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53a5f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53a5f-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53a5f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="53a5f-105">Parameters</span></span>  

 `pIStream`  
 <span data-ttu-id="53a5f-106">in Ein Schnittstellen Zeiger auf den beschreibbaren Stream, in dem die Änderungen gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="53a5f-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="53a5f-107">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="53a5f-107">[in] Reserved.</span></span> <span data-ttu-id="53a5f-108">Dieser Wert muss null (0) sein.</span><span class="sxs-lookup"><span data-stu-id="53a5f-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53a5f-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="53a5f-109">Requirements</span></span>  

 <span data-ttu-id="53a5f-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53a5f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53a5f-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="53a5f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53a5f-112">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="53a5f-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="53a5f-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53a5f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53a5f-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53a5f-114">See also</span></span>

- [<span data-ttu-id="53a5f-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53a5f-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="53a5f-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53a5f-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
