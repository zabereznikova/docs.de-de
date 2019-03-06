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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4188d1ef83f685bf39bdf951939e0ec6493b323d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466400"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="b78ad-102">IMetaDataEmit::DefinePermissionSet-Methode</span><span class="sxs-lookup"><span data-stu-id="b78ad-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="b78ad-103">Erstellt eine Definition für einen Berechtigungssatz, der mit der angegebenen Metadaten-Signatur und ruft ein Token für die Definition dieser Berechtigung Menge ab.</span><span class="sxs-lookup"><span data-stu-id="b78ad-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b78ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b78ad-104">Syntax</span></span>  
  
```  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b78ad-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b78ad-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="b78ad-106">[in] Das Objekt, das Attribut versehen werden.</span><span class="sxs-lookup"><span data-stu-id="b78ad-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="b78ad-107">[in] Ein [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) Wert, der angibt, den Typ der deklarativen Sicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b78ad-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="b78ad-108">[in] Die BLOB-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="b78ad-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="b78ad-109">[in] Die Größe in Bytes, des `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="b78ad-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="b78ad-110">[out] Das zurückgegebene Berechtigungstoken.</span><span class="sxs-lookup"><span data-stu-id="b78ad-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b78ad-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b78ad-111">Requirements</span></span>  
 <span data-ttu-id="b78ad-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b78ad-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b78ad-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b78ad-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b78ad-114">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="b78ad-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b78ad-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b78ad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b78ad-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b78ad-116">See also</span></span>
- [<span data-ttu-id="b78ad-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b78ad-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b78ad-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b78ad-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
