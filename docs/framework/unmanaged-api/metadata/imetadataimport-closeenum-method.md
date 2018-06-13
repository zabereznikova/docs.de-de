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
ms.openlocfilehash: 3d81f9b0107fd927ddfda24cfd0ea3249e4c8651
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448816"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="d5e1f-102">IMetaDataImport::CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="d5e1f-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="d5e1f-103">Schließt den Enumerator, der durch das angegebene Handle identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="d5e1f-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5e1f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5e1f-104">Syntax</span></span>  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5e1f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5e1f-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="d5e1f-106">[in] Das Handle für den Enumerator zu schließen.</span><span class="sxs-lookup"><span data-stu-id="d5e1f-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5e1f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5e1f-107">Remarks</span></span>  
 <span data-ttu-id="d5e1f-108">Das Handle, das vom angegebenen `hEnum` stammt von einer früheren `Enum` *Namen* aufrufen (z. B. [IMetaDataImport:: EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="d5e1f-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5e1f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d5e1f-109">Requirements</span></span>  
 <span data-ttu-id="d5e1f-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5e1f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5e1f-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d5e1f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d5e1f-112">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d5e1f-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d5e1f-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5e1f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e1f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5e1f-114">See Also</span></span>  
 [<span data-ttu-id="d5e1f-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5e1f-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="d5e1f-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5e1f-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
