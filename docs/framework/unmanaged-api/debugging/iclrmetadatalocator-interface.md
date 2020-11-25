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
ms.openlocfilehash: 69c52c13a4a0aca5094274de969ebed6e09651b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723505"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="ac57b-102">ICLRMetadataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac57b-102">ICLRMetadataLocator Interface</span></span>

<span data-ttu-id="ac57b-103">Wird von der Ebene der Datenzugriffs Dienste verwendet, um Metadaten von Assemblys in einem Ziel Prozess zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ac57b-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ac57b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ac57b-104">Methods</span></span>  
  
|<span data-ttu-id="ac57b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ac57b-105">Method</span></span>|<span data-ttu-id="ac57b-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ac57b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ac57b-107">GetMetadata-Methode</span><span class="sxs-lookup"><span data-stu-id="ac57b-107">GetMetadata Method</span></span>](iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="ac57b-108">Ruft die Metadaten eines Bilds aus dem Ziel Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="ac57b-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac57b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac57b-109">Remarks</span></span>  

 <span data-ttu-id="ac57b-110">Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren.</span><span class="sxs-lookup"><span data-stu-id="ac57b-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="ac57b-111">Beispielsweise unterscheidet sich die Implementierung für einen Live Prozess von der eines Speicher Abbilds.</span><span class="sxs-lookup"><span data-stu-id="ac57b-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac57b-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ac57b-112">Requirements</span></span>  

 <span data-ttu-id="ac57b-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac57b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac57b-114">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="ac57b-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ac57b-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac57b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac57b-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac57b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac57b-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ac57b-117">See also</span></span>

- [<span data-ttu-id="ac57b-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ac57b-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
