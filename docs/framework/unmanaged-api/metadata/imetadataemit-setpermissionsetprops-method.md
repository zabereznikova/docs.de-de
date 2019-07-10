---
title: IMetaDataEmit::SetPermissionSetProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f77e6e9711f05262e494f2814750af8ef7cd9f64
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750906"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="37110-102">IMetaDataEmit::SetPermissionSetProps-Methode</span><span class="sxs-lookup"><span data-stu-id="37110-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="37110-103">Legt fest oder aktualisiert die Metadatensignatur der einen Berechtigungssatz auf, die von einem vorherigen Aufruf von definierten Funktionen [DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="37110-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37110-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37110-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37110-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="37110-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="37110-106">[in] Ein Metadatentoken, das das Objekt, das Attribut versehen werden darstellt.</span><span class="sxs-lookup"><span data-stu-id="37110-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="37110-107">[in] Ein [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) Wert, der angibt, den Typ der deklarativen Sicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37110-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="37110-108">[in] Die BLOB-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="37110-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="37110-109">[in] Die Größe in Bytes, des `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="37110-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="37110-110">[out] Ein `mdPermission` Metadatentoken, das die aktualisierten Berechtigungen darstellt.</span><span class="sxs-lookup"><span data-stu-id="37110-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37110-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="37110-111">Requirements</span></span>  
 <span data-ttu-id="37110-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37110-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37110-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="37110-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37110-114">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="37110-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37110-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37110-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37110-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37110-116">See also</span></span>

- [<span data-ttu-id="37110-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37110-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="37110-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37110-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
