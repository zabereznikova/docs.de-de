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
ms.openlocfilehash: d3e25f271fc434785e25e7b226ad98f86b5f8dfc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492784"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="8c306-102">IMetaDataEmit2::SaveDelta-Methode</span><span class="sxs-lookup"><span data-stu-id="8c306-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="8c306-103">Speichert Änderungen aus der aktuellen Bearbeitungs-und fortsetzungssitzung in der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="8c306-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c306-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c306-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c306-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c306-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="8c306-106">in Der Dateiname, unter dem die Änderungen gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8c306-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="8c306-107">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="8c306-107">[in] Reserved.</span></span> <span data-ttu-id="8c306-108">Muss Null sein.</span><span class="sxs-lookup"><span data-stu-id="8c306-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c306-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8c306-109">Requirements</span></span>  
 <span data-ttu-id="8c306-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c306-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c306-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8c306-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c306-112">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c306-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8c306-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c306-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c306-114">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="8c306-114">See also</span></span>

- [<span data-ttu-id="8c306-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c306-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="8c306-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c306-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
