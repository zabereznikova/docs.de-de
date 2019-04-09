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
ms.openlocfilehash: 94c1c083d010cd82fd9e9e2f02b23e81d88fedd5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116440"
---
# <a name="closeassembly-method"></a><span data-ttu-id="4c992-102">CloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="4c992-102">CloseAssembly Method</span></span>
<span data-ttu-id="4c992-103">Schließt die Vorgänge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="4c992-103">Finalizes assembly operations.</span></span> <span data-ttu-id="4c992-104">Rufen Sie diese Methode, bevor Sie beginnen, eine neue Assembly oder ein ungebundenes Modul.</span><span class="sxs-lookup"><span data-stu-id="4c992-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c992-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c992-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c992-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4c992-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4c992-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="4c992-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c992-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4c992-108">Return Value</span></span>  
 <span data-ttu-id="4c992-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="4c992-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c992-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c992-110">Requirements</span></span>  
 <span data-ttu-id="4c992-111">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="4c992-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c992-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c992-112">See also</span></span>

- [<span data-ttu-id="4c992-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4c992-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="4c992-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4c992-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="4c992-115">ALink-API</span><span class="sxs-lookup"><span data-stu-id="4c992-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
