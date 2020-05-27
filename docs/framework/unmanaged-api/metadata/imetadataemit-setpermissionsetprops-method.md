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
ms.openlocfilehash: 1e6ee1f2f497ef30a5390e7afac55c54705248ed
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007805"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="b6d53-102">IMetaDataEmit::SetPermissionSetProps-Methode</span><span class="sxs-lookup"><span data-stu-id="b6d53-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="b6d53-103">Legt die Features der Metadatensignatur eines Berechtigungs Satzes fest, der durch einen vorherigen [IMetaDataEmit::D efinepermissionset](imetadataemit-definepermissionset-method.md)definiert ist, oder aktualisiert diese.</span><span class="sxs-lookup"><span data-stu-id="b6d53-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d53-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6d53-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6d53-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b6d53-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="b6d53-106">in Ein Metadatentoken, das das zu ergänzte Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="b6d53-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="b6d53-107">in Ein [CorDeclSecurity](cordeclsecurity-enumeration.md) -Wert, der den Typ der zu verwendenden deklarativen Sicherheit angibt.</span><span class="sxs-lookup"><span data-stu-id="b6d53-107">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="b6d53-108">in Das Berechtigungs-BLOB.</span><span class="sxs-lookup"><span data-stu-id="b6d53-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="b6d53-109">in Die Größe von in Bytes `pvPermission` .</span><span class="sxs-lookup"><span data-stu-id="b6d53-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="b6d53-110">vorgenommen Ein `mdPermission` Metadatentoken, das die aktualisierten Berechtigungen darstellt.</span><span class="sxs-lookup"><span data-stu-id="b6d53-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6d53-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b6d53-111">Requirements</span></span>  
 <span data-ttu-id="b6d53-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6d53-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6d53-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b6d53-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6d53-114">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="b6d53-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6d53-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6d53-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6d53-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6d53-116">See also</span></span>

- [<span data-ttu-id="b6d53-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b6d53-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b6d53-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b6d53-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
