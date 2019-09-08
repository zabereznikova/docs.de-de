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
ms.openlocfilehash: ea0fbceb1e778a2f26e0625a337b803f417b59eb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777248"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="2005f-102">FreeWin32ResBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="2005f-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="2005f-103">Gibt das Win32-ressourcenblob und zugehörige Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="2005f-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2005f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2005f-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2005f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2005f-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="2005f-106">Das Ressourcen-BLOB, das freigegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="2005f-106">The resource blob to be released.</span></span> <span data-ttu-id="2005f-107">Diese Methode weist den BLOB-Zeiger NULL zu.</span><span class="sxs-lookup"><span data-stu-id="2005f-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2005f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2005f-108">Return Value</span></span>  
 <span data-ttu-id="2005f-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="2005f-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2005f-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2005f-110">Requirements</span></span>  
 <span data-ttu-id="2005f-111">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="2005f-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2005f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2005f-112">See also</span></span>

- [<span data-ttu-id="2005f-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2005f-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="2005f-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2005f-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="2005f-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="2005f-115">ALink API</span></span>](index.md)
