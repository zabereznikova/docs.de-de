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
ms.openlocfilehash: 4e8aeef3520c4d5c9735b2c8975ac1e39470ba93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717019"
---
# <a name="closeassembly-method"></a><span data-ttu-id="6a699-102">CloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="6a699-102">CloseAssembly Method</span></span>

<span data-ttu-id="6a699-103">Schließt assemblyvorgänge ab.</span><span class="sxs-lookup"><span data-stu-id="6a699-103">Finalizes assembly operations.</span></span> <span data-ttu-id="6a699-104">Diese Methode wird aufgerufen, bevor eine neue Assembly oder ein ungebundenes Modul gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="6a699-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a699-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a699-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a699-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6a699-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="6a699-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="6a699-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a699-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6a699-108">Return Value</span></span>  

 <span data-ttu-id="6a699-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="6a699-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a699-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6a699-110">Requirements</span></span>  

 <span data-ttu-id="6a699-111">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="6a699-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a699-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a699-112">See also</span></span>

- [<span data-ttu-id="6a699-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a699-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6a699-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a699-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6a699-115">ALink-API</span><span class="sxs-lookup"><span data-stu-id="6a699-115">ALink API</span></span>](index.md)
