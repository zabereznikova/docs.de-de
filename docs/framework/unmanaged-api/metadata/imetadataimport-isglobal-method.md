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
ms.openlocfilehash: 13f8a50f3fcbe9d6e7602ca3bbeb36587ecff32c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778800"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="2a6b0-102">IMetaDataImport::IsGlobal-Methode</span><span class="sxs-lookup"><span data-stu-id="2a6b0-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="2a6b0-103">Ruft einen Wert ab, der angibt, ob für das durch das angegebene Metadatentoken dargestellte Feld, die Methode oder den Typ der globale Bereich gilt.</span><span class="sxs-lookup"><span data-stu-id="2a6b0-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a6b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a6b0-104">Syntax</span></span>  
  
```cpp  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a6b0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a6b0-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="2a6b0-106">[in] Ein Metadatentoken, das einen Typ, ein Feld oder Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="2a6b0-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="2a6b0-107">[out] 1, wenn hat das Objekt einen globalen Gültigkeitsbereich; andernfalls 0 (null).</span><span class="sxs-lookup"><span data-stu-id="2a6b0-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a6b0-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2a6b0-108">Requirements</span></span>  
 <span data-ttu-id="2a6b0-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a6b0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a6b0-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2a6b0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a6b0-111">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2a6b0-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a6b0-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a6b0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a6b0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a6b0-113">See also</span></span>

- [<span data-ttu-id="2a6b0-114">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a6b0-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2a6b0-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a6b0-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
