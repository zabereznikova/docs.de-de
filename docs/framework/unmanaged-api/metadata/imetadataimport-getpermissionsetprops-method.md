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
ms.openlocfilehash: 3ff91a24dec7f8507989b701ea24b569c1670c89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777610"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="6c2e7-102">IMetaDataImport::GetPermissionSetProps-Methode</span><span class="sxs-lookup"><span data-stu-id="6c2e7-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="6c2e7-103">Ruft ab, die zugeordneten Metadaten den <xref:System.Security.PermissionSet?displayProperty=nameWithType> durch das angegebene Berechtigungstoken dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6c2e7-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c2e7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c2e7-104">Syntax</span></span>  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c2e7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6c2e7-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="6c2e7-106">[in] Das Metadatentoken, das die Berechtigungen zum Abrufen der Metadateneigenschaften für darstellt.</span><span class="sxs-lookup"><span data-stu-id="6c2e7-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="6c2e7-107">[out] Ein Zeiger auf den Berechtigungssatz auf.</span><span class="sxs-lookup"><span data-stu-id="6c2e7-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="6c2e7-108">[out] Ein Zeiger auf die binäre Metadatensignatur des Berechtigungssatzes.</span><span class="sxs-lookup"><span data-stu-id="6c2e7-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="6c2e7-109">[out] Die Größe in Bytes der `ppvPermission`.</span><span class="sxs-lookup"><span data-stu-id="6c2e7-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c2e7-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c2e7-110">Requirements</span></span>  
 <span data-ttu-id="6c2e7-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c2e7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c2e7-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6c2e7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6c2e7-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6c2e7-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6c2e7-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c2e7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c2e7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c2e7-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="6c2e7-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6c2e7-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6c2e7-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6c2e7-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
