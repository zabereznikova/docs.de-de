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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184508"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="ec97a-102">PreCloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="ec97a-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="ec97a-103">Schließt die Assemblydatei an.</span><span class="sxs-lookup"><span data-stu-id="ec97a-103">Closes the assembly file.</span></span> <span data-ttu-id="ec97a-104">Rufen Sie diese Methode, nach dem schließen alle anderen Dateien, jedoch vor dem Schließen der Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="ec97a-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="ec97a-105">Rufen Sie diese Methode nicht für die ungebundenen Modulen.</span><span class="sxs-lookup"><span data-stu-id="ec97a-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec97a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec97a-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec97a-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec97a-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ec97a-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="ec97a-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec97a-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ec97a-109">Return Value</span></span>  
 <span data-ttu-id="ec97a-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="ec97a-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec97a-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec97a-111">Requirements</span></span>  
 <span data-ttu-id="ec97a-112">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="ec97a-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec97a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec97a-113">See also</span></span>

- [<span data-ttu-id="ec97a-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec97a-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ec97a-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec97a-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ec97a-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="ec97a-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
