---
title: ICorDebugDebugEvent::GetEventKind-Methode
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 0c67f8bdce49b4e9200b501aaf00ae293cced7d7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783415"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="68691-102">ICorDebugDebugEvent::GetEventKind-Methode</span><span class="sxs-lookup"><span data-stu-id="68691-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="68691-103">Gibt an, welche Art von Ereignis dieses `ICorDebugDebugEvent`-Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="68691-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68691-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="68691-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68691-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="68691-105">Parameters</span></span>  
 <span data-ttu-id="68691-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="68691-106">pDebugEventKind</span></span>  
 <span data-ttu-id="68691-107">Ein Zeiger auf einen [cordebugdebugeventkind](cordebugdebugeventkind-enumeration.md) -Enumerationsmember, der den Ereignistyp angibt.</span><span class="sxs-lookup"><span data-stu-id="68691-107">A pointer to a [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68691-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68691-108">Remarks</span></span>  
 <span data-ttu-id="68691-109">Basierend auf dem `pDebugEventKind`-Wert können Sie `QueryInterface` aufrufen, um eine präzisere Debug-Ereignisschnittstelle abzurufen, welche zusätzliche Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="68691-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68691-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="68691-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68691-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68691-111">Requirements</span></span>  
 <span data-ttu-id="68691-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68691-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68691-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68691-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68691-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68691-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68691-115">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68691-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68691-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68691-116">See also</span></span>

- [<span data-ttu-id="68691-117">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68691-117">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="68691-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="68691-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
