---
title: EmitAssembly-Methode
ms.date: 03/30/2017
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssembly
helpviewer_keywords:
- EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1cd1c077a8f2a5fe3b2b46c2e1da2e92b5a797a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402056"
---
# <a name="emitassembly-method"></a><span data-ttu-id="18538-102">EmitAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="18538-102">EmitAssembly Method</span></span>
<span data-ttu-id="18538-103">Erstellt die Assembly an.</span><span class="sxs-lookup"><span data-stu-id="18538-103">Creates the assembly.</span></span> <span data-ttu-id="18538-104">Aufgerufen Sie diese Methode wird, nachdem alle anderen Dateien mit Ausnahme der Assemblydatei geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="18538-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="18538-105">Rufen Sie diese Methode nicht, wenn ungebundene Module erstellen.</span><span class="sxs-lookup"><span data-stu-id="18538-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18538-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="18538-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18538-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="18538-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="18538-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="18538-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18538-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="18538-109">Return Value</span></span>  
 <span data-ttu-id="18538-110">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="18538-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18538-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="18538-111">Requirements</span></span>  
 <span data-ttu-id="18538-112">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="18538-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18538-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18538-113">See Also</span></span>  
 [<span data-ttu-id="18538-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="18538-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="18538-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="18538-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="18538-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="18538-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
