---
title: ETW-Stapelereignis
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
ms.openlocfilehash: f3014a04ba7cacbe37b6706e2919ffd7de19aa65
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715912"
---
# <a name="stack-etw-event"></a><span data-ttu-id="53fa1-102">ETW-Stapelereignis</span><span class="sxs-lookup"><span data-stu-id="53fa1-102">Stack ETW Event</span></span>
<span data-ttu-id="53fa1-103">Das Stapelereignis sollte in Verbindung mit anderen Ereignissen verwendet werden, um Stapelüberwachungen zu generieren, nachdem ein Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="53fa1-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="53fa1-104">Es wird protokolliert, wann der Laufzeitanbieter aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="53fa1-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="53fa1-105">Dieses Ereignis hat eine hohe Frequenz, da es ausgelöst wird, wenn ein anderes Laufzeitereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="53fa1-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="53fa1-106">Aus diesem Grund wird empfohlen, dass Sie dieses Ereignis mit Vorsicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="53fa1-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="53fa1-107">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="53fa1-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="53fa1-108">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="53fa1-108">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="53fa1-109">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="53fa1-109">Keyword for raising the event</span></span>|<span data-ttu-id="53fa1-110">Level</span><span class="sxs-lookup"><span data-stu-id="53fa1-110">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="53fa1-111">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="53fa1-111">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="53fa1-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="53fa1-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="53fa1-113">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="53fa1-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="53fa1-114">Event</span><span class="sxs-lookup"><span data-stu-id="53fa1-114">Event</span></span>|<span data-ttu-id="53fa1-115">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="53fa1-115">Event ID</span></span>|<span data-ttu-id="53fa1-116">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="53fa1-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="53fa1-117">82</span><span class="sxs-lookup"><span data-stu-id="53fa1-117">82</span></span>|<span data-ttu-id="53fa1-118">In Verbindung mit anderen Ereignissen zum Generieren von Stapelüberwachungen nach einem Ereignis.</span><span class="sxs-lookup"><span data-stu-id="53fa1-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="53fa1-119">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="53fa1-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="53fa1-120">Feldname</span><span class="sxs-lookup"><span data-stu-id="53fa1-120">Field name</span></span>|<span data-ttu-id="53fa1-121">-Datentyp</span><span class="sxs-lookup"><span data-stu-id="53fa1-121">Data Type</span></span>|<span data-ttu-id="53fa1-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53fa1-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="53fa1-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="53fa1-123">ClrInstanceID</span></span>|<span data-ttu-id="53fa1-124">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="53fa1-124">win:Uint16</span></span>|<span data-ttu-id="53fa1-125">URI.</span><span class="sxs-lookup"><span data-stu-id="53fa1-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="53fa1-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="53fa1-126">Reserved1</span></span>|<span data-ttu-id="53fa1-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="53fa1-127">win:UInt8</span></span>|<span data-ttu-id="53fa1-128">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="53fa1-128">Reserved.</span></span>|  
|<span data-ttu-id="53fa1-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="53fa1-129">Reserved2</span></span>|<span data-ttu-id="53fa1-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="53fa1-130">win:UInt8</span></span>|<span data-ttu-id="53fa1-131">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="53fa1-131">Reserved.</span></span>|  
|<span data-ttu-id="53fa1-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="53fa1-132">FrameCount</span></span>|<span data-ttu-id="53fa1-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="53fa1-133">win:UInt32</span></span>|<span data-ttu-id="53fa1-134">Die Anzahl von Frames in der Stapelüberwachung.</span><span class="sxs-lookup"><span data-stu-id="53fa1-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="53fa1-135">Stapel</span><span class="sxs-lookup"><span data-stu-id="53fa1-135">Stack</span></span>|<span data-ttu-id="53fa1-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="53fa1-136">win:Pointer</span></span>|<span data-ttu-id="53fa1-137">Anweisungszeigerspalten.</span><span class="sxs-lookup"><span data-stu-id="53fa1-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53fa1-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53fa1-138">See also</span></span>

- [<span data-ttu-id="53fa1-139">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="53fa1-139">CLR ETW Events</span></span>](clr-etw-events.md)
