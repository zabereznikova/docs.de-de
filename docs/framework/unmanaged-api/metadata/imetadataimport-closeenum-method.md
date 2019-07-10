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
ms.openlocfilehash: 7f27955467436d562c6a9acc9d7f666427e4c85b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770713"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="6a3b6-102">IMetaDataImport::CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="6a3b6-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="6a3b6-103">Schließt den Enumerator, der durch das angegebene Handle identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="6a3b6-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a3b6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a3b6-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a3b6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6a3b6-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="6a3b6-106">[in] Das Handle für den Enumerator zu schließen.</span><span class="sxs-lookup"><span data-stu-id="6a3b6-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a3b6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a3b6-107">Remarks</span></span>  
 <span data-ttu-id="6a3b6-108">Das Handle, das vom angegebenen `hEnum` abgerufen wird, von einer früheren `Enum` *Namen* aufrufen (z. B. [IMetaDataImport:: EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="6a3b6-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a3b6-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6a3b6-109">Requirements</span></span>  
 <span data-ttu-id="6a3b6-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a3b6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a3b6-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6a3b6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a3b6-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6a3b6-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6a3b6-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a3b6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a3b6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a3b6-114">See also</span></span>

- [<span data-ttu-id="6a3b6-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a3b6-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6a3b6-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a3b6-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
