---
title: CALL_ID-Struktur
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2823c018ff22607052cb9a298f69dbd0c4fe2c23
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769498"
---
# <a name="callid-structure"></a><span data-ttu-id="e80a3-102">CALL_ID-Struktur</span><span class="sxs-lookup"><span data-stu-id="e80a3-102">CALL_ID Structure</span></span>
<span data-ttu-id="e80a3-103">Stellt Informationen bereit, an den Debugger zu einer Funktion, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e80a3-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="e80a3-104">Finden Sie unter den [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) Schnittstelle für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="e80a3-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e80a3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e80a3-105">Syntax</span></span>  
  
```cpp  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a><span data-ttu-id="e80a3-106">Member</span><span class="sxs-lookup"><span data-stu-id="e80a3-106">Members</span></span>  
  
|<span data-ttu-id="e80a3-107">Member</span><span class="sxs-lookup"><span data-stu-id="e80a3-107">Member</span></span>|<span data-ttu-id="e80a3-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e80a3-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="e80a3-109">Identifiziert den Computer, der den Aufruf ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="e80a3-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="e80a3-110">Gibt den Computerprozessor an.</span><span class="sxs-lookup"><span data-stu-id="e80a3-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="e80a3-111">Identifiziert den Thread, der den Aufruf ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e80a3-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="e80a3-112">Gibt die Adresse der Aufrufliste.</span><span class="sxs-lookup"><span data-stu-id="e80a3-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="e80a3-113">Gibt die Adresse des Aufrufs.</span><span class="sxs-lookup"><span data-stu-id="e80a3-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="e80a3-114">Identifiziert den Computer, der den Aufruf ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e80a3-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e80a3-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e80a3-115">Requirements</span></span>  
 <span data-ttu-id="e80a3-116">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="e80a3-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e80a3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e80a3-117">See also</span></span>

- [<span data-ttu-id="e80a3-118">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e80a3-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="e80a3-119">Diagnosesymbolspeicher-Strukturen</span><span class="sxs-lookup"><span data-stu-id="e80a3-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
