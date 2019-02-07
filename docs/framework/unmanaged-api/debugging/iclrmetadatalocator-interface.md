---
title: ICLRMetadataLocator-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5dd77783c03d6a61d0b5831e44db97a731d8074
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825887"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="d5db9-102">ICLRMetadataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5db9-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="d5db9-103">Wird von der Datenzugriffsdienstebene zum Suchen von Metadaten von Assemblys in einem Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="d5db9-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5db9-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d5db9-104">Methods</span></span>  
  
|<span data-ttu-id="d5db9-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d5db9-105">Method</span></span>|<span data-ttu-id="d5db9-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5db9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5db9-107">GetMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="d5db9-107">GetMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="d5db9-108">Ruft die Metadaten eines Bilds aus dem Zielprozess ab.</span><span class="sxs-lookup"><span data-stu-id="d5db9-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5db9-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5db9-109">Remarks</span></span>  
 <span data-ttu-id="d5db9-110">Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="d5db9-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="d5db9-111">Beispielsweise würde die Implementierung für einen aktiven Prozess von der ein Speicherabbild unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="d5db9-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5db9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d5db9-112">Requirements</span></span>  
 <span data-ttu-id="d5db9-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5db9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5db9-114">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="d5db9-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d5db9-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5db9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5db9-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5db9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5db9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5db9-117">See also</span></span>
- [<span data-ttu-id="d5db9-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d5db9-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
