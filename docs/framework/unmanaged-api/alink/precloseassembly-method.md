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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e1aeffbd5d5b22bea87dd7a49a3268822ce84d38
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481173"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="ae01d-102">PreCloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="ae01d-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="ae01d-103">Schließt die Assemblydatei an.</span><span class="sxs-lookup"><span data-stu-id="ae01d-103">Closes the assembly file.</span></span> <span data-ttu-id="ae01d-104">Rufen Sie diese Methode, nach dem schließen alle anderen Dateien, jedoch vor dem Schließen der Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="ae01d-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="ae01d-105">Rufen Sie diese Methode nicht für die ungebundenen Modulen.</span><span class="sxs-lookup"><span data-stu-id="ae01d-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae01d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae01d-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae01d-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="ae01d-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ae01d-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="ae01d-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae01d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ae01d-109">Return Value</span></span>  
 <span data-ttu-id="ae01d-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="ae01d-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae01d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ae01d-111">Requirements</span></span>  
 <span data-ttu-id="ae01d-112">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="ae01d-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae01d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae01d-113">See also</span></span>
- [<span data-ttu-id="ae01d-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ae01d-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ae01d-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ae01d-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ae01d-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="ae01d-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
