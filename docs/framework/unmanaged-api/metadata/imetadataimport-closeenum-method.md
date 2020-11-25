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
ms.openlocfilehash: f418b48f1b62ae8093197d64ca44b2ef659990a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701717"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="a90c6-102">IMetaDataImport::CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="a90c6-102">IMetaDataImport::CloseEnum Method</span></span>

<span data-ttu-id="a90c6-103">Schließt den Enumerator, der durch das angegebene Handle identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="a90c6-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a90c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a90c6-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a90c6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a90c6-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="a90c6-106">in Das Handle für den Enumerator, der geschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a90c6-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a90c6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a90c6-107">Remarks</span></span>  

 <span data-ttu-id="a90c6-108">Das Handle, das von angegeben `hEnum` wird, wird von einem vorherigen `Enum` *namens* -Ruf abgerufen (z. b. [IMetaDataImport:: EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="a90c6-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a90c6-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a90c6-109">Requirements</span></span>  

 <span data-ttu-id="a90c6-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a90c6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a90c6-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a90c6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a90c6-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a90c6-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a90c6-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a90c6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a90c6-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a90c6-114">See also</span></span>

- [<span data-ttu-id="a90c6-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a90c6-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a90c6-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a90c6-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
