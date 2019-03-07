---
title: FreeWin32ResBlob-Methode
ms.date: 03/30/2017
api_name:
- IALink.FreeWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- FreeWin32ResBlob
helpviewer_keywords:
- FreeWin32ResBlob method
ms.assetid: d941102b-2679-4c49-b15e-c0fc9c53e11f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e52984e12f22486212f0a2ec02d452a77242400e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491827"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="4bcbd-102">FreeWin32ResBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="4bcbd-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="4bcbd-103">Gibt die Win32-Ressourcen-Blob und die zugeordneten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bcbd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4bcbd-104">Syntax</span></span>  
  
```  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bcbd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4bcbd-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="4bcbd-106">Die Ressourcen-Blob freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-106">The resource blob to be released.</span></span> <span data-ttu-id="4bcbd-107">Diese Methode weist den Blob-Zeiger auf NULL.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4bcbd-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4bcbd-108">Return Value</span></span>  
 <span data-ttu-id="4bcbd-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="4bcbd-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bcbd-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4bcbd-110">Requirements</span></span>  
 <span data-ttu-id="4bcbd-111">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="4bcbd-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bcbd-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bcbd-112">See also</span></span>
- [<span data-ttu-id="4bcbd-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4bcbd-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="4bcbd-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4bcbd-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="4bcbd-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="4bcbd-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
