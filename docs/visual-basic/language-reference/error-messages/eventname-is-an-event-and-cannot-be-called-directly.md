---
title: '&#39; &lt;Eventname&gt;&#39; ist ein Ereignis und kann nicht direkt aufgerufen werden'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords: BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb987c957a28aa37c40ad975b945c20da4690f6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="06bc3-102">&#39; &lt;Eventname&gt;&#39; ist ein Ereignis und kann nicht direkt aufgerufen werden</span><span class="sxs-lookup"><span data-stu-id="06bc3-102">&#39;&lt;eventname&gt;&#39; is an event, and cannot be called directly</span></span>
<span data-ttu-id="06bc3-103">"<`eventname`>' ist ein Ereignis und kann daher nicht direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="06bc3-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="06bc3-104">Verwenden einer `RaiseEvent` Anweisung, um ein Ereignis auszulösen.</span><span class="sxs-lookup"><span data-stu-id="06bc3-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="06bc3-105">Ein Prozeduraufruf gibt ein Ereignis für den Namen der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="06bc3-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="06bc3-106">Ein Ereignishandler ist eine Prozedur, aber das Ereignis selbst ist ein signaling Gerät, die ausgelöst und behandelt werden muss.</span><span class="sxs-lookup"><span data-stu-id="06bc3-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="06bc3-107">**Fehler-ID:** BC32022</span><span class="sxs-lookup"><span data-stu-id="06bc3-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="06bc3-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="06bc3-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="06bc3-109">Verwenden einer `RaiseEvent` Anweisung signalisieren eines Ereignisses und das Aufrufen der Prozedur oder Prozeduren, die sie behandeln.</span><span class="sxs-lookup"><span data-stu-id="06bc3-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06bc3-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06bc3-110">See Also</span></span>  
 [<span data-ttu-id="06bc3-111">RaiseEvent-Anweisung</span><span class="sxs-lookup"><span data-stu-id="06bc3-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
