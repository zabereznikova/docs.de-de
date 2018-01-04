---
title: IMetaDataEmit::DefineSecurityAttributeSet-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineSecurityAttributeSet
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4863ee416bba7fe66326c1d11ec3aa0037d022a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="146c8-102">IMetaDataEmit::DefineSecurityAttributeSet-Methode</span><span class="sxs-lookup"><span data-stu-id="146c8-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="146c8-103">Erstellt einen Satz von Sicherheitsberechtigungen für die Verbindung mit dem Objekt, das durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="146c8-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="146c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="146c8-104">Syntax</span></span>  
  
```  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="146c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="146c8-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="146c8-106">[in] Das Token an den die Sicherheitsinformationen angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="146c8-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="146c8-107">[in] Ein Array von `COR_SECATTR` Strukturen.</span><span class="sxs-lookup"><span data-stu-id="146c8-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="146c8-108">[in] Die Anzahl der Elemente im `rSecAttrs`.</span><span class="sxs-lookup"><span data-stu-id="146c8-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="146c8-109">[out] Wenn die Methode fehlschlägt, gibt den Index in `rSecAttrs` des Elements, das das Problem verursacht.</span><span class="sxs-lookup"><span data-stu-id="146c8-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="146c8-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="146c8-110">Requirements</span></span>  
 <span data-ttu-id="146c8-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="146c8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="146c8-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="146c8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="146c8-113">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="146c8-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="146c8-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="146c8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="146c8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="146c8-115">See Also</span></span>  
 [<span data-ttu-id="146c8-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="146c8-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="146c8-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="146c8-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
