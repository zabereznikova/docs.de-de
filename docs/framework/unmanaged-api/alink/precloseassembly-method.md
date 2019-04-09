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
ms.openlocfilehash: aab42e939651d75b1933962d72ba8bec1090f52d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184508"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="e2ca6-102">PreCloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="e2ca6-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="e2ca6-103">Schließt die Assemblydatei an.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-103">Closes the assembly file.</span></span> <span data-ttu-id="e2ca6-104">Rufen Sie diese Methode, nach dem schließen alle anderen Dateien, jedoch vor dem Schließen der Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="e2ca6-105">Rufen Sie diese Methode nicht für die ungebundenen Modulen.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2ca6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2ca6-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2ca6-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2ca6-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e2ca6-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2ca6-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e2ca6-109">Return Value</span></span>  
 <span data-ttu-id="e2ca6-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2ca6-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2ca6-111">Requirements</span></span>  
 <span data-ttu-id="e2ca6-112">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ca6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2ca6-113">See also</span></span>

- [<span data-ttu-id="e2ca6-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e2ca6-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e2ca6-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e2ca6-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e2ca6-116">ALink-API</span><span class="sxs-lookup"><span data-stu-id="e2ca6-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
