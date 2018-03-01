---
title: ICLRMetadataLocator-Schnittstelle
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
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a06997c47a85ced56dc579759192f7256def4f5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="082a7-102">ICLRMetadataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="082a7-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="082a7-103">Von der Datenzugriffsdienstebene Metadaten von Assemblys in einem Zielprozess Suche verwendet.</span><span class="sxs-lookup"><span data-stu-id="082a7-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="082a7-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="082a7-104">Methods</span></span>  
  
|<span data-ttu-id="082a7-105">Methode</span><span class="sxs-lookup"><span data-stu-id="082a7-105">Method</span></span>|<span data-ttu-id="082a7-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="082a7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="082a7-107">GetMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="082a7-107">GetMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="082a7-108">Ruft die Metadaten eines Bilds aus dem Zielprozess ab.</span><span class="sxs-lookup"><span data-stu-id="082a7-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="082a7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="082a7-109">Remarks</span></span>  
 <span data-ttu-id="082a7-110">Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="082a7-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="082a7-111">Beispielsweise würde die Implementierung für ein Liveprozess aus einem Speicherabbild unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="082a7-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="082a7-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="082a7-112">Requirements</span></span>  
 <span data-ttu-id="082a7-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="082a7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="082a7-114">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="082a7-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="082a7-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="082a7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="082a7-116">**.**</span><span class="sxs-lookup"><span data-stu-id="082a7-116">**.**</span></span> <span data-ttu-id="082a7-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="082a7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="082a7-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="082a7-118">See Also</span></span>  
 [<span data-ttu-id="082a7-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="082a7-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
