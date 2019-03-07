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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a1963221942134d148d5417ebafea97a26aead5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494284"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="2ca52-102">IMetaDataEmit2::SaveDelta-Methode</span><span class="sxs-lookup"><span data-stu-id="2ca52-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="2ca52-103">Speichert Änderungen aus der aktuellen Sitzung mit bearbeiten und fortfahren, in der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="2ca52-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ca52-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ca52-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ca52-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ca52-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="2ca52-106">[in] Der Dateiname, unter dem die Änderungen gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2ca52-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="2ca52-107">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="2ca52-107">[in] Reserved.</span></span> <span data-ttu-id="2ca52-108">NULL muss sein.</span><span class="sxs-lookup"><span data-stu-id="2ca52-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ca52-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ca52-109">Requirements</span></span>  
 <span data-ttu-id="2ca52-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ca52-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ca52-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2ca52-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2ca52-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2ca52-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2ca52-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ca52-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ca52-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ca52-114">See also</span></span>
- [<span data-ttu-id="2ca52-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ca52-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="2ca52-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ca52-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
