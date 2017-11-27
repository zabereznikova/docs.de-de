---
title: IMetaDataImport::IsGlobal-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.IsGlobal
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09f7d437e09063bf621990dec4f2903139af8238
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="00d17-102">IMetaDataImport::IsGlobal-Methode</span><span class="sxs-lookup"><span data-stu-id="00d17-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="00d17-103">Ruft einen Wert ab, der angibt, ob für das durch das angegebene Metadatentoken dargestellte Feld, die Methode oder den Typ der globale Bereich gilt.</span><span class="sxs-lookup"><span data-stu-id="00d17-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00d17-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00d17-104">Syntax</span></span>  
  
```  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00d17-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="00d17-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="00d17-106">[in] Ein Metadatentoken, das einen Typ, ein Feld oder Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="00d17-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="00d17-107">[out] 1, wenn hat das Objekt globalen Gültigkeitsbereich. andernfalls 0 (null).</span><span class="sxs-lookup"><span data-stu-id="00d17-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00d17-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00d17-108">Requirements</span></span>  
 <span data-ttu-id="00d17-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00d17-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00d17-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="00d17-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="00d17-111">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="00d17-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="00d17-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00d17-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00d17-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00d17-113">See Also</span></span>  
 [<span data-ttu-id="00d17-114">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00d17-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="00d17-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00d17-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
