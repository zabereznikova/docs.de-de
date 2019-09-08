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
ms.openlocfilehash: a2adf53d1e29fda077cdcf7b79891f6271993109
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787582"
---
# <a name="emitassembly-method"></a><span data-ttu-id="161fc-102">EmitAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="161fc-102">EmitAssembly Method</span></span>
<span data-ttu-id="161fc-103">Erstellt die Assembly.</span><span class="sxs-lookup"><span data-stu-id="161fc-103">Creates the assembly.</span></span> <span data-ttu-id="161fc-104">Diese Methode wird aufgerufen, nachdem alle anderen Dateien mit Ausnahme der Assemblydatei geschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="161fc-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="161fc-105">Wenn nicht gebundene Module erzeugt werden, wird diese Methode nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="161fc-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="161fc-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="161fc-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="161fc-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="161fc-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="161fc-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="161fc-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="161fc-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="161fc-109">Return Value</span></span>  
 <span data-ttu-id="161fc-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="161fc-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="161fc-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="161fc-111">Requirements</span></span>  
 <span data-ttu-id="161fc-112">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="161fc-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="161fc-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="161fc-113">See also</span></span>

- [<span data-ttu-id="161fc-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="161fc-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="161fc-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="161fc-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="161fc-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="161fc-116">ALink API</span></span>](index.md)
