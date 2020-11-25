---
title: ComCallUnmarshal-Co-Klasse
ms.date: 03/30/2017
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
ms.openlocfilehash: 90bcf4f37631e0246e58cc14bfcd331d981e4713
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731721"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="bb53e-102">ComCallUnmarshal-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="bb53e-102">ComCallUnmarshal Coclass</span></span>

<span data-ttu-id="bb53e-103">Stellt Schnittstellen zum Verwalten des Marshalling von Schnittstellen Zeigern bereit.</span><span class="sxs-lookup"><span data-stu-id="bb53e-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb53e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb53e-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="bb53e-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bb53e-105">Interfaces</span></span>  
  
|<span data-ttu-id="bb53e-106">Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb53e-106">Interface</span></span>|<span data-ttu-id="bb53e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bb53e-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="bb53e-108">Stellt Methoden zum Erstellen, initialisieren und Verwalten eines Proxys in einem Client Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="bb53e-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb53e-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bb53e-109">Requirements</span></span>  

 <span data-ttu-id="bb53e-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb53e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb53e-111">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="bb53e-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="bb53e-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bb53e-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb53e-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb53e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb53e-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb53e-114">See also</span></span>

- [<span data-ttu-id="bb53e-115">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="bb53e-115">Hosting Coclasses</span></span>](hosting-coclasses.md)
