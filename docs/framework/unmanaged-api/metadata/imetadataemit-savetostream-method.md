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
ms.openlocfilehash: 87e00a69643b6bc403188fb0fdb6f9e3f3d82115
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003876"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="da3b1-102">IMetaDataEmit::SaveToStream-Methode</span><span class="sxs-lookup"><span data-stu-id="da3b1-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="da3b1-103">Speichert alle Metadaten im aktuellen Gültigkeitsbereich in der angegebenen `IStream` .</span><span class="sxs-lookup"><span data-stu-id="da3b1-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da3b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="da3b1-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da3b1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="da3b1-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="da3b1-106">in Der beschreibbare Stream, in dem gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="da3b1-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="da3b1-107">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="da3b1-107">[in] Reserved.</span></span> <span data-ttu-id="da3b1-108">Muss Null sein.</span><span class="sxs-lookup"><span data-stu-id="da3b1-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da3b1-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="da3b1-109">Requirements</span></span>  
 <span data-ttu-id="da3b1-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da3b1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da3b1-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="da3b1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da3b1-112">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="da3b1-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da3b1-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da3b1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da3b1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da3b1-114">See also</span></span>

- [<span data-ttu-id="da3b1-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="da3b1-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="da3b1-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="da3b1-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
