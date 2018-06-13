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
ms.openlocfilehash: 82421fa83a6f0d24492d70f961e731b679c25728
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400717"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="63b75-102">PreCloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="63b75-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="63b75-103">Schließt die Assemblydatei an.</span><span class="sxs-lookup"><span data-stu-id="63b75-103">Closes the assembly file.</span></span> <span data-ttu-id="63b75-104">Rufen Sie diese Methode aus, schließen Sie alle anderen Dateien, jedoch vor dem Schließen der Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="63b75-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="63b75-105">Rufen Sie diese Methode nicht für ungebundenen Modulen.</span><span class="sxs-lookup"><span data-stu-id="63b75-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63b75-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="63b75-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63b75-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="63b75-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="63b75-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="63b75-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63b75-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="63b75-109">Return Value</span></span>  
 <span data-ttu-id="63b75-110">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="63b75-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63b75-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="63b75-111">Requirements</span></span>  
 <span data-ttu-id="63b75-112">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="63b75-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63b75-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63b75-113">See Also</span></span>  
 [<span data-ttu-id="63b75-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63b75-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="63b75-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63b75-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="63b75-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="63b75-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
