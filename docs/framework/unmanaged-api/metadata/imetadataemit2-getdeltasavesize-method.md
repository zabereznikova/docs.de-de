---
title: IMetaDataEmit2::GetDeltaSaveSize-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
ms.openlocfilehash: 36021333c1efb61e23c16782d8ad721de62c2643
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674319"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="9fa8e-102">IMetaDataEmit2::GetDeltaSaveSize-Methode</span><span class="sxs-lookup"><span data-stu-id="9fa8e-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>

<span data-ttu-id="9fa8e-103">Ruft einen Wert ab, der eine Änderung der Metadatengröße angibt, die sich aus der aktuellen Sitzung zum Bearbeiten und Fortfahren ergibt.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fa8e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fa8e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fa8e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9fa8e-105">Parameters</span></span>  

 `fSave`  
 <span data-ttu-id="9fa8e-106">in Einer der [CorSaveSize](corsavesize-enumeration.md) -Werte, der den gewünschten Genauigkeits Grad angibt.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-106">[in] One of the [CorSaveSize](corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="9fa8e-107">Bei der .NET Framework-Version 2,0 wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="9fa8e-108">vorgenommen Die Änderung der Größe der Metadaten.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fa8e-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9fa8e-109">Requirements</span></span>  

 <span data-ttu-id="9fa8e-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fa8e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fa8e-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9fa8e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9fa8e-112">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9fa8e-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fa8e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fa8e-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9fa8e-114">See also</span></span>

- [<span data-ttu-id="9fa8e-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9fa8e-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="9fa8e-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9fa8e-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
