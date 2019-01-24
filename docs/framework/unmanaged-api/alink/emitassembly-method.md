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
ms.openlocfilehash: d73c158fa9d7b5574e4f875b8d51e932e30041b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572239"
---
# <a name="emitassembly-method"></a><span data-ttu-id="e2861-102">EmitAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="e2861-102">EmitAssembly Method</span></span>
<span data-ttu-id="e2861-103">Erstellt die Assembly an.</span><span class="sxs-lookup"><span data-stu-id="e2861-103">Creates the assembly.</span></span> <span data-ttu-id="e2861-104">Rufen Sie diese Methode auf, nachdem alle anderen Dateien mit Ausnahme der Assemblydatei geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="e2861-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="e2861-105">Rufen Sie diese Methode nicht auf, wenn ungebundene Modulen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e2861-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2861-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2861-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2861-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2861-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e2861-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="e2861-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2861-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e2861-109">Return Value</span></span>  
 <span data-ttu-id="e2861-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="e2861-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2861-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2861-111">Requirements</span></span>  
 <span data-ttu-id="e2861-112">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="e2861-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2861-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2861-113">See also</span></span>
- [<span data-ttu-id="e2861-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e2861-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e2861-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e2861-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e2861-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="e2861-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
