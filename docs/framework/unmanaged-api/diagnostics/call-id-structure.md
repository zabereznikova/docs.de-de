---
title: CALL_ID-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CALL_ID
api_location: diasymreader.dll
api_type: COM
f1_keywords: CALL_ID
helpviewer_keywords: CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c44db9021a7dbf5b497db3536eddcea020e71bf7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="callid-structure"></a><span data-ttu-id="2e006-102">CALL_ID-Struktur</span><span class="sxs-lookup"><span data-stu-id="2e006-102">CALL_ID Structure</span></span>
<span data-ttu-id="2e006-103">Enthält Informationen für einen Debugger zu einer Funktion, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2e006-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="2e006-104">Finden Sie unter der [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) Schnittstelle für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="2e006-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e006-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e006-105">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="2e006-106">Member</span><span class="sxs-lookup"><span data-stu-id="2e006-106">Members</span></span>  
  
|<span data-ttu-id="2e006-107">Member</span><span class="sxs-lookup"><span data-stu-id="2e006-107">Member</span></span>|<span data-ttu-id="2e006-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e006-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="2e006-109">Identifiziert den Computer, der den Aufruf ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="2e006-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="2e006-110">Identifiziert den Computerprozessor.</span><span class="sxs-lookup"><span data-stu-id="2e006-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="2e006-111">Identifiziert den Thread, der den Aufruf ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2e006-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="2e006-112">Gibt die Adresse der Aufrufliste.</span><span class="sxs-lookup"><span data-stu-id="2e006-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="2e006-113">Gibt die Adresse des Aufrufs.</span><span class="sxs-lookup"><span data-stu-id="2e006-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="2e006-114">Identifiziert den Computer, der den Aufruf ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2e006-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e006-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2e006-115">Requirements</span></span>  
 <span data-ttu-id="2e006-116">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="2e006-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e006-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e006-117">See Also</span></span>  
 [<span data-ttu-id="2e006-118">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2e006-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="2e006-119">Diagnosesymbolspeicher-Strukturen</span><span class="sxs-lookup"><span data-stu-id="2e006-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
