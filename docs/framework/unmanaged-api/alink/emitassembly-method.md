---
title: EmitAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location: alink.dll
api_type: COM
f1_keywords: EmitAssembly
helpviewer_keywords: EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f012ea89fec0e64bc1639e6c47fb79249c25411a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="emitassembly-method"></a><span data-ttu-id="f7439-102">EmitAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="f7439-102">EmitAssembly Method</span></span>
<span data-ttu-id="f7439-103">Erstellt die Assembly an.</span><span class="sxs-lookup"><span data-stu-id="f7439-103">Creates the assembly.</span></span> <span data-ttu-id="f7439-104">Aufgerufen Sie diese Methode wird, nachdem alle anderen Dateien mit Ausnahme der Assemblydatei geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="f7439-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="f7439-105">Rufen Sie diese Methode nicht, wenn ungebundene Module erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7439-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7439-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7439-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7439-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="f7439-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f7439-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="f7439-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7439-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f7439-109">Return Value</span></span>  
 <span data-ttu-id="f7439-110">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f7439-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7439-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f7439-111">Requirements</span></span>  
 <span data-ttu-id="f7439-112">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="f7439-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7439-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7439-113">See Also</span></span>  
 [<span data-ttu-id="f7439-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7439-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="f7439-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7439-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="f7439-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="f7439-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
