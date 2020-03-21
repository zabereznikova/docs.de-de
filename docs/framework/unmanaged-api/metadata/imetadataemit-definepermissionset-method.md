---
title: IMetaDataEmit::DefinePermissionSet-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
ms.openlocfilehash: a0fd3fdb6dde9fd6b88ea6c64ed907c8a3e9e46d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175797"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="bfb3d-102">IMetaDataEmit::DefinePermissionSet-Methode</span><span class="sxs-lookup"><span data-stu-id="bfb3d-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="bfb3d-103">Erstellt eine Definition für einen Berechtigungssatz mit der angegebenen Metadatensignatur und ruft ein Token für diese Berechtigungssatzdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="bfb3d-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfb3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bfb3d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfb3d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bfb3d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="bfb3d-106">[in] Das zu verzierende Objekt.</span><span class="sxs-lookup"><span data-stu-id="bfb3d-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="bfb3d-107">[in] Ein [CorDeclSecurity-Wert,](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) der den Typ der zu verwendenden deklarativen Sicherheit angibt.</span><span class="sxs-lookup"><span data-stu-id="bfb3d-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="bfb3d-108">[in] Die Berechtigung BLOB.</span><span class="sxs-lookup"><span data-stu-id="bfb3d-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="bfb3d-109">[in] Die Größe von in `pvPermission`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="bfb3d-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="bfb3d-110">[out] Das zurückgegebene Berechtigungstoken.</span><span class="sxs-lookup"><span data-stu-id="bfb3d-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfb3d-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bfb3d-111">Requirements</span></span>  
 <span data-ttu-id="bfb3d-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfb3d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfb3d-113">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bfb3d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bfb3d-114">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="bfb3d-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bfb3d-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfb3d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfb3d-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bfb3d-116">See also</span></span>

- [<span data-ttu-id="bfb3d-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bfb3d-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bfb3d-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bfb3d-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
