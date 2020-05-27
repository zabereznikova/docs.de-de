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
ms.openlocfilehash: 23f6a301c4c11be92e05dbac0d4f69817d857a28
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003947"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="e6296-102">IMetaDataEmit::Save-Methode</span><span class="sxs-lookup"><span data-stu-id="e6296-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="e6296-103">Speichert alle Metadaten im aktuellen Gültigkeitsbereich in der Datei an der angegebenen Adresse.</span><span class="sxs-lookup"><span data-stu-id="e6296-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6296-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6296-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (
    [in]  LPCWSTR     szFile,
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6296-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e6296-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="e6296-106">in Der Name der Datei, in der gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e6296-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="e6296-107">Wenn dieser Wert NULL ist, wird die in-Memory-Kopie am letzten verwendeten Speicherort gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e6296-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="e6296-108">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="e6296-108">[in] Reserved.</span></span> <span data-ttu-id="e6296-109">Muss Null sein.</span><span class="sxs-lookup"><span data-stu-id="e6296-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6296-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e6296-110">Requirements</span></span>  
 <span data-ttu-id="e6296-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6296-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6296-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e6296-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e6296-113">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="e6296-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6296-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6296-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6296-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6296-115">See also</span></span>

- [<span data-ttu-id="e6296-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6296-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e6296-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6296-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
