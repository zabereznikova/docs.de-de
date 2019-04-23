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
ms.openlocfilehash: 196a57b3e919ea4ccbc0b91e5b6f281ad3c30b62
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118156"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="a0ecd-102">FreeWin32ResBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="a0ecd-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="a0ecd-103">Gibt die Win32-Ressourcen-Blob und die zugeordneten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="a0ecd-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0ecd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0ecd-104">Syntax</span></span>  
  
```  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0ecd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0ecd-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="a0ecd-106">Die Ressourcen-Blob freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a0ecd-106">The resource blob to be released.</span></span> <span data-ttu-id="a0ecd-107">Diese Methode weist den Blob-Zeiger auf NULL.</span><span class="sxs-lookup"><span data-stu-id="a0ecd-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0ecd-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a0ecd-108">Return Value</span></span>  
 <span data-ttu-id="a0ecd-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="a0ecd-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0ecd-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0ecd-110">Requirements</span></span>  
 <span data-ttu-id="a0ecd-111">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="a0ecd-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ecd-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0ecd-112">See also</span></span>

- [<span data-ttu-id="a0ecd-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0ecd-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a0ecd-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0ecd-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a0ecd-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="a0ecd-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
