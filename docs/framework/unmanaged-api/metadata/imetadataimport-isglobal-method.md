---
title: IMetaDataImport::IsGlobal-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4156c3507ccbd21d59893c5e03e15fe9b7322e48
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447797"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="3c8a6-102">IMetaDataImport::IsGlobal-Methode</span><span class="sxs-lookup"><span data-stu-id="3c8a6-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="3c8a6-103">Ruft einen Wert ab, der angibt, ob für das durch das angegebene Metadatentoken dargestellte Feld, die Methode oder den Typ der globale Bereich gilt.</span><span class="sxs-lookup"><span data-stu-id="3c8a6-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c8a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c8a6-104">Syntax</span></span>  
  
```  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c8a6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3c8a6-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="3c8a6-106">[in] Ein Metadatentoken, das einen Typ, ein Feld oder Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="3c8a6-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="3c8a6-107">[out] 1, wenn hat das Objekt globalen Gültigkeitsbereich. andernfalls 0 (null).</span><span class="sxs-lookup"><span data-stu-id="3c8a6-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c8a6-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3c8a6-108">Requirements</span></span>  
 <span data-ttu-id="3c8a6-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c8a6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c8a6-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c8a6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c8a6-111">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3c8a6-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c8a6-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c8a6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c8a6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c8a6-113">See Also</span></span>  
 [<span data-ttu-id="3c8a6-114">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c8a6-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="3c8a6-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c8a6-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
