---
title: IMetaDataImport::GetScopeProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 061c482a7e674fd425fe627c741a11b39864ba5c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778860"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="056f6-102">IMetaDataImport::GetScopeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="056f6-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="056f6-103">Ruft den Namen und optional den Versionsbezeichner der Assembly oder des Moduls im aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="056f6-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="056f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="056f6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="056f6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="056f6-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="056f6-106">[out] Ein Puffer für den Namen der Assembly "oder"-Modul.</span><span class="sxs-lookup"><span data-stu-id="056f6-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="056f6-107">[in] Die Größe in Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="056f6-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="056f6-108">[out] Die Anzahl der Breitzeichen, die in zurückgegebenen `szName`.</span><span class="sxs-lookup"><span data-stu-id="056f6-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="056f6-109">[Out, optional] Ein Zeiger auf eine GUID, die die Version der Assembly oder des Moduls eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="056f6-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="056f6-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="056f6-110">Remarks</span></span>  
 <span data-ttu-id="056f6-111">Die [IMetaDataEmit:: SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) Methode dient zum Festlegen dieser Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="056f6-111">The [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="056f6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="056f6-112">Requirements</span></span>  
 <span data-ttu-id="056f6-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="056f6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="056f6-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="056f6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="056f6-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="056f6-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="056f6-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="056f6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="056f6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="056f6-117">See also</span></span>

- [<span data-ttu-id="056f6-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="056f6-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="056f6-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="056f6-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
