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
ms.openlocfilehash: 89c45c049ebadf9e1f16bef8d2626b4e2a17fb70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729251"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="5baf5-102">IMetaDataImport::GetPermissionSetProps-Methode</span><span class="sxs-lookup"><span data-stu-id="5baf5-102">IMetaDataImport::GetPermissionSetProps Method</span></span>

<span data-ttu-id="5baf5-103">Ruft die Metadaten ab, die dem <xref:System.Security.PermissionSet?displayProperty=nameWithType> durch das angegebene Berechtigungs Token dargestellten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5baf5-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5baf5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5baf5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5baf5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5baf5-105">Parameters</span></span>  

 `pm`  
 <span data-ttu-id="5baf5-106">in Das Berechtigungs Metadatentoken, das den Berechtigungs Satz darstellt, für den die Metadateneigenschaften zu erhalten sind</span><span class="sxs-lookup"><span data-stu-id="5baf5-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="5baf5-107">vorgenommen Ein Zeiger auf den Berechtigungs Satz.</span><span class="sxs-lookup"><span data-stu-id="5baf5-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="5baf5-108">vorgenommen Ein Zeiger auf die binäre Metadatensignatur des Berechtigungs Satzes.</span><span class="sxs-lookup"><span data-stu-id="5baf5-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="5baf5-109">vorgenommen Die Größe von in Bytes `ppvPermission` .</span><span class="sxs-lookup"><span data-stu-id="5baf5-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5baf5-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5baf5-110">Requirements</span></span>  

 <span data-ttu-id="5baf5-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5baf5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5baf5-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5baf5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5baf5-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5baf5-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5baf5-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5baf5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5baf5-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5baf5-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="5baf5-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5baf5-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="5baf5-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5baf5-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
