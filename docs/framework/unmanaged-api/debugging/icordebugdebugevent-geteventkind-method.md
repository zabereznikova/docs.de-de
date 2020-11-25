---
title: ICorDebugDebugEvent::GetEventKind-Methode
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 7876dc6ec5ecee52b64e54e1c42533f8348e4dc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713677"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="6898c-102">ICorDebugDebugEvent::GetEventKind-Methode</span><span class="sxs-lookup"><span data-stu-id="6898c-102">ICorDebugDebugEvent::GetEventKind Method</span></span>

<span data-ttu-id="6898c-103">Gibt an, welche Art von Ereignis dieses `ICorDebugDebugEvent`-Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="6898c-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6898c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6898c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6898c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6898c-105">Parameters</span></span>  

 <span data-ttu-id="6898c-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="6898c-106">pDebugEventKind</span></span>  
 <span data-ttu-id="6898c-107">Ein Zeiger auf einen [cordebugdebugeventkind](cordebugdebugeventkind-enumeration.md) -Enumerationsmember, der den Ereignistyp angibt.</span><span class="sxs-lookup"><span data-stu-id="6898c-107">A pointer to a [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6898c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6898c-108">Remarks</span></span>  

 <span data-ttu-id="6898c-109">Basierend auf dem `pDebugEventKind`-Wert können Sie `QueryInterface` aufrufen, um eine präzisere Debug-Ereignisschnittstelle abzurufen, welche zusätzliche Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="6898c-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6898c-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6898c-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6898c-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6898c-111">Requirements</span></span>  

 <span data-ttu-id="6898c-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6898c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6898c-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6898c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6898c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6898c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6898c-115">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6898c-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6898c-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6898c-116">See also</span></span>

- [<span data-ttu-id="6898c-117">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6898c-117">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="6898c-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6898c-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
