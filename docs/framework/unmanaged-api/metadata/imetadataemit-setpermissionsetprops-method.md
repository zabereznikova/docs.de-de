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
ms.openlocfilehash: 53a75b8e7edd15cd233577e0a3714fb5d981495f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432328"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="420a1-102">IMetaDataEmit::SetPermissionSetProps-Methode</span><span class="sxs-lookup"><span data-stu-id="420a1-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="420a1-103">Legt die Features der Metadatensignatur eines Berechtigungs Satzes fest, der durch einen vorherigen [IMetaDataEmit::D efinepermissionset](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)definiert ist, oder aktualisiert diese.</span><span class="sxs-lookup"><span data-stu-id="420a1-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="420a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="420a1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="420a1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="420a1-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="420a1-106">in Ein Metadatentoken, das das zu ergänzte Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="420a1-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="420a1-107">in Ein [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) -Wert, der den Typ der zu verwendenden deklarativen Sicherheit angibt.</span><span class="sxs-lookup"><span data-stu-id="420a1-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="420a1-108">in Das Berechtigungs-BLOB.</span><span class="sxs-lookup"><span data-stu-id="420a1-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="420a1-109">in Die Größe `pvPermission`in Byte.</span><span class="sxs-lookup"><span data-stu-id="420a1-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="420a1-110">vorgenommen Ein `mdPermission` Metadatentoken, das die aktualisierten Berechtigungen darstellt.</span><span class="sxs-lookup"><span data-stu-id="420a1-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="420a1-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="420a1-111">Requirements</span></span>  
 <span data-ttu-id="420a1-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="420a1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="420a1-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="420a1-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="420a1-114">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="420a1-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="420a1-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="420a1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="420a1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="420a1-116">See also</span></span>

- [<span data-ttu-id="420a1-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="420a1-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="420a1-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="420a1-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
