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
ms.openlocfilehash: ec92214e33cd1acda8b2702d93deba1f0fb2aaa2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111027"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="10381-102">ICLRMetadataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10381-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="10381-103">Wird von der Ebene der Datenzugriffs Dienste verwendet, um Metadaten von Assemblys in einem Ziel Prozess zu suchen.</span><span class="sxs-lookup"><span data-stu-id="10381-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10381-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="10381-104">Methods</span></span>  
  
|<span data-ttu-id="10381-105">Methode</span><span class="sxs-lookup"><span data-stu-id="10381-105">Method</span></span>|<span data-ttu-id="10381-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10381-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10381-107">GetMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="10381-107">GetMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="10381-108">Ruft die Metadaten eines Bilds aus dem Ziel Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="10381-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10381-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="10381-109">Remarks</span></span>  
 <span data-ttu-id="10381-110">Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="10381-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="10381-111">Beispielsweise unterscheidet sich die Implementierung für einen Live Prozess von der eines Speicher Abbilds.</span><span class="sxs-lookup"><span data-stu-id="10381-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10381-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10381-112">Requirements</span></span>  
 <span data-ttu-id="10381-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10381-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10381-114">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="10381-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="10381-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10381-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10381-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10381-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10381-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10381-117">See also</span></span>

- [<span data-ttu-id="10381-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="10381-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
