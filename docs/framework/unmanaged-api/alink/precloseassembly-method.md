---
title: PreCloseAssembly-Methode
ms.date: 03/30/2017
api_name:
- IALink.PreCloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- PreCloseAssembly
helpviewer_keywords:
- PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type:
- apiref
ms.openlocfilehash: fcfd3e79bbb52837a333b5ffacf5c13ae60f2490
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445616"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="8f1f9-102">PreCloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="8f1f9-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="8f1f9-103">Schließt die Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="8f1f9-103">Closes the assembly file.</span></span> <span data-ttu-id="8f1f9-104">Ruft diese Methode auf, nachdem alle anderen Dateien, jedoch vor dem Schließen der Assemblydatei geschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="8f1f9-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="8f1f9-105">Diese Methode darf nicht für ungebundene Module aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8f1f9-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f1f9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f1f9-106">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f1f9-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f1f9-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="8f1f9-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="8f1f9-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f1f9-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8f1f9-109">Return Value</span></span>  
 <span data-ttu-id="8f1f9-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="8f1f9-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f1f9-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8f1f9-111">Requirements</span></span>  
 <span data-ttu-id="8f1f9-112">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="8f1f9-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f1f9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f1f9-113">See also</span></span>

- [<span data-ttu-id="8f1f9-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f1f9-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="8f1f9-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f1f9-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="8f1f9-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="8f1f9-116">ALink API</span></span>](index.md)
