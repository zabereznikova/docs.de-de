---
title: EmitManifest-Methode
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 051b5f47db05301f3a3326a2cc4cc5cf5c8b1ec2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137825"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="5cad8-102">EmitManifest-Methode</span><span class="sxs-lookup"><span data-stu-id="5cad8-102">EmitManifest Method</span></span>
<span data-ttu-id="5cad8-103">Gibt das endgültige Manifest an.</span><span class="sxs-lookup"><span data-stu-id="5cad8-103">Emits the final manifest.</span></span> <span data-ttu-id="5cad8-104">Rufen Sie diese Methode auf, nachdem alle anderen Dateien importiert, und alle Optionen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5cad8-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="5cad8-105">Rufen Sie diese Methode nicht für die ungebundenen Modulen.</span><span class="sxs-lookup"><span data-stu-id="5cad8-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cad8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5cad8-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cad8-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="5cad8-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="5cad8-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="5cad8-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="5cad8-109">Empfängt die Größe, die in der Assemblydatei Reservieren von abgerufen [StrongNameSignatureSize-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="5cad8-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="5cad8-110">Empfängt optional das Assemblymanifesttoken.</span><span class="sxs-lookup"><span data-stu-id="5cad8-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5cad8-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5cad8-111">Return Value</span></span>  
 <span data-ttu-id="5cad8-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="5cad8-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cad8-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5cad8-113">Requirements</span></span>  
 <span data-ttu-id="5cad8-114">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="5cad8-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cad8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cad8-115">See also</span></span>

- [<span data-ttu-id="5cad8-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5cad8-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="5cad8-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5cad8-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="5cad8-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="5cad8-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
