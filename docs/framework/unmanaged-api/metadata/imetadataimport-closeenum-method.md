---
title: IMetaDataImport::CloseEnum-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 013629b5a3389fcb8da9368f7875bd1977ee9e20
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="6eae5-102">IMetaDataImport::CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="6eae5-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="6eae5-103">Schließt den Enumerator, der durch das angegebene Handle identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="6eae5-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eae5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6eae5-104">Syntax</span></span>  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6eae5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6eae5-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="6eae5-106">[in] Das Handle für den Enumerator zu schließen.</span><span class="sxs-lookup"><span data-stu-id="6eae5-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6eae5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6eae5-107">Remarks</span></span>  
 <span data-ttu-id="6eae5-108">Das Handle, das vom angegebenen `hEnum` stammt von einer früheren `Enum` *Namen* aufrufen (z. B. [IMetaDataImport:: EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="6eae5-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6eae5-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6eae5-109">Requirements</span></span>  
 <span data-ttu-id="6eae5-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6eae5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6eae5-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6eae5-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6eae5-112">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6eae5-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6eae5-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6eae5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eae5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6eae5-114">See Also</span></span>  
 [<span data-ttu-id="6eae5-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6eae5-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="6eae5-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6eae5-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
