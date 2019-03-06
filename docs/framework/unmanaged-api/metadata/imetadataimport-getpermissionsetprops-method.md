---
title: IMetaDataImport::GetPermissionSetProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 806f1ebcacb9e7ad27b7370f9976b3341bf64f8c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466933"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="f1d89-102">IMetaDataImport::GetPermissionSetProps-Methode</span><span class="sxs-lookup"><span data-stu-id="f1d89-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="f1d89-103">Ruft ab, die zugeordneten Metadaten den <xref:System.Security.PermissionSet?displayProperty=nameWithType> durch das angegebene Berechtigungstoken dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f1d89-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1d89-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1d89-104">Syntax</span></span>  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1d89-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1d89-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="f1d89-106">[in] Das Metadatentoken, das die Berechtigungen zum Abrufen der Metadateneigenschaften für darstellt.</span><span class="sxs-lookup"><span data-stu-id="f1d89-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="f1d89-107">[out] Ein Zeiger auf den Berechtigungssatz auf.</span><span class="sxs-lookup"><span data-stu-id="f1d89-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="f1d89-108">[out] Ein Zeiger auf die binäre Metadatensignatur des Berechtigungssatzes.</span><span class="sxs-lookup"><span data-stu-id="f1d89-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="f1d89-109">[out] Die Größe in Bytes der `ppvPermission`.</span><span class="sxs-lookup"><span data-stu-id="f1d89-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1d89-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f1d89-110">Requirements</span></span>  
 <span data-ttu-id="f1d89-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1d89-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1d89-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f1d89-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1d89-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f1d89-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1d89-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1d89-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d89-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1d89-115">See also</span></span>
- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="f1d89-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1d89-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f1d89-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1d89-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
