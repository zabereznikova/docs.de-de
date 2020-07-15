---
title: ExceptionThrown_V1-ETW-Ereignis
description: Ausführliche Informationen zum ExceptionThrown_V1 ETW-Ereignis anzeigen. Ereignisdaten, wie z. b. Feldnamen, Datentypen und Beschreibungen, werden für ausgelöste Ausnahmen angegeben.
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
ms.openlocfilehash: f800a43d0ed2a82bc51a5e3a028b5fa1870df3fb
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309455"
---
# <a name="exception-thrown_v1-etw-event"></a><span data-ttu-id="a5f11-104">ExceptionThrown_V1-ETW-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a5f11-104">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="a5f11-105">Dieses Ereignis erfasst Informationen über die ausgelösten Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="a5f11-105">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="a5f11-106">Die folgende Tabelle zeigt das Schlüsselwort, unter dem das Ereignis ausgelöst wird, und die Ebene des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="a5f11-106">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="a5f11-107">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="a5f11-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a5f11-108">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a5f11-108">Keyword for raising the event</span></span>|<span data-ttu-id="a5f11-109">Ebene</span><span class="sxs-lookup"><span data-stu-id="a5f11-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a5f11-110">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="a5f11-110">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="a5f11-111">Warning (2)</span><span class="sxs-lookup"><span data-stu-id="a5f11-111">Warning (2)</span></span>|  
  
 <span data-ttu-id="a5f11-112">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a5f11-112">The following table shows event information.</span></span>  
  
|<span data-ttu-id="a5f11-113">Ereignis</span><span class="sxs-lookup"><span data-stu-id="a5f11-113">Event</span></span>|<span data-ttu-id="a5f11-114">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a5f11-114">Event ID</span></span>|<span data-ttu-id="a5f11-115">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a5f11-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="a5f11-116">80</span><span class="sxs-lookup"><span data-stu-id="a5f11-116">80</span></span>|<span data-ttu-id="a5f11-117">Eine verwaltete Ausnahme wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a5f11-117">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="a5f11-118">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a5f11-118">The following table shows event data.</span></span>  
  
|<span data-ttu-id="a5f11-119">Feldname</span><span class="sxs-lookup"><span data-stu-id="a5f11-119">Field name</span></span>|<span data-ttu-id="a5f11-120">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a5f11-120">Data type</span></span>|<span data-ttu-id="a5f11-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a5f11-121">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a5f11-122">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="a5f11-122">Exception Type</span></span>|<span data-ttu-id="a5f11-123">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a5f11-123">win:UnicodeString</span></span>|<span data-ttu-id="a5f11-124">Typ der Ausnahme, z.B. `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="a5f11-124">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="a5f11-125">Ausnahmemeldung</span><span class="sxs-lookup"><span data-stu-id="a5f11-125">Exception Message</span></span>|<span data-ttu-id="a5f11-126">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a5f11-126">win:UnicodeString</span></span>|<span data-ttu-id="a5f11-127">Tatsächliche Ausnahmemeldung.</span><span class="sxs-lookup"><span data-stu-id="a5f11-127">Actual exception message.</span></span>|  
|<span data-ttu-id="a5f11-128">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="a5f11-128">EIPCodeThrow</span></span>|<span data-ttu-id="a5f11-129">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="a5f11-129">win:Pointer</span></span>|<span data-ttu-id="a5f11-130">Anweisungszeiger an der Stelle, an der die Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a5f11-130">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="a5f11-131">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="a5f11-131">ExceptionHR</span></span>|<span data-ttu-id="a5f11-132">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a5f11-132">win:UInt32</span></span>|<span data-ttu-id="a5f11-133">Ausnahme [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span><span class="sxs-lookup"><span data-stu-id="a5f11-133">Exception [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|  
|<span data-ttu-id="a5f11-134">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="a5f11-134">ExceptionFlags</span></span>|<span data-ttu-id="a5f11-135">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a5f11-135">win:UInt16</span></span>|<span data-ttu-id="a5f11-136">0x01: HasInnerException (siehe [CLR ETW Events (CLR-ETW-Ereignisse)](clr-etw-events.md) in der Visual Basic-Dokumentation).</span><span class="sxs-lookup"><span data-stu-id="a5f11-136">0x01: HasInnerException (see [CLR ETW Events](clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="a5f11-137">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="a5f11-137">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="a5f11-138">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="a5f11-138">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="a5f11-139">0x08: isbeschätedstateexception (gibt an, dass der Prozessstatus beschädigt ist, siehe [Behandlung von Ausnahmen für beschädigte](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)Zustände).</span><span class="sxs-lookup"><span data-stu-id="a5f11-139">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="a5f11-140">0x10: IsCLSCompliant (eine Ausnahme, die von <xref:System.Exception> ableitet, ob eine CLS-Kompatibilität vorliegt, andernfalls ist sie nicht CLS-kompatibel).</span><span class="sxs-lookup"><span data-stu-id="a5f11-140">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="a5f11-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a5f11-141">ClrInstanceID</span></span>|<span data-ttu-id="a5f11-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a5f11-142">win:UInt16</span></span>|<span data-ttu-id="a5f11-143">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a5f11-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5f11-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5f11-144">See also</span></span>

- [<span data-ttu-id="a5f11-145">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="a5f11-145">CLR ETW Events</span></span>](clr-etw-events.md)
