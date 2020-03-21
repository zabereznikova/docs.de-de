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
ms.openlocfilehash: b780ca513d8a0b4f88e66594e86e9ff8290f6523
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177360"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="bcb93-102">IMetaDataImport::CountEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="bcb93-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="bcb93-103">Ruft die Anzahl der Elemente in der Enumeration ab, die vom angegebenen Enumerator abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="bcb93-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcb93-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bcb93-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcb93-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bcb93-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="bcb93-106">[in] Der Handle für den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="bcb93-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="bcb93-107">[out] Die Anzahl der aufgezählten Elemente.</span><span class="sxs-lookup"><span data-stu-id="bcb93-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcb93-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bcb93-108">Remarks</span></span>  
 <span data-ttu-id="bcb93-109">`hEnum` Das von angegebene Handle wird `Enum`von einem vorherigen *Name-Aufruf* abgerufen (z. B. [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="bcb93-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcb93-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bcb93-110">Requirements</span></span>  
 <span data-ttu-id="bcb93-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcb93-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcb93-112">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bcb93-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bcb93-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bcb93-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bcb93-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcb93-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcb93-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bcb93-115">See also</span></span>

- [<span data-ttu-id="bcb93-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bcb93-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bcb93-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bcb93-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
