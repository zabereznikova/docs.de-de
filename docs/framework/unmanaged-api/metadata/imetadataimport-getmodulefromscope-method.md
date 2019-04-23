---
title: IMetaDataImport::GetModuleFromScope-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f40e6bfdbebdadc41da52564348c6070c18372c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194681"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="7c3d9-102">IMetaDataImport::GetModuleFromScope-Methode</span><span class="sxs-lookup"><span data-stu-id="7c3d9-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="7c3d9-103">Ruft Metadaten für das Modul verwiesen wird, im aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="7c3d9-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c3d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c3d9-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c3d9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c3d9-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="7c3d9-106">[out] Ein Zeiger auf das Token, die das Modul im aktuellen Metadatenbereich verwiesen darstellt.</span><span class="sxs-lookup"><span data-stu-id="7c3d9-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c3d9-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c3d9-107">Requirements</span></span>  
 <span data-ttu-id="7c3d9-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c3d9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c3d9-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c3d9-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c3d9-110">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7c3d9-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c3d9-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c3d9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c3d9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c3d9-112">See also</span></span>

- [<span data-ttu-id="7c3d9-113">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c3d9-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7c3d9-114">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c3d9-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
