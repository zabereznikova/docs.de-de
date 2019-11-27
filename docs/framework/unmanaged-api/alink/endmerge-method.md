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
ms.openlocfilehash: cacf7eab1e53f590ad46fd98ed2f5dcbd14cd30a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434410"
---
# <a name="endmerge-method"></a><span data-ttu-id="6b6f4-102">EndMerge-Methode</span><span class="sxs-lookup"><span data-stu-id="6b6f4-102">EndMerge Method</span></span>
<span data-ttu-id="6b6f4-103">Gibt an, dass alle benutzerdefinierten Attribute im Ausgabebereich zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="6b6f4-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b6f4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b6f4-104">Syntax</span></span>  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b6f4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b6f4-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6b6f4-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="6b6f4-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b6f4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6b6f4-107">Return Value</span></span>  
 <span data-ttu-id="6b6f4-108">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="6b6f4-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b6f4-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6b6f4-109">Requirements</span></span>  
 <span data-ttu-id="6b6f4-110">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="6b6f4-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b6f4-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b6f4-111">See also</span></span>

- [<span data-ttu-id="6b6f4-112">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b6f4-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6b6f4-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b6f4-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6b6f4-114">Alink-API</span><span class="sxs-lookup"><span data-stu-id="6b6f4-114">ALink API</span></span>](index.md)
