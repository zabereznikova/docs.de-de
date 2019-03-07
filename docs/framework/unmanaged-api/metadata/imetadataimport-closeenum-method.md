---
title: IMetaDataImport::CloseEnum-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dda94acc2ec5da456cdc41ba0902cdc414b11524
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486380"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="dc411-102">IMetaDataImport::CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="dc411-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="dc411-103">Schließt den Enumerator, der durch das angegebene Handle identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="dc411-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc411-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc411-104">Syntax</span></span>  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc411-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dc411-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="dc411-106">[in] Das Handle für den Enumerator zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dc411-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc411-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dc411-107">Remarks</span></span>  
 <span data-ttu-id="dc411-108">Das Handle, das vom angegebenen `hEnum` abgerufen wird, von einer früheren `Enum` *Namen* aufrufen (z. B. [IMetaDataImport:: EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="dc411-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc411-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dc411-109">Requirements</span></span>  
 <span data-ttu-id="dc411-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc411-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc411-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dc411-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc411-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dc411-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dc411-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc411-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc411-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc411-114">See also</span></span>
- [<span data-ttu-id="dc411-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc411-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dc411-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc411-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
