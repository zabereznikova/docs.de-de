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
ms.openlocfilehash: 5faf1a6ae89045b2ef17fab789ee6e5bf23eecf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175342"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="1e9bc-102">IMetaDataImport::GetPermissionSetProps-Methode</span><span class="sxs-lookup"><span data-stu-id="1e9bc-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="1e9bc-103">Ruft die Metadaten <xref:System.Security.PermissionSet?displayProperty=nameWithType> ab, die dem dargestellten durch das angegebene Berechtigungstoken zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e9bc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e9bc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e9bc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1e9bc-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="1e9bc-106">[in] Das Berechtigungsmetadatentoken, das den Berechtigungssatz zum Abrufen der Metadateneigenschaften darstellt.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="1e9bc-107">[out] Ein Zeiger auf den Berechtigungssatz.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="1e9bc-108">[out] Ein Zeiger auf die binäre Metadatensignatur des Berechtigungssatzes.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="1e9bc-109">[out] Die Größe in `ppvPermission`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="1e9bc-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e9bc-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1e9bc-110">Requirements</span></span>  
 <span data-ttu-id="1e9bc-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e9bc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e9bc-112">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1e9bc-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e9bc-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1e9bc-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e9bc-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e9bc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e9bc-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e9bc-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="1e9bc-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e9bc-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1e9bc-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e9bc-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
