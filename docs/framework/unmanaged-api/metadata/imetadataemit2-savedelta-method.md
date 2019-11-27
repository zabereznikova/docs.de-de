---
title: IMetaDataEmit2::SaveDelta-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
ms.openlocfilehash: afb0c09c09236267be2a999ce5c130feebb52b6f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447903"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="f3600-102">IMetaDataEmit2::SaveDelta-Methode</span><span class="sxs-lookup"><span data-stu-id="f3600-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="f3600-103">Speichert Änderungen aus der aktuellen Bearbeitungs-und fortsetzungssitzung in der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="f3600-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3600-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3600-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3600-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3600-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="f3600-106">in Der Dateiname, unter dem die Änderungen gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f3600-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="f3600-107">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="f3600-107">[in] Reserved.</span></span> <span data-ttu-id="f3600-108">Muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="f3600-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3600-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f3600-109">Requirements</span></span>  
 <span data-ttu-id="f3600-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3600-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3600-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f3600-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3600-112">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="f3600-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f3600-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3600-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3600-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3600-114">See also</span></span>

- [<span data-ttu-id="f3600-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3600-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="f3600-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3600-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
