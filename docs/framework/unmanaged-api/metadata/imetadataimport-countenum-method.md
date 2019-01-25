---
title: IMetaDataImport::CountEnum-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CountEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b48ff81fad397adcd5b2d0caae961484bfea5e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706390"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="997e2-102">IMetaDataImport::CountEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="997e2-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="997e2-103">Ruft die Anzahl der Elemente in der Enumeration, die von den angegebenen Enumerator abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="997e2-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="997e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="997e2-104">Syntax</span></span>  
  
```  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="997e2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="997e2-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="997e2-106">[in] Das Handle für den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="997e2-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="997e2-107">[out] Die Anzahl der aufgelisteten Elemente.</span><span class="sxs-lookup"><span data-stu-id="997e2-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="997e2-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="997e2-108">Remarks</span></span>  
 <span data-ttu-id="997e2-109">Das Handle, das vom angegebenen `hEnum` abgerufen wird, von einer früheren `Enum` *Namen* aufrufen (z. B. [IMetaDataImport:: EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="997e2-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="997e2-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="997e2-110">Requirements</span></span>  
 <span data-ttu-id="997e2-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="997e2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="997e2-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="997e2-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="997e2-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="997e2-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="997e2-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="997e2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="997e2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="997e2-115">See also</span></span>
- [<span data-ttu-id="997e2-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="997e2-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="997e2-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="997e2-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
