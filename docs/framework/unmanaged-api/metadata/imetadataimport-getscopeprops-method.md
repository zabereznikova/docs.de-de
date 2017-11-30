---
title: IMetaDataImport::GetScopeProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetScopeProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5b0936a9f47e2d0fa52816b78a7eecf3d244d594
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="48435-102">IMetaDataImport::GetScopeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="48435-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="48435-103">Ruft den Namen und optional den Versionsbezeichner der Assembly oder des Moduls im aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="48435-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48435-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48435-104">Syntax</span></span>  
  
```  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48435-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="48435-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="48435-106">[out] Ein Puffer für die Assembly oder ein Modul Name.</span><span class="sxs-lookup"><span data-stu-id="48435-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="48435-107">[in] Die Größe in Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="48435-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="48435-108">[out] Die Anzahl der Breitzeichen, die im zurückgegebenen `szName`.</span><span class="sxs-lookup"><span data-stu-id="48435-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="48435-109">[out, optional] Ein Zeiger auf eine GUID, die die Version der Assembly oder des Moduls eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="48435-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48435-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48435-110">Remarks</span></span>  
 <span data-ttu-id="48435-111">Die [IMetaDataEmit:: SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) Methode zum Festlegen dieser Eigenschaften verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="48435-111">The [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48435-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="48435-112">Requirements</span></span>  
 <span data-ttu-id="48435-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48435-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48435-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="48435-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="48435-115">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="48435-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="48435-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48435-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48435-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48435-117">See Also</span></span>  
 [<span data-ttu-id="48435-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48435-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="48435-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48435-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
