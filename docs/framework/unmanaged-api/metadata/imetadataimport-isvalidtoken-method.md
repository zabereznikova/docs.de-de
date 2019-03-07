---
title: IMetaDataImport::IsValidToken-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e887fb5f4f9667bed7eef4a84899f82cada0fcd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489578"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="47e0e-102">IMetaDataImport::IsValidToken-Methode</span><span class="sxs-lookup"><span data-stu-id="47e0e-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="47e0e-103">Ruft einen Wert ab, der angibt, ob das angegebene Token einen gültigen Verweis auf ein Codeobjekt enthält.</span><span class="sxs-lookup"><span data-stu-id="47e0e-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47e0e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="47e0e-104">Syntax</span></span>  
  
```  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47e0e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="47e0e-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="47e0e-106">[in] Das Token überprüft die Gültigkeit des Verweises.</span><span class="sxs-lookup"><span data-stu-id="47e0e-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47e0e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="47e0e-107">Return Value</span></span>  
 <span data-ttu-id="47e0e-108">`true` Wenn `tk` ist ein gültiges Metadatentoken im aktuellen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="47e0e-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="47e0e-109">Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="47e0e-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47e0e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47e0e-110">Requirements</span></span>  
 <span data-ttu-id="47e0e-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47e0e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47e0e-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="47e0e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47e0e-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="47e0e-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47e0e-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47e0e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47e0e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47e0e-115">See also</span></span>
- [<span data-ttu-id="47e0e-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47e0e-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="47e0e-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47e0e-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
