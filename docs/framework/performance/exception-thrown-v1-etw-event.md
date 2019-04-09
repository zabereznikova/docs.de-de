---
title: ExceptionThrown_V1-ETW-Ereignis
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd322d25d91bb277a4c817594c968c28a6d61d68
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136135"
---
# <a name="exception-thrownv1-etw-event"></a><span data-ttu-id="406d2-102">ExceptionThrown_V1-ETW-Ereignis</span><span class="sxs-lookup"><span data-stu-id="406d2-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="406d2-103">Dieses Ereignis erfasst Informationen über die ausgelösten Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="406d2-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="406d2-104">Die folgende Tabelle zeigt das Schlüsselwort, unter dem das Ereignis ausgelöst wird, und die Ebene des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="406d2-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="406d2-105">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="406d2-105">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="406d2-106">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="406d2-106">Keyword for raising the event</span></span>|<span data-ttu-id="406d2-107">Ebene</span><span class="sxs-lookup"><span data-stu-id="406d2-107">Level</span></span>|  
|-----------------------------------|-----------|  
|`ExceptionKeyword` <span data-ttu-id="406d2-108">(0x8000)</span><span class="sxs-lookup"><span data-stu-id="406d2-108">(0x8000)</span></span>|<span data-ttu-id="406d2-109">Warnung (2)</span><span class="sxs-lookup"><span data-stu-id="406d2-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="406d2-110">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="406d2-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="406d2-111">event</span><span class="sxs-lookup"><span data-stu-id="406d2-111">Event</span></span>|<span data-ttu-id="406d2-112">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="406d2-112">Event ID</span></span>|<span data-ttu-id="406d2-113">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="406d2-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="406d2-114">80</span><span class="sxs-lookup"><span data-stu-id="406d2-114">80</span></span>|<span data-ttu-id="406d2-115">Eine verwaltete Ausnahme wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="406d2-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="406d2-116">In der folgenden Tabelle finden Sie die Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="406d2-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="406d2-117">Feldname</span><span class="sxs-lookup"><span data-stu-id="406d2-117">Field name</span></span>|<span data-ttu-id="406d2-118">Datentyp</span><span class="sxs-lookup"><span data-stu-id="406d2-118">Data type</span></span>|<span data-ttu-id="406d2-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="406d2-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="406d2-120">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="406d2-120">Exception Type</span></span>|<span data-ttu-id="406d2-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="406d2-121">win:UnicodeString</span></span>|<span data-ttu-id="406d2-122">Typ der Ausnahme, z.B. `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="406d2-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="406d2-123">Ausnahmemeldung</span><span class="sxs-lookup"><span data-stu-id="406d2-123">Exception Message</span></span>|<span data-ttu-id="406d2-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="406d2-124">win:UnicodeString</span></span>|<span data-ttu-id="406d2-125">Tatsächliche Ausnahmemeldung.</span><span class="sxs-lookup"><span data-stu-id="406d2-125">Actual exception message.</span></span>|  
|<span data-ttu-id="406d2-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="406d2-126">EIPCodeThrow</span></span>|<span data-ttu-id="406d2-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="406d2-127">win:Pointer</span></span>|<span data-ttu-id="406d2-128">Anweisungszeiger an der Stelle, an der die Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="406d2-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="406d2-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="406d2-129">ExceptionHR</span></span>|<span data-ttu-id="406d2-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="406d2-130">win:UInt32</span></span>|<span data-ttu-id="406d2-131">Ausnahme [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span><span class="sxs-lookup"><span data-stu-id="406d2-131">Exception [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="406d2-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="406d2-132">ExceptionFlags</span></span>|<span data-ttu-id="406d2-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="406d2-133">win:UInt16</span></span>|<span data-ttu-id="406d2-134">0x01: HasInnerException (siehe [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md) in der Dokumentation zu Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="406d2-134">0x01: HasInnerException (see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="406d2-135">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="406d2-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="406d2-136">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="406d2-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="406d2-137">0x08: IsCorruptedStateException (gibt an, dass der Prozessstatus fehlerhaft ist, finden Sie unter [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) auf MSDN).</span><span class="sxs-lookup"><span data-stu-id="406d2-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="406d2-138">0 x 10: IsCLSCompliant (eine Ausnahme, die abgeleitet <xref:System.Exception> CLS-kompatibel ist, andernfalls ist es nicht CLS-kompatibel).</span><span class="sxs-lookup"><span data-stu-id="406d2-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="406d2-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="406d2-139">ClrInstanceID</span></span>|<span data-ttu-id="406d2-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="406d2-140">win:UInt16</span></span>|<span data-ttu-id="406d2-141">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="406d2-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="406d2-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="406d2-142">See also</span></span>

- [<span data-ttu-id="406d2-143">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="406d2-143">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
