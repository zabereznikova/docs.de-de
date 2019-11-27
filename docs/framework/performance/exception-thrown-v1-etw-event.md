---
title: ExceptionThrown_V1-ETW-Ereignis
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f0e968053c87319bf90bf3de0f21d750ec899ab
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447632"
---
# <a name="exception-thrown_v1-etw-event"></a><span data-ttu-id="05e3f-102">ExceptionThrown_V1-ETW-Ereignis</span><span class="sxs-lookup"><span data-stu-id="05e3f-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="05e3f-103">Dieses Ereignis erfasst Informationen über die ausgelösten Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="05e3f-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="05e3f-104">Die folgende Tabelle zeigt das Schlüsselwort, unter dem das Ereignis ausgelöst wird, und die Ebene des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="05e3f-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="05e3f-105">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="05e3f-105">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="05e3f-106">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="05e3f-106">Keyword for raising the event</span></span>|<span data-ttu-id="05e3f-107">Level</span><span class="sxs-lookup"><span data-stu-id="05e3f-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="05e3f-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="05e3f-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="05e3f-109">Warnung (2)</span><span class="sxs-lookup"><span data-stu-id="05e3f-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="05e3f-110">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="05e3f-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="05e3f-111">Ereignis</span><span class="sxs-lookup"><span data-stu-id="05e3f-111">Event</span></span>|<span data-ttu-id="05e3f-112">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="05e3f-112">Event ID</span></span>|<span data-ttu-id="05e3f-113">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="05e3f-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="05e3f-114">80</span><span class="sxs-lookup"><span data-stu-id="05e3f-114">80</span></span>|<span data-ttu-id="05e3f-115">Eine verwaltete Ausnahme wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="05e3f-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="05e3f-116">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="05e3f-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="05e3f-117">Feldname</span><span class="sxs-lookup"><span data-stu-id="05e3f-117">Field name</span></span>|<span data-ttu-id="05e3f-118">Datentyp</span><span class="sxs-lookup"><span data-stu-id="05e3f-118">Data type</span></span>|<span data-ttu-id="05e3f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05e3f-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="05e3f-120">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="05e3f-120">Exception Type</span></span>|<span data-ttu-id="05e3f-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="05e3f-121">win:UnicodeString</span></span>|<span data-ttu-id="05e3f-122">Typ der Ausnahme, z.B. `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="05e3f-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="05e3f-123">Ausnahmemeldung</span><span class="sxs-lookup"><span data-stu-id="05e3f-123">Exception Message</span></span>|<span data-ttu-id="05e3f-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="05e3f-124">win:UnicodeString</span></span>|<span data-ttu-id="05e3f-125">Tatsächliche Ausnahmemeldung.</span><span class="sxs-lookup"><span data-stu-id="05e3f-125">Actual exception message.</span></span>|  
|<span data-ttu-id="05e3f-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="05e3f-126">EIPCodeThrow</span></span>|<span data-ttu-id="05e3f-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="05e3f-127">win:Pointer</span></span>|<span data-ttu-id="05e3f-128">Anweisungszeiger an der Stelle, an der die Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="05e3f-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="05e3f-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="05e3f-129">ExceptionHR</span></span>|<span data-ttu-id="05e3f-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="05e3f-130">win:UInt32</span></span>|<span data-ttu-id="05e3f-131">Ausnahme [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span><span class="sxs-lookup"><span data-stu-id="05e3f-131">Exception [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|  
|<span data-ttu-id="05e3f-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="05e3f-132">ExceptionFlags</span></span>|<span data-ttu-id="05e3f-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="05e3f-133">win:UInt16</span></span>|<span data-ttu-id="05e3f-134">0x01: HasInnerException (siehe [CLR ETW Events (CLR-ETW-Ereignisse)](clr-etw-events.md) in der Visual Basic-Dokumentation).</span><span class="sxs-lookup"><span data-stu-id="05e3f-134">0x01: HasInnerException (see [CLR ETW Events](clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="05e3f-135">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="05e3f-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="05e3f-136">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="05e3f-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="05e3f-137">0x08: isbeschätedstateexception (gibt an, dass der Prozessstatus beschädigt ist, siehe [Behandlung von Ausnahmen für beschädigte](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)Zustände).</span><span class="sxs-lookup"><span data-stu-id="05e3f-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="05e3f-138">0x10: IsCLSCompliant (eine Ausnahme, die von <xref:System.Exception> ableitet, ob eine CLS-Kompatibilität vorliegt, andernfalls ist sie nicht CLS-kompatibel).</span><span class="sxs-lookup"><span data-stu-id="05e3f-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="05e3f-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="05e3f-139">ClrInstanceID</span></span>|<span data-ttu-id="05e3f-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="05e3f-140">win:UInt16</span></span>|<span data-ttu-id="05e3f-141">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="05e3f-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05e3f-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05e3f-142">See also</span></span>

- [<span data-ttu-id="05e3f-143">CLR ETW Events (CLR-ETW-Ereignisse)</span><span class="sxs-lookup"><span data-stu-id="05e3f-143">CLR ETW Events</span></span>](clr-etw-events.md)
