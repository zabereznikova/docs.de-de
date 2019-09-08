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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b7828c86018724bb934de99cab4617f9885fdca6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787608"
---
# <a name="closeassembly-method"></a><span data-ttu-id="60156-102">CloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="60156-102">CloseAssembly Method</span></span>
<span data-ttu-id="60156-103">Schließt assemblyvorgänge ab.</span><span class="sxs-lookup"><span data-stu-id="60156-103">Finalizes assembly operations.</span></span> <span data-ttu-id="60156-104">Diese Methode wird aufgerufen, bevor eine neue Assembly oder ein ungebundenes Modul gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="60156-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60156-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="60156-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="60156-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="60156-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="60156-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="60156-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60156-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="60156-108">Return Value</span></span>  
 <span data-ttu-id="60156-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="60156-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60156-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60156-110">Requirements</span></span>  
 <span data-ttu-id="60156-111">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="60156-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60156-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60156-112">See also</span></span>

- [<span data-ttu-id="60156-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60156-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="60156-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60156-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="60156-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="60156-115">ALink API</span></span>](index.md)
