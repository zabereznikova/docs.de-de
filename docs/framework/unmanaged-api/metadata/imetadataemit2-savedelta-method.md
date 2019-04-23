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
ms.openlocfilehash: d97f536d54ac1cb77c5d0413d2437508374ac7f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168999"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="c29cf-102">IMetaDataEmit2::SaveDelta-Methode</span><span class="sxs-lookup"><span data-stu-id="c29cf-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="c29cf-103">Speichert Änderungen aus der aktuellen Sitzung mit bearbeiten und fortfahren, in der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="c29cf-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c29cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c29cf-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c29cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c29cf-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="c29cf-106">[in] Der Dateiname, unter dem die Änderungen gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c29cf-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="c29cf-107">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="c29cf-107">[in] Reserved.</span></span> <span data-ttu-id="c29cf-108">NULL muss sein.</span><span class="sxs-lookup"><span data-stu-id="c29cf-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c29cf-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c29cf-109">Requirements</span></span>  
 <span data-ttu-id="c29cf-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c29cf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c29cf-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c29cf-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c29cf-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c29cf-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c29cf-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c29cf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c29cf-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c29cf-114">See also</span></span>

- [<span data-ttu-id="c29cf-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c29cf-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="c29cf-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c29cf-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
