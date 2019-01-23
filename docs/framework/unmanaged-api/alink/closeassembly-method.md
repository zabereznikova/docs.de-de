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
ms.openlocfilehash: aa415926f4a818f697812f1a3c5531cb0ab7081b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510168"
---
# <a name="closeassembly-method"></a><span data-ttu-id="5fa39-102">CloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="5fa39-102">CloseAssembly Method</span></span>
<span data-ttu-id="5fa39-103">Schließt die Vorgänge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="5fa39-103">Finalizes assembly operations.</span></span> <span data-ttu-id="5fa39-104">Rufen Sie diese Methode, bevor Sie beginnen, eine neue Assembly oder ein ungebundenes Modul.</span><span class="sxs-lookup"><span data-stu-id="5fa39-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fa39-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5fa39-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5fa39-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5fa39-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="5fa39-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="5fa39-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5fa39-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5fa39-108">Return Value</span></span>  
 <span data-ttu-id="5fa39-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="5fa39-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fa39-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5fa39-110">Requirements</span></span>  
 <span data-ttu-id="5fa39-111">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="5fa39-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa39-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fa39-112">See also</span></span>
- [<span data-ttu-id="5fa39-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5fa39-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="5fa39-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5fa39-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="5fa39-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="5fa39-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
