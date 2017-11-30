---
title: IMetaDataEmit::DefinePermissionSet-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefinePermissionSet
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6a503f22710f392ecbb0ae2704d2c2950a858c30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="cd6ce-102">IMetaDataEmit::DefinePermissionSet-Methode</span><span class="sxs-lookup"><span data-stu-id="cd6ce-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="cd6ce-103">Erstellt eine Definition für einen Berechtigungssatz, der mit der angegebenen Metadatensignatur und ruft ein Token für diese Berechtigungssatzdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="cd6ce-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd6ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd6ce-104">Syntax</span></span>  
  
```  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd6ce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cd6ce-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="cd6ce-106">[in] Das Objekt, ergänzt werden.</span><span class="sxs-lookup"><span data-stu-id="cd6ce-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="cd6ce-107">[in] Ein [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) Wert, der den Typ des zu verwendenden deklarative Sicherheit angibt.</span><span class="sxs-lookup"><span data-stu-id="cd6ce-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="cd6ce-108">[in] Die BLOB-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="cd6ce-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="cd6ce-109">[in] Die Größe in Bytes, der `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="cd6ce-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="cd6ce-110">[out] Die zurückgegebene Berechtigungstoken.</span><span class="sxs-lookup"><span data-stu-id="cd6ce-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd6ce-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd6ce-111">Requirements</span></span>  
 <span data-ttu-id="cd6ce-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd6ce-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd6ce-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cd6ce-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cd6ce-114">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="cd6ce-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd6ce-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd6ce-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd6ce-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd6ce-116">See Also</span></span>  
 [<span data-ttu-id="cd6ce-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cd6ce-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="cd6ce-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cd6ce-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
