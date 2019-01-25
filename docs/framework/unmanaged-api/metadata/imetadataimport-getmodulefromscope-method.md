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
ms.openlocfilehash: 931b17858465d4ff380069fc2cf2bb37cb7a7ffc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718181"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="83d26-102">IMetaDataImport::GetModuleFromScope-Methode</span><span class="sxs-lookup"><span data-stu-id="83d26-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="83d26-103">Ruft Metadaten für das Modul verwiesen wird, im aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="83d26-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d26-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="83d26-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83d26-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="83d26-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="83d26-106">[out] Ein Zeiger auf das Token, die das Modul im aktuellen Metadatenbereich verwiesen darstellt.</span><span class="sxs-lookup"><span data-stu-id="83d26-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83d26-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83d26-107">Requirements</span></span>  
 <span data-ttu-id="83d26-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83d26-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83d26-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="83d26-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83d26-110">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="83d26-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="83d26-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83d26-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d26-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83d26-112">See also</span></span>
- [<span data-ttu-id="83d26-113">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83d26-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="83d26-114">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83d26-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
