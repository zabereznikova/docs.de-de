---
title: IMetaDataEmit::Save-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
ms.openlocfilehash: afd60cdf566bea459816ee890d44cc09258de516
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435947"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="cf507-102">IMetaDataEmit::Save-Methode</span><span class="sxs-lookup"><span data-stu-id="cf507-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="cf507-103">Speichert alle Metadaten im aktuellen Gültigkeitsbereich in der Datei an der angegebenen Adresse.</span><span class="sxs-lookup"><span data-stu-id="cf507-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf507-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf507-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf507-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cf507-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="cf507-106">in Der Name der Datei, in der gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="cf507-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="cf507-107">Wenn dieser Wert NULL ist, wird die in-Memory-Kopie am letzten verwendeten Speicherort gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cf507-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="cf507-108">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="cf507-108">[in] Reserved.</span></span> <span data-ttu-id="cf507-109">Muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="cf507-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf507-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cf507-110">Requirements</span></span>  
 <span data-ttu-id="cf507-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf507-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf507-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cf507-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf507-113">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf507-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf507-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf507-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf507-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf507-115">See also</span></span>

- [<span data-ttu-id="cf507-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf507-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="cf507-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf507-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
