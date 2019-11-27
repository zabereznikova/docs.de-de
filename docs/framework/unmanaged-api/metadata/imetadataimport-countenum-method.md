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
ms.openlocfilehash: 0c78ce8192d6456dd1b1be990d87b9209b028e09
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440368"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="301c9-102">IMetaDataImport::CountEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="301c9-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="301c9-103">Ruft die Anzahl der Elemente in der-Enumeration ab, die vom angegebenen Enumerator abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="301c9-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="301c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="301c9-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="301c9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="301c9-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="301c9-106">in Das Handle für den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="301c9-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="301c9-107">vorgenommen Die Anzahl der aufgezählten Elemente.</span><span class="sxs-lookup"><span data-stu-id="301c9-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="301c9-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="301c9-108">Remarks</span></span>  
 <span data-ttu-id="301c9-109">Das durch `hEnum` angegebene Handle wird von einem vorherigen `Enum`*namens* aufrufruf abgerufen (z. b. [IMetaDataImport:: EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="301c9-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="301c9-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="301c9-110">Requirements</span></span>  
 <span data-ttu-id="301c9-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="301c9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="301c9-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="301c9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="301c9-113">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="301c9-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="301c9-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="301c9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="301c9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="301c9-115">See also</span></span>

- [<span data-ttu-id="301c9-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="301c9-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="301c9-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="301c9-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
