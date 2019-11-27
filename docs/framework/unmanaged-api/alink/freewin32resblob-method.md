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
ms.openlocfilehash: 2b1addc752c7238116e072c6e957d2b277ceb1e3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449398"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="268b0-102">FreeWin32ResBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="268b0-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="268b0-103">Gibt das Win32-ressourcenblob und zugehörige Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="268b0-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="268b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="268b0-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="268b0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="268b0-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="268b0-106">Das Ressourcen-BLOB, das freigegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="268b0-106">The resource blob to be released.</span></span> <span data-ttu-id="268b0-107">Diese Methode weist den BLOB-Zeiger NULL zu.</span><span class="sxs-lookup"><span data-stu-id="268b0-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="268b0-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="268b0-108">Return Value</span></span>  
 <span data-ttu-id="268b0-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="268b0-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="268b0-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="268b0-110">Requirements</span></span>  
 <span data-ttu-id="268b0-111">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="268b0-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="268b0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="268b0-112">See also</span></span>

- [<span data-ttu-id="268b0-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="268b0-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="268b0-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="268b0-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="268b0-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="268b0-115">ALink API</span></span>](index.md)
