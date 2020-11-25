---
title: CloseEnum-Methode
ms.date: 03/30/2017
api_name:
- CloseEnum
- IALink.CloseEnum
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseEnum
helpviewer_keywords:
- CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type:
- apiref
ms.openlocfilehash: 59b1ec3f9ca382ef13680e3aad4d0c0c0e175f1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716966"
---
# <a name="closeenum-method"></a><span data-ttu-id="650a3-102">CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="650a3-102">CloseEnum Method</span></span>

<span data-ttu-id="650a3-103">Schließt die angegeben Enumeration und gibt zugeordnete Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="650a3-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="650a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="650a3-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="650a3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="650a3-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="650a3-106">Handle der Enumeration, die geschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="650a3-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="650a3-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="650a3-107">Return Value</span></span>  

 <span data-ttu-id="650a3-108">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="650a3-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="650a3-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="650a3-109">Requirements</span></span>  

 <span data-ttu-id="650a3-110">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="650a3-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="650a3-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="650a3-111">See also</span></span>

- [<span data-ttu-id="650a3-112">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="650a3-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="650a3-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="650a3-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="650a3-114">ALink-API</span><span class="sxs-lookup"><span data-stu-id="650a3-114">ALink API</span></span>](index.md)
