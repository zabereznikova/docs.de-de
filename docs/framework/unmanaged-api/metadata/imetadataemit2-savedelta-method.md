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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168999"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="2987b-102">IMetaDataEmit2::SaveDelta-Methode</span><span class="sxs-lookup"><span data-stu-id="2987b-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="2987b-103">Speichert Änderungen aus der aktuellen Sitzung mit bearbeiten und fortfahren, in der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="2987b-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2987b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2987b-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2987b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2987b-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="2987b-106">[in] Der Dateiname, unter dem die Änderungen gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2987b-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="2987b-107">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="2987b-107">[in] Reserved.</span></span> <span data-ttu-id="2987b-108">NULL muss sein.</span><span class="sxs-lookup"><span data-stu-id="2987b-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2987b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2987b-109">Requirements</span></span>  
 <span data-ttu-id="2987b-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2987b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2987b-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2987b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2987b-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2987b-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="2987b-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="2987b-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2987b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2987b-114">See also</span></span>

- [<span data-ttu-id="2987b-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2987b-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="2987b-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2987b-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
