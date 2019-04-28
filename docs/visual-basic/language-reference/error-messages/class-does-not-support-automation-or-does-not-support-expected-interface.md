---
title: Klasse unterstützt keine Automatisierung oder unterstützt die erwartete Schnittstelle nicht
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: 4545c6d3bc302dba0c37e5ae6ebefa8939b0cff9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649906"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a><span data-ttu-id="886b5-102">Klasse unterstützt keine Automatisierung oder unterstützt die erwartete Schnittstelle nicht</span><span class="sxs-lookup"><span data-stu-id="886b5-102">Class does not support Automation or does not support expected interface</span></span>
<span data-ttu-id="886b5-103">Entweder macht die im Funktionsaufruf `GetObject` oder `CreateObject` angegebene Klasse eine Programmierschnittstelle nicht verfügbar, oder Sie haben ein Projekt von .dll in .exe oder umgekehrt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="886b5-103">Either the class you specified in the `GetObject` or `CreateObject` function call has not exposed a programmability interface, or you changed a project from .dll to .exe, or vice versa.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="886b5-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="886b5-104">To correct this error</span></span>  
  
1. <span data-ttu-id="886b5-105">Lesen Sie die Dokumentation zur Anwendung, mit der das Objekt erstellt wurde, um Beschränkungen hinsichtlich des Einsatzes von Automatisierung bei dieser Objektklasse herauszufinden.</span><span class="sxs-lookup"><span data-stu-id="886b5-105">Check the documentation of the application that created the object for limitations on the use of automation with this class of object.</span></span>  
  
2. <span data-ttu-id="886b5-106">Wenn Sie ein Projekt von .dll in .exe oder umgekehrt geändert haben, müssen Sie die Registrierung der alten .dll oder .exe manuell aufheben.</span><span class="sxs-lookup"><span data-stu-id="886b5-106">If you changed a project from .dll to .exe or vice versa, you must manually unregister the old .dll or .exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="886b5-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="886b5-107">See also</span></span>

- [<span data-ttu-id="886b5-108">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="886b5-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="886b5-109">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="886b5-109">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
