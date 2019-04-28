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
ms.openlocfilehash: 3a99ed42f500b83b5109631b21a88029995b43d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777467"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="f3ca6-102">IMetaDataImport::IsValidToken-Methode</span><span class="sxs-lookup"><span data-stu-id="f3ca6-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="f3ca6-103">Ruft einen Wert ab, der angibt, ob das angegebene Token einen gültigen Verweis auf ein Codeobjekt enthält.</span><span class="sxs-lookup"><span data-stu-id="f3ca6-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3ca6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3ca6-104">Syntax</span></span>  
  
```  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3ca6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3ca6-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f3ca6-106">[in] Das Token überprüft die Gültigkeit des Verweises.</span><span class="sxs-lookup"><span data-stu-id="f3ca6-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3ca6-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f3ca6-107">Return Value</span></span>  
 <span data-ttu-id="f3ca6-108">`true` Wenn `tk` ist ein gültiges Metadatentoken im aktuellen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="f3ca6-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="f3ca6-109">Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="f3ca6-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3ca6-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3ca6-110">Requirements</span></span>  
 <span data-ttu-id="f3ca6-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3ca6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3ca6-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f3ca6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3ca6-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f3ca6-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f3ca6-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3ca6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ca6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3ca6-115">See also</span></span>

- [<span data-ttu-id="f3ca6-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3ca6-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f3ca6-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3ca6-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
