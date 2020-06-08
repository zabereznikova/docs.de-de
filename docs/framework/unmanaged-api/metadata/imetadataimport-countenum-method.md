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
ms.openlocfilehash: 4521a3f15ec358a4d786a4533efb6b99d0e1c1cc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492381"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="a23d8-102">IMetaDataImport::CountEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="a23d8-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="a23d8-103">Ruft die Anzahl der Elemente in der-Enumeration ab, die vom angegebenen Enumerator abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="a23d8-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a23d8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a23d8-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a23d8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a23d8-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="a23d8-106">in Das Handle für den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="a23d8-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="a23d8-107">vorgenommen Die Anzahl der aufgezählten Elemente.</span><span class="sxs-lookup"><span data-stu-id="a23d8-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a23d8-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a23d8-108">Remarks</span></span>  
 <span data-ttu-id="a23d8-109">Das Handle, das von angegeben `hEnum` wird, wird von einem vorherigen `Enum` *namens* -Ruf abgerufen (z. b. [IMetaDataImport:: EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="a23d8-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a23d8-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a23d8-110">Requirements</span></span>  
 <span data-ttu-id="a23d8-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a23d8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a23d8-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a23d8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a23d8-113">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a23d8-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a23d8-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a23d8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a23d8-115">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a23d8-115">See also</span></span>

- [<span data-ttu-id="a23d8-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a23d8-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a23d8-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a23d8-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
