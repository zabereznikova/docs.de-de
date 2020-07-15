---
title: 'Konflikt-ETW-Ereignisse: .net'
description: Hier finden Sie Details zu etw-Konflikt Ereignissen, die ausgelöst werden, wenn Konflikte zwischen System. Threading. Monitor-sperren oder System eigenen Sperren auftreten, die von der Laufzeit verwendet werden.
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
ms.openlocfilehash: a36b091e0896562fffdb66e895d70049ce0667d7
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309598"
---
# <a name="contention-etw-events"></a><span data-ttu-id="1ba3a-103">Etw-konfliktereignisse</span><span class="sxs-lookup"><span data-stu-id="1ba3a-103">Contention ETW events</span></span>

<span data-ttu-id="1ba3a-104">Konfliktereignisse werden immer dann ausgelöst, wenn es Konflikte bei <xref:System.Threading.Monitor?displayProperty=nameWithType>-Sperren oder nativen Sperren gibt, die von der Laufzeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ba3a-104">Contention events are raised whenever there is contention for <xref:System.Threading.Monitor?displayProperty=nameWithType> locks or native locks used by the runtime.</span></span> <span data-ttu-id="1ba3a-105">Konflikte treten auf, wenn ein Thread auf eine Sperre wartet, während ein anderer Thread die Sperre besitzt.</span><span class="sxs-lookup"><span data-stu-id="1ba3a-105">Contention occurs when a thread is waiting for a lock while another thread possesses the lock.</span></span>

<span data-ttu-id="1ba3a-106">Die folgende Tabelle zeigt das Schlüsselwort, unter dem Konfliktereignisse ausgelöst werden, und die Ebene der Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="1ba3a-106">The following table shows the keyword under which contention events are raised, and the level of the events.</span></span> <span data-ttu-id="1ba3a-107">Weitere Informationen finden Sie unter [CLR-ETW-Schlüsselwörter und-Ebenen](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1ba3a-107">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="1ba3a-108">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="1ba3a-108">Keyword for raising the event</span></span>|<span data-ttu-id="1ba3a-109">Ebene</span><span class="sxs-lookup"><span data-stu-id="1ba3a-109">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1ba3a-110">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="1ba3a-110">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="1ba3a-111">Information (4)</span><span class="sxs-lookup"><span data-stu-id="1ba3a-111">Informational (4)</span></span>|

<span data-ttu-id="1ba3a-112">In der folgenden Tabelle werden die Ereignis Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ba3a-112">The following table shows event information:</span></span>

|<span data-ttu-id="1ba3a-113">Ereignis</span><span class="sxs-lookup"><span data-stu-id="1ba3a-113">Event</span></span>|<span data-ttu-id="1ba3a-114">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="1ba3a-114">Event ID</span></span>|<span data-ttu-id="1ba3a-115">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="1ba3a-115">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|<span data-ttu-id="1ba3a-116">81</span><span class="sxs-lookup"><span data-stu-id="1ba3a-116">81</span></span>|<span data-ttu-id="1ba3a-117">Konflikt startet.</span><span class="sxs-lookup"><span data-stu-id="1ba3a-117">Contention starts.</span></span> <span data-ttu-id="1ba3a-118">Dieses Ereignis enthält die Spinzeit vor dem Abruf einer Sperre eines Threads nicht. Dies wird nur ausgelöst, wenn der Thread darauf wartet, eine Sperre abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1ba3a-118">This event does not include the amount of spinning time before a thread waits to acquire a lock; it is raised only when the thread waits to acquire a lock.</span></span>|
|`ContentionStop`|<span data-ttu-id="1ba3a-119">91</span><span class="sxs-lookup"><span data-stu-id="1ba3a-119">91</span></span>|<span data-ttu-id="1ba3a-120">Konflikt endet.</span><span class="sxs-lookup"><span data-stu-id="1ba3a-120">Contention ends.</span></span>|

<span data-ttu-id="1ba3a-121">In der folgenden Tabelle werden die Ereignisdaten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ba3a-121">The following table shows event data:</span></span>

|<span data-ttu-id="1ba3a-122">Feldname</span><span class="sxs-lookup"><span data-stu-id="1ba3a-122">Field name</span></span>|<span data-ttu-id="1ba3a-123">Datentyp</span><span class="sxs-lookup"><span data-stu-id="1ba3a-123">Data type</span></span>|<span data-ttu-id="1ba3a-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1ba3a-124">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="1ba3a-125">Flags</span><span class="sxs-lookup"><span data-stu-id="1ba3a-125">Flags</span></span>|<span data-ttu-id="1ba3a-126">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="1ba3a-126">win:UInt8</span></span>|<span data-ttu-id="1ba3a-127">0 für verwaltet. 1 für nativ.</span><span class="sxs-lookup"><span data-stu-id="1ba3a-127">0 for managed; 1 for native.</span></span>|
|<span data-ttu-id="1ba3a-128">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1ba3a-128">ClrInstanceID</span></span>|<span data-ttu-id="1ba3a-129">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1ba3a-129">win:UInt16</span></span>|<span data-ttu-id="1ba3a-130">Eindeutige ID für die Instanz von CLR.</span><span class="sxs-lookup"><span data-stu-id="1ba3a-130">Unique ID for the instance of CLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="1ba3a-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ba3a-131">See also</span></span>

- [<span data-ttu-id="1ba3a-132">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="1ba3a-132">CLR ETW Events</span></span>](clr-etw-events.md)
