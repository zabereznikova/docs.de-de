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
ms.openlocfilehash: 3f41dd969e25f7a42308ff0b7b2d617344284b38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725247"
---
# <a name="call_id-structure"></a><span data-ttu-id="cbe66-102">CALL_ID-Struktur</span><span class="sxs-lookup"><span data-stu-id="cbe66-102">CALL_ID Structure</span></span>

<span data-ttu-id="cbe66-103">Stellt einem Debugger Informationen zu einer Funktion bereit, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="cbe66-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="cbe66-104">Weitere Informationen finden Sie in der [INotifySink2](inotifysink2-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="cbe66-104">See the [INotifySink2](inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbe66-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbe66-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="cbe66-106">Member</span><span class="sxs-lookup"><span data-stu-id="cbe66-106">Members</span></span>  
  
|<span data-ttu-id="cbe66-107">Member</span><span class="sxs-lookup"><span data-stu-id="cbe66-107">Member</span></span>|<span data-ttu-id="cbe66-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cbe66-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="cbe66-109">Identifiziert den Computer, der den-Befehl aufruft.</span><span class="sxs-lookup"><span data-stu-id="cbe66-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="cbe66-110">Identifiziert den Computer Prozessor.</span><span class="sxs-lookup"><span data-stu-id="cbe66-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="cbe66-111">Identifiziert den Thread, der den-Befehl ausführt.</span><span class="sxs-lookup"><span data-stu-id="cbe66-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="cbe66-112">Gibt die Adresse der-aufrufsstapel an.</span><span class="sxs-lookup"><span data-stu-id="cbe66-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="cbe66-113">Gibt die Adresse des Aufrufes an.</span><span class="sxs-lookup"><span data-stu-id="cbe66-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="cbe66-114">Identifiziert den Computer, der den-Befehl ausführt.</span><span class="sxs-lookup"><span data-stu-id="cbe66-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cbe66-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cbe66-115">Requirements</span></span>  

 <span data-ttu-id="cbe66-116">**Header:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="cbe66-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe66-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cbe66-117">See also</span></span>

- [<span data-ttu-id="cbe66-118">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cbe66-118">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="cbe66-119">Diagnosesymbolspeicher-Strukturen</span><span class="sxs-lookup"><span data-stu-id="cbe66-119">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
