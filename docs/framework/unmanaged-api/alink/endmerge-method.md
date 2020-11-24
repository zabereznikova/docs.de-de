---
title: EndMerge-Methode
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
ms.openlocfilehash: ed4ac7b12caa0dd78b79554258de62b8752553e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684927"
---
# <a name="endmerge-method"></a><span data-ttu-id="23a9e-102">EndMerge-Methode</span><span class="sxs-lookup"><span data-stu-id="23a9e-102">EndMerge Method</span></span>

<span data-ttu-id="23a9e-103">Gibt an, dass alle benutzerdefinierten Attribute im Ausgabebereich zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="23a9e-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23a9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23a9e-104">Syntax</span></span>  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="23a9e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23a9e-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="23a9e-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="23a9e-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23a9e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="23a9e-107">Return Value</span></span>  

 <span data-ttu-id="23a9e-108">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="23a9e-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23a9e-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="23a9e-109">Requirements</span></span>  

 <span data-ttu-id="23a9e-110">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="23a9e-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23a9e-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23a9e-111">See also</span></span>

- [<span data-ttu-id="23a9e-112">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23a9e-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="23a9e-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23a9e-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="23a9e-114">ALink-API</span><span class="sxs-lookup"><span data-stu-id="23a9e-114">ALink API</span></span>](index.md)
