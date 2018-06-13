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
ms.openlocfilehash: 68698aab0fd0872c6e6f67e4ec531ab0226e784f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401952"
---
# <a name="closeassembly-method"></a><span data-ttu-id="c0807-102">CloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="c0807-102">CloseAssembly Method</span></span>
<span data-ttu-id="c0807-103">Schließt die Vorgänge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="c0807-103">Finalizes assembly operations.</span></span> <span data-ttu-id="c0807-104">Rufen Sie diese Methode, bevor Sie beginnen, eine neue Assembly oder ein ungebundener Modul.</span><span class="sxs-lookup"><span data-stu-id="c0807-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0807-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0807-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0807-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c0807-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c0807-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="c0807-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0807-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c0807-108">Return Value</span></span>  
 <span data-ttu-id="c0807-109">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c0807-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0807-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0807-110">Requirements</span></span>  
 <span data-ttu-id="c0807-111">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="c0807-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0807-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0807-112">See Also</span></span>  
 [<span data-ttu-id="c0807-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0807-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="c0807-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0807-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="c0807-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="c0807-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
