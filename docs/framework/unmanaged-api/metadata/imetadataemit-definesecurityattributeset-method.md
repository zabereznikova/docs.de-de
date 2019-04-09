---
title: IMetaDataEmit::DefineSecurityAttributeSet-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f244d256d3af104d1d0c65769e82a87d6de046e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189012"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="dda3a-102">IMetaDataEmit::DefineSecurityAttributeSet-Methode</span><span class="sxs-lookup"><span data-stu-id="dda3a-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="dda3a-103">Erstellt einen Satz von Sicherheitsberechtigungen für das Anfügen an das Objekt, das durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="dda3a-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dda3a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dda3a-104">Syntax</span></span>  
  
```  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dda3a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dda3a-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="dda3a-106">[in] Das Token an den die Sicherheitsinformationen angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="dda3a-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="dda3a-107">[in] Ein Array von `COR_SECATTR` Strukturen.</span><span class="sxs-lookup"><span data-stu-id="dda3a-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="dda3a-108">[in] Die Anzahl der Elemente in `rSecAttrs`.</span><span class="sxs-lookup"><span data-stu-id="dda3a-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="dda3a-109">[out] Wenn die Methode fehlschlägt, gibt Sie den Index in `rSecAttrs` des Elements, das die Ursache des Problems.</span><span class="sxs-lookup"><span data-stu-id="dda3a-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dda3a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dda3a-110">Requirements</span></span>  
 <span data-ttu-id="dda3a-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dda3a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dda3a-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dda3a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dda3a-113">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="dda3a-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="dda3a-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="dda3a-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dda3a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dda3a-115">See also</span></span>

- [<span data-ttu-id="dda3a-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dda3a-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="dda3a-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dda3a-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
