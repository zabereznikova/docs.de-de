---
title: EmitManifest-Methode
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 11966eccfdbbdbab29d305915afd904a54f9c57b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="emitmanifest-method"></a><span data-ttu-id="bbadf-102">EmitManifest-Methode</span><span class="sxs-lookup"><span data-stu-id="bbadf-102">EmitManifest Method</span></span>
<span data-ttu-id="bbadf-103">Gibt das endgültige Manifest an.</span><span class="sxs-lookup"><span data-stu-id="bbadf-103">Emits the final manifest.</span></span> <span data-ttu-id="bbadf-104">Rufen Sie diese Methode nach dem Importieren alle anderen Dateien und alle Optionen festlegen.</span><span class="sxs-lookup"><span data-stu-id="bbadf-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="bbadf-105">Rufen Sie diese Methode nicht für ungebundenen Modulen.</span><span class="sxs-lookup"><span data-stu-id="bbadf-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbadf-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="bbadf-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbadf-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="bbadf-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="bbadf-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="bbadf-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="bbadf-109">Empfängt die Größe, in der Assemblydatei reservieren entnommen [StrongNameSignatureSize-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="bbadf-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="bbadf-110">Optional empfängt das Assembly-manifest-Token.</span><span class="sxs-lookup"><span data-stu-id="bbadf-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bbadf-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bbadf-111">Return Value</span></span>  
 <span data-ttu-id="bbadf-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bbadf-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbadf-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bbadf-113">Requirements</span></span>  
 <span data-ttu-id="bbadf-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="bbadf-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbadf-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bbadf-115">See Also</span></span>  
 [<span data-ttu-id="bbadf-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bbadf-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="bbadf-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bbadf-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="bbadf-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="bbadf-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
