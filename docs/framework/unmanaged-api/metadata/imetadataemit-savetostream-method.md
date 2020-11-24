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
ms.openlocfilehash: 3f8da08b96c47c90ecccae28dd1662a7abffaf1d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688561"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="b9f23-102">IMetaDataEmit::SaveToStream-Methode</span><span class="sxs-lookup"><span data-stu-id="b9f23-102">IMetaDataEmit::SaveToStream Method</span></span>

<span data-ttu-id="b9f23-103">Speichert alle Metadaten im aktuellen Gültigkeitsbereich in der angegebenen `IStream` .</span><span class="sxs-lookup"><span data-stu-id="b9f23-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9f23-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9f23-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9f23-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b9f23-105">Parameters</span></span>  

 `pIStream`  
 <span data-ttu-id="b9f23-106">in Der beschreibbare Stream, in dem gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9f23-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="b9f23-107">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="b9f23-107">[in] Reserved.</span></span> <span data-ttu-id="b9f23-108">Muss Null sein.</span><span class="sxs-lookup"><span data-stu-id="b9f23-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9f23-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b9f23-109">Requirements</span></span>  

 <span data-ttu-id="b9f23-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9f23-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9f23-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b9f23-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9f23-112">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9f23-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9f23-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9f23-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f23-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b9f23-114">See also</span></span>

- [<span data-ttu-id="b9f23-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9f23-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b9f23-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9f23-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
