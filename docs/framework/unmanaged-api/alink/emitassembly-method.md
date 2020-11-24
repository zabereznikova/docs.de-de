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
ms.openlocfilehash: b85b2576660f77eb901c504d398e8bc7909882f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676373"
---
# <a name="emitassembly-method"></a><span data-ttu-id="6f9af-102">EmitAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="6f9af-102">EmitAssembly Method</span></span>

<span data-ttu-id="6f9af-103">Erstellt die Assembly.</span><span class="sxs-lookup"><span data-stu-id="6f9af-103">Creates the assembly.</span></span> <span data-ttu-id="6f9af-104">Diese Methode wird aufgerufen, nachdem alle anderen Dateien mit Ausnahme der Assemblydatei geschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="6f9af-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="6f9af-105">Wenn nicht gebundene Module erzeugt werden, wird diese Methode nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6f9af-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f9af-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f9af-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f9af-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f9af-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="6f9af-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="6f9af-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f9af-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6f9af-109">Return Value</span></span>  

 <span data-ttu-id="6f9af-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="6f9af-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f9af-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6f9af-111">Requirements</span></span>  

 <span data-ttu-id="6f9af-112">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="6f9af-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f9af-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f9af-113">See also</span></span>

- [<span data-ttu-id="6f9af-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f9af-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6f9af-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f9af-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6f9af-116">ALink-API</span><span class="sxs-lookup"><span data-stu-id="6f9af-116">ALink API</span></span>](index.md)
