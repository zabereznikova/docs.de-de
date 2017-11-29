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
ms.openlocfilehash: 3471c4ad2d06443e0f05dc344be5f791817f2d2f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="emitassembly-method"></a><span data-ttu-id="8f961-102">EmitAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="8f961-102">EmitAssembly Method</span></span>
<span data-ttu-id="8f961-103">Erstellt die Assembly an.</span><span class="sxs-lookup"><span data-stu-id="8f961-103">Creates the assembly.</span></span> <span data-ttu-id="8f961-104">Aufgerufen Sie diese Methode wird, nachdem alle anderen Dateien mit Ausnahme der Assemblydatei geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8f961-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="8f961-105">Rufen Sie diese Methode nicht, wenn ungebundene Module erstellen.</span><span class="sxs-lookup"><span data-stu-id="8f961-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f961-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f961-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f961-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f961-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="8f961-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="8f961-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f961-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8f961-109">Return Value</span></span>  
 <span data-ttu-id="8f961-110">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8f961-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f961-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f961-111">Requirements</span></span>  
 <span data-ttu-id="8f961-112">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="8f961-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f961-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f961-113">See Also</span></span>  
 [<span data-ttu-id="8f961-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f961-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="8f961-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f961-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="8f961-116">ALink-API</span><span class="sxs-lookup"><span data-stu-id="8f961-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
