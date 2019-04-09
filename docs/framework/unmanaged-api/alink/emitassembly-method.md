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
ms.openlocfilehash: bf7b54ab7a2318e8194bf39dbe41b864633ddb43
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212908"
---
# <a name="emitassembly-method"></a><span data-ttu-id="57aa4-102">EmitAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="57aa4-102">EmitAssembly Method</span></span>
<span data-ttu-id="57aa4-103">Erstellt die Assembly an.</span><span class="sxs-lookup"><span data-stu-id="57aa4-103">Creates the assembly.</span></span> <span data-ttu-id="57aa4-104">Rufen Sie diese Methode auf, nachdem alle anderen Dateien mit Ausnahme der Assemblydatei geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="57aa4-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="57aa4-105">Rufen Sie diese Methode nicht auf, wenn ungebundene Modulen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="57aa4-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57aa4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="57aa4-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="57aa4-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="57aa4-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="57aa4-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="57aa4-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57aa4-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="57aa4-109">Return Value</span></span>  
 <span data-ttu-id="57aa4-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="57aa4-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57aa4-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="57aa4-111">Requirements</span></span>  
 <span data-ttu-id="57aa4-112">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="57aa4-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57aa4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57aa4-113">See also</span></span>

- [<span data-ttu-id="57aa4-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57aa4-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="57aa4-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57aa4-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="57aa4-116">ALink-API</span><span class="sxs-lookup"><span data-stu-id="57aa4-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
