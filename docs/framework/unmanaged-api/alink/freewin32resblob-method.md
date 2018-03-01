---
title: FreeWin32ResBlob-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cdecedf319ad235bd635dd1d2edf600b0d00dbb7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="c5869-102">FreeWin32ResBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="c5869-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="c5869-103">Gibt die Win32-Ressource-Blob und die zugeordneten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="c5869-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5869-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5869-104">Syntax</span></span>  
  
```  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5869-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c5869-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="c5869-106">Das Blob Ressourcen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c5869-106">The resource blob to be released.</span></span> <span data-ttu-id="c5869-107">Diese Methode weist der Blob-Zeiger auf NULL.</span><span class="sxs-lookup"><span data-stu-id="c5869-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5869-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c5869-108">Return Value</span></span>  
 <span data-ttu-id="c5869-109">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c5869-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5869-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c5869-110">Requirements</span></span>  
 <span data-ttu-id="c5869-111">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="c5869-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5869-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5869-112">See Also</span></span>  
 [<span data-ttu-id="c5869-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5869-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="c5869-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5869-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="c5869-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="c5869-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
