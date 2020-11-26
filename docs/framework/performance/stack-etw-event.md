---
title: ETW-Stapelereignis
description: Informieren Sie sich über das ETW-Stapel Ereignis, das zusammen mit anderen Ereignissen verwendet werden sollte, um Stapel Überwachungen zu generieren, nachdem ein Ereignis ausgelöst wurde.
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
ms.openlocfilehash: 3b890e587abd5cb1b7315fe41897f24638fd4604
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236207"
---
# <a name="stack-etw-event"></a><span data-ttu-id="27294-103">ETW-Stapelereignis</span><span class="sxs-lookup"><span data-stu-id="27294-103">Stack ETW Event</span></span>

<span data-ttu-id="27294-104">Das Stapelereignis sollte in Verbindung mit anderen Ereignissen verwendet werden, um Stapelüberwachungen zu generieren, nachdem ein Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="27294-104">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="27294-105">Es wird protokolliert, wann der Laufzeitanbieter aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="27294-105">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="27294-106">Dieses Ereignis hat eine hohe Frequenz, da es ausgelöst wird, wenn ein anderes Laufzeitereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="27294-106">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="27294-107">Aus diesem Grund wird empfohlen, dass Sie dieses Ereignis mit Vorsicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="27294-107">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="27294-108">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="27294-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="27294-109">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="27294-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="27294-110">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="27294-110">Keyword for raising the event</span></span>|<span data-ttu-id="27294-111">Ebene</span><span class="sxs-lookup"><span data-stu-id="27294-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="27294-112">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="27294-112">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="27294-113">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="27294-113">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="27294-114">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="27294-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="27294-115">Ereignis</span><span class="sxs-lookup"><span data-stu-id="27294-115">Event</span></span>|<span data-ttu-id="27294-116">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="27294-116">Event ID</span></span>|<span data-ttu-id="27294-117">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="27294-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="27294-118">82</span><span class="sxs-lookup"><span data-stu-id="27294-118">82</span></span>|<span data-ttu-id="27294-119">In Verbindung mit anderen Ereignissen zum Generieren von Stapelüberwachungen nach einem Ereignis.</span><span class="sxs-lookup"><span data-stu-id="27294-119">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="27294-120">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="27294-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="27294-121">Feldname</span><span class="sxs-lookup"><span data-stu-id="27294-121">Field name</span></span>|<span data-ttu-id="27294-122">Datentyp</span><span class="sxs-lookup"><span data-stu-id="27294-122">Data Type</span></span>|<span data-ttu-id="27294-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="27294-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="27294-124">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="27294-124">ClrInstanceID</span></span>|<span data-ttu-id="27294-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="27294-125">win:Uint16</span></span>|<span data-ttu-id="27294-126">URI.</span><span class="sxs-lookup"><span data-stu-id="27294-126">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="27294-127">Reserved1</span><span class="sxs-lookup"><span data-stu-id="27294-127">Reserved1</span></span>|<span data-ttu-id="27294-128">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="27294-128">win:UInt8</span></span>|<span data-ttu-id="27294-129">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="27294-129">Reserved.</span></span>|  
|<span data-ttu-id="27294-130">Reserved2</span><span class="sxs-lookup"><span data-stu-id="27294-130">Reserved2</span></span>|<span data-ttu-id="27294-131">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="27294-131">win:UInt8</span></span>|<span data-ttu-id="27294-132">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="27294-132">Reserved.</span></span>|  
|<span data-ttu-id="27294-133">FrameCount</span><span class="sxs-lookup"><span data-stu-id="27294-133">FrameCount</span></span>|<span data-ttu-id="27294-134">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="27294-134">win:UInt32</span></span>|<span data-ttu-id="27294-135">Die Anzahl von Frames in der Stapelüberwachung.</span><span class="sxs-lookup"><span data-stu-id="27294-135">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="27294-136">Stapel</span><span class="sxs-lookup"><span data-stu-id="27294-136">Stack</span></span>|<span data-ttu-id="27294-137">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="27294-137">win:Pointer</span></span>|<span data-ttu-id="27294-138">Anweisungszeigerspalten.</span><span class="sxs-lookup"><span data-stu-id="27294-138">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27294-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27294-139">See also</span></span>

- [<span data-ttu-id="27294-140">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="27294-140">CLR ETW Events</span></span>](clr-etw-events.md)
