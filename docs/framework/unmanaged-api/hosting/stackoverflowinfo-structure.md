---
title: StackOverflowInfo-Struktur
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: a8a57cfcaf36949d4d10c6ec267a5f55a2aee5eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729927"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="eb558-102">StackOverflowInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="eb558-102">StackOverflowInfo Structure</span></span>

<span data-ttu-id="eb558-103">Speichert den Typ des aufgetretenen Überlaufs und Informationen zu der Ausnahme, die aufgrund des Überlaufs ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="eb558-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb558-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb558-104">Syntax</span></span>  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="eb558-105">Member</span><span class="sxs-lookup"><span data-stu-id="eb558-105">Members</span></span>  
  
|<span data-ttu-id="eb558-106">Member</span><span class="sxs-lookup"><span data-stu-id="eb558-106">Member</span></span>|<span data-ttu-id="eb558-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eb558-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="eb558-108">Ein Wert der [StackOverflowType](stackoverflowtype-enumeration.md) -Enumeration, der den Typ des Überlaufs angibt.</span><span class="sxs-lookup"><span data-stu-id="eb558-108">A value of the [StackOverflowType](stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="eb558-109">Ein Zeiger auf ein Win32 `EXCEPTION_POINTERS` -Objekt, das einen Ausnahme Daten Satz mit einer Computer unabhängigen Beschreibung einer Ausnahme und einem Kontext Daten Satz mit einer vom Computer abhängigen Beschreibung des Prozessor Kontexts zum Zeitpunkt der Ausnahme enthält.</span><span class="sxs-lookup"><span data-stu-id="eb558-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb558-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eb558-110">Remarks</span></span>  

 <span data-ttu-id="eb558-111">Ein- `StackOverflowInfo` Objekt wird für-Ereignisse an die [iaktiononclrevent:: OnEvent](iactiononclrevent-onevent-method.md) -Methode weitergegeben `Event_StackOverflow` .</span><span class="sxs-lookup"><span data-stu-id="eb558-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb558-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="eb558-112">Requirements</span></span>  

 <span data-ttu-id="eb558-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb558-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb558-114">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="eb558-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="eb558-115">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="eb558-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb558-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb558-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb558-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb558-117">See also</span></span>

- [<span data-ttu-id="eb558-118">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="eb558-118">Hosting Structures</span></span>](hosting-structures.md)
