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
ms.openlocfilehash: 753449924f3415eb826b59d3a887eb69b9efba39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778787"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="081b9-102">IMetaDataImport::IsValidToken-Methode</span><span class="sxs-lookup"><span data-stu-id="081b9-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="081b9-103">Ruft einen Wert ab, der angibt, ob das angegebene Token einen gültigen Verweis auf ein Codeobjekt enthält.</span><span class="sxs-lookup"><span data-stu-id="081b9-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="081b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="081b9-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="081b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="081b9-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="081b9-106">[in] Das Token überprüft die Gültigkeit des Verweises.</span><span class="sxs-lookup"><span data-stu-id="081b9-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="081b9-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="081b9-107">Return Value</span></span>  
 <span data-ttu-id="081b9-108">`true` Wenn `tk` ist ein gültiges Metadatentoken im aktuellen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="081b9-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="081b9-109">Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="081b9-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="081b9-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="081b9-110">Requirements</span></span>  
 <span data-ttu-id="081b9-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="081b9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="081b9-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="081b9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="081b9-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="081b9-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="081b9-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="081b9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="081b9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="081b9-115">See also</span></span>

- [<span data-ttu-id="081b9-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="081b9-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="081b9-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="081b9-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
