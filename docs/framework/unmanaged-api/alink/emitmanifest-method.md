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
ms.openlocfilehash: 6df28cd3eaadfe62cd34e20e6e03d5a89e6bb425
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401208"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="a5a8b-102">EmitManifest-Methode</span><span class="sxs-lookup"><span data-stu-id="a5a8b-102">EmitManifest Method</span></span>
<span data-ttu-id="a5a8b-103">Gibt das endgültige Manifest an.</span><span class="sxs-lookup"><span data-stu-id="a5a8b-103">Emits the final manifest.</span></span> <span data-ttu-id="a5a8b-104">Rufen Sie diese Methode nach dem Importieren alle anderen Dateien und alle Optionen festlegen.</span><span class="sxs-lookup"><span data-stu-id="a5a8b-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="a5a8b-105">Rufen Sie diese Methode nicht für ungebundenen Modulen.</span><span class="sxs-lookup"><span data-stu-id="a5a8b-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5a8b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5a8b-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5a8b-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="a5a8b-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a5a8b-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="a5a8b-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="a5a8b-109">Empfängt die Größe, in der Assemblydatei reservieren entnommen [StrongNameSignatureSize-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="a5a8b-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="a5a8b-110">Optional empfängt das Assembly-manifest-Token.</span><span class="sxs-lookup"><span data-stu-id="a5a8b-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5a8b-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a5a8b-111">Return Value</span></span>  
 <span data-ttu-id="a5a8b-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a5a8b-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5a8b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a5a8b-113">Requirements</span></span>  
 <span data-ttu-id="a5a8b-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="a5a8b-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5a8b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5a8b-115">See Also</span></span>  
 [<span data-ttu-id="a5a8b-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a5a8b-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a5a8b-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a5a8b-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="a5a8b-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="a5a8b-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
