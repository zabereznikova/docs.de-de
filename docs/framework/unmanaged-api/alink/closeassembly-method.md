---
title: CloseAssembly-Methode
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
ms.openlocfilehash: 70dca19075d8c896408ec78f89549b0c539280de
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446582"
---
# <a name="closeassembly-method"></a><span data-ttu-id="e41ce-102">CloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="e41ce-102">CloseAssembly Method</span></span>
<span data-ttu-id="e41ce-103">Schließt assemblyvorgänge ab.</span><span class="sxs-lookup"><span data-stu-id="e41ce-103">Finalizes assembly operations.</span></span> <span data-ttu-id="e41ce-104">Diese Methode wird aufgerufen, bevor eine neue Assembly oder ein ungebundenes Modul gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="e41ce-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e41ce-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e41ce-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e41ce-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e41ce-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e41ce-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="e41ce-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e41ce-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e41ce-108">Return Value</span></span>  
 <span data-ttu-id="e41ce-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="e41ce-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e41ce-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e41ce-110">Requirements</span></span>  
 <span data-ttu-id="e41ce-111">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="e41ce-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e41ce-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e41ce-112">See also</span></span>

- [<span data-ttu-id="e41ce-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e41ce-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e41ce-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e41ce-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e41ce-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="e41ce-115">ALink API</span></span>](index.md)
