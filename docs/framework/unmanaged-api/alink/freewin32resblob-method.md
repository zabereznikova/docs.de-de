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
ms.openlocfilehash: 6f7ffef0af68bee3e7184fe8bde9264f570230be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573635"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="02e6b-102">FreeWin32ResBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="02e6b-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="02e6b-103">Gibt die Win32-Ressourcen-Blob und die zugeordneten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="02e6b-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02e6b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="02e6b-104">Syntax</span></span>  
  
```  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02e6b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="02e6b-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="02e6b-106">Die Ressourcen-Blob freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="02e6b-106">The resource blob to be released.</span></span> <span data-ttu-id="02e6b-107">Diese Methode weist den Blob-Zeiger auf NULL.</span><span class="sxs-lookup"><span data-stu-id="02e6b-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02e6b-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="02e6b-108">Return Value</span></span>  
 <span data-ttu-id="02e6b-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="02e6b-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02e6b-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="02e6b-110">Requirements</span></span>  
 <span data-ttu-id="02e6b-111">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="02e6b-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02e6b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02e6b-112">See also</span></span>
- [<span data-ttu-id="02e6b-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="02e6b-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="02e6b-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="02e6b-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="02e6b-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="02e6b-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
