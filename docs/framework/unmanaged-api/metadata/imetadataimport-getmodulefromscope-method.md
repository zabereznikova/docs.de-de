---
title: IMetaDataImport::GetModuleFromScope-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetModuleFromScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b389df634a69bff6197ae11dea96fbb6344dd369
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="f6656-102">IMetaDataImport::GetModuleFromScope-Methode</span><span class="sxs-lookup"><span data-stu-id="f6656-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="f6656-103">Ruft ein Metadatentoken für das Modul im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f6656-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6656-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6656-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6656-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6656-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="f6656-106">[out] Ein Zeiger auf das Token für das Modul im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f6656-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6656-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6656-107">Requirements</span></span>  
 <span data-ttu-id="f6656-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6656-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6656-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f6656-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f6656-110">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f6656-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6656-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6656-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6656-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6656-112">See Also</span></span>  
 [<span data-ttu-id="f6656-113">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6656-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="f6656-114">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6656-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
