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
ms.openlocfilehash: 734f8eaa7c520bbf1ad1208ece42751e967a208a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859718"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="096cf-102">ICLRMetadataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="096cf-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="096cf-103">Wird von der Ebene der Datenzugriffs Dienste verwendet, um Metadaten von Assemblys in einem Ziel Prozess zu suchen.</span><span class="sxs-lookup"><span data-stu-id="096cf-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="096cf-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="096cf-104">Methods</span></span>  
  
|<span data-ttu-id="096cf-105">Methode</span><span class="sxs-lookup"><span data-stu-id="096cf-105">Method</span></span>|<span data-ttu-id="096cf-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="096cf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="096cf-107">GetMetadata-Methode</span><span class="sxs-lookup"><span data-stu-id="096cf-107">GetMetadata Method</span></span>](iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="096cf-108">Ruft die Metadaten eines Bilds aus dem Ziel Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="096cf-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="096cf-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="096cf-109">Remarks</span></span>  
 <span data-ttu-id="096cf-110">Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="096cf-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="096cf-111">Beispielsweise unterscheidet sich die Implementierung für einen Live Prozess von der eines Speicher Abbilds.</span><span class="sxs-lookup"><span data-stu-id="096cf-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="096cf-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="096cf-112">Requirements</span></span>  
 <span data-ttu-id="096cf-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="096cf-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="096cf-114">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="096cf-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="096cf-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="096cf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="096cf-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="096cf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="096cf-117">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="096cf-117">See also</span></span>

- [<span data-ttu-id="096cf-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="096cf-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
