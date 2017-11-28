---
title: "Klasse unterstützt keine Automatisierung oder unterstützt die erwartete Schnittstelle nicht"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6528ceabeb7fb7a1cdc0beff2fd362632a0a0c9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a><span data-ttu-id="be026-102">Klasse unterstützt keine Automatisierung oder unterstützt die erwartete Schnittstelle nicht</span><span class="sxs-lookup"><span data-stu-id="be026-102">Class does not support Automation or does not support expected interface</span></span>
<span data-ttu-id="be026-103">Entweder macht die im Funktionsaufruf `GetObject` oder `CreateObject` angegebene Klasse eine Programmierschnittstelle nicht verfügbar, oder Sie haben ein Projekt von .dll in .exe oder umgekehrt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="be026-103">Either the class you specified in the `GetObject` or `CreateObject` function call has not exposed a programmability interface, or you changed a project from .dll to .exe, or vice versa.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="be026-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="be026-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="be026-105">Lesen Sie die Dokumentation zur Anwendung, mit der das Objekt erstellt wurde, um Beschränkungen hinsichtlich des Einsatzes von Automatisierung bei dieser Objektklasse herauszufinden.</span><span class="sxs-lookup"><span data-stu-id="be026-105">Check the documentation of the application that created the object for limitations on the use of automation with this class of object.</span></span>  
  
2.  <span data-ttu-id="be026-106">Wenn Sie ein Projekt von .dll in .exe oder umgekehrt geändert haben, müssen Sie die Registrierung der alten .dll oder .exe manuell aufheben.</span><span class="sxs-lookup"><span data-stu-id="be026-106">If you changed a project from .dll to .exe or vice versa, you must manually unregister the old .dll or .exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be026-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be026-107">See Also</span></span>  
 [<span data-ttu-id="be026-108">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="be026-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="be026-109">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="be026-109">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
