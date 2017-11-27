---
title: EmitManifest-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EmitManifest
- IALink.EmitManifest
api_location: alink.dll
api_type: COM
f1_keywords: EmitManifest
helpviewer_keywords: EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 03ef815f03a65cbf7e2dc936b21848e206132add
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="emitmanifest-method"></a><span data-ttu-id="a0491-102">EmitManifest-Methode</span><span class="sxs-lookup"><span data-stu-id="a0491-102">EmitManifest Method</span></span>
<span data-ttu-id="a0491-103">Gibt das endgültige Manifest an.</span><span class="sxs-lookup"><span data-stu-id="a0491-103">Emits the final manifest.</span></span> <span data-ttu-id="a0491-104">Rufen Sie diese Methode nach dem Importieren alle anderen Dateien und alle Optionen festlegen.</span><span class="sxs-lookup"><span data-stu-id="a0491-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="a0491-105">Rufen Sie diese Methode nicht für ungebundenen Modulen.</span><span class="sxs-lookup"><span data-stu-id="a0491-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0491-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0491-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0491-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0491-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a0491-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="a0491-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="a0491-109">Empfängt die Größe, in der Assemblydatei reservieren entnommen [StrongNameSignatureSize-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="a0491-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="a0491-110">Optional empfängt das Assembly-manifest-Token.</span><span class="sxs-lookup"><span data-stu-id="a0491-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0491-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a0491-111">Return Value</span></span>  
 <span data-ttu-id="a0491-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a0491-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0491-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0491-113">Requirements</span></span>  
 <span data-ttu-id="a0491-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="a0491-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0491-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0491-115">See Also</span></span>  
 [<span data-ttu-id="a0491-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0491-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a0491-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0491-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="a0491-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="a0491-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
