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
ms.openlocfilehash: 642391bce99328f3700d1783054943b6a450b22b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789015"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="86062-102">ICLRMetadataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="86062-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="86062-103">Wird von der Ebene der Datenzugriffs Dienste verwendet, um Metadaten von Assemblys in einem Ziel Prozess zu suchen.</span><span class="sxs-lookup"><span data-stu-id="86062-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="86062-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="86062-104">Methods</span></span>  
  
|<span data-ttu-id="86062-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="86062-105">Method</span></span>|<span data-ttu-id="86062-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86062-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="86062-107">GetMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="86062-107">GetMetadata Method</span></span>](iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="86062-108">Ruft die Metadaten eines Bilds aus dem Ziel Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="86062-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86062-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86062-109">Remarks</span></span>  
 <span data-ttu-id="86062-110">Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="86062-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="86062-111">Beispielsweise unterscheidet sich die Implementierung für einen Live Prozess von der eines Speicher Abbilds.</span><span class="sxs-lookup"><span data-stu-id="86062-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86062-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="86062-112">Requirements</span></span>  
 <span data-ttu-id="86062-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86062-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86062-114">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="86062-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="86062-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86062-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86062-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86062-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86062-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86062-117">See also</span></span>

- [<span data-ttu-id="86062-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="86062-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
