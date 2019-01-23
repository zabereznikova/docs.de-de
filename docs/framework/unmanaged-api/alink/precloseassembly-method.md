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
ms.openlocfilehash: 6fab522adbdb1b50448dfabfd23d663fb223c6da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499196"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="4fc09-102">PreCloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="4fc09-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="4fc09-103">Schließt die Assemblydatei an.</span><span class="sxs-lookup"><span data-stu-id="4fc09-103">Closes the assembly file.</span></span> <span data-ttu-id="4fc09-104">Rufen Sie diese Methode, nach dem schließen alle anderen Dateien, jedoch vor dem Schließen der Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="4fc09-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="4fc09-105">Rufen Sie diese Methode nicht für die ungebundenen Modulen.</span><span class="sxs-lookup"><span data-stu-id="4fc09-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fc09-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4fc09-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4fc09-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="4fc09-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4fc09-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="4fc09-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4fc09-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4fc09-109">Return Value</span></span>  
 <span data-ttu-id="4fc09-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="4fc09-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fc09-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4fc09-111">Requirements</span></span>  
 <span data-ttu-id="4fc09-112">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="4fc09-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc09-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fc09-113">See also</span></span>
- [<span data-ttu-id="4fc09-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4fc09-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="4fc09-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4fc09-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="4fc09-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="4fc09-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
