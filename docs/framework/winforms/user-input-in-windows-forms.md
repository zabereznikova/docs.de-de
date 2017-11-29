---
title: Benutzereingaben in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- keyboard input [Windows Forms], using in Windows Forms
- Windows Forms, user input
- mouse input [Windows Forms], using in Windows Forms
- keyboards [Windows Forms], keyboard input
ms.assetid: 1486075f-1e06-4c9e-82c6-f948331db6d6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c65fdca99bb12cccf70273194e3294c71a2f5a7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="user-input-in-windows-forms"></a><span data-ttu-id="e9816-102">Benutzereingaben in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e9816-102">User Input in Windows Forms</span></span>
<span data-ttu-id="e9816-103">Windows Forms umfasst ein Modell für Benutzereingaben auf der Grundlage von Ereignissen, die ausgelöst werden, während zugehörige Windows-Nachrichten verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e9816-103">Windows Forms includes a user input model based on events that are raised while processing related Windows messages.</span></span> <span data-ttu-id="e9816-104">Die Themen in diesem Abschnitt enthalten Informationen zu Benutzereingaben über die Maus und Tastatur, einschließlich Codebeispielen, die zeigen, wie bestimmte Aufgaben ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e9816-104">The topics in this section provide information on mouse and keyboard user input, including code examples that demonstrate how to perform specific tasks.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9816-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e9816-105">In This Section</span></span>  
 [<span data-ttu-id="e9816-106">Benutzereingabe in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="e9816-106">User Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/user-input-in-a-windows-forms-application.md)  
 <span data-ttu-id="e9816-107">Bietet eine Übersicht über Benutzereingabeereignisse und die Methoden, die Windows-Nachrichten verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e9816-107">Provides an overview of user input events and the methods that process Windows messages.</span></span>  
  
 [<span data-ttu-id="e9816-108">Tastatureingaben in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="e9816-108">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 <span data-ttu-id="e9816-109">Stellt Informationen zur Tastaturnachrichtenbehandlung, zu den verschiedenen Typen von Tasten und zu Tastaturereignissen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e9816-109">Provides information on keyboard message handling, the different types of keys, and the keyboard events.</span></span>  
  
 [<span data-ttu-id="e9816-110">Mauseingabe in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="e9816-110">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)  
 <span data-ttu-id="e9816-111">Stellt Informationen zu Mausereignissen und anderen mausbezogenen Funktionen einschließlich Mauscursor und Mausaufzeichnung bereit.</span><span class="sxs-lookup"><span data-stu-id="e9816-111">Provides information on the mouse events and other mouse-related features, including mouse cursors and mouse capture.</span></span>  
  
 [<span data-ttu-id="e9816-112">Gewusst wie: Simulieren von Maus- und Tastaturereignissen in Code</span><span class="sxs-lookup"><span data-stu-id="e9816-112">How to: Simulate Mouse and Keyboard Events in Code</span></span>](../../../docs/framework/winforms/how-to-simulate-mouse-and-keyboard-events-in-code.md)  
 <span data-ttu-id="e9816-113">Zeigt verschiedene Möglichkeiten, Maus- und Tastatureingaben programmgesteuert zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="e9816-113">Demonstrates several different ways to programmatically simulate mouse and keyboard input.</span></span>  
  
 [<span data-ttu-id="e9816-114">Gewusst wie: Behandeln von Benutzereingabeereignissen in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="e9816-114">How to: Handle User Input Events in Windows Forms Controls</span></span>](../../../docs/framework/winforms/how-to-handle-user-input-events-in-windows-forms-controls.md)  
 <span data-ttu-id="e9816-115">Enthält ein Codebeispiel, das die meisten Benutzereingabeereignisse verarbeitet und Informationen zu jedem Ereignis bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e9816-115">Presents a code example that handles most user input events and reports information about each event.</span></span>  
  
 [<span data-ttu-id="e9816-116">Validierung von Benutzereingaben in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e9816-116">User Input Validation in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 <span data-ttu-id="e9816-117">Beschreibt die Methoden zum Überprüfen von Benutzereingaben in Windows Forms-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e9816-117">Describes the methods to validate user input in Windows Forms applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e9816-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e9816-118">Related Sections</span></span>  
 <span data-ttu-id="e9816-119">Siehe auch [Erstellen von Ereignishandlern in Windows Forms](http://msdn.microsoft.com/library/dacysss4\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="e9816-119">Also see [Creating Event Handlers in Windows Forms](http://msdn.microsoft.com/library/dacysss4\(v=vs.110\)).</span></span>
