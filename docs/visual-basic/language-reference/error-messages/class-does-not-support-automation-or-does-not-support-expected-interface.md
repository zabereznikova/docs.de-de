---
title: Klasse unterstützt keine Automatisierung oder unterstützt die erwartete Schnittstelle nicht
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: 856c3f5ef503a7e5919e9e602532c56d9557482f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415400"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a><span data-ttu-id="73364-102">Klasse unterstützt keine Automatisierung oder unterstützt die erwartete Schnittstelle nicht</span><span class="sxs-lookup"><span data-stu-id="73364-102">Class does not support Automation or does not support expected interface</span></span>
<span data-ttu-id="73364-103">Entweder macht die im Funktionsaufruf `GetObject` oder `CreateObject` angegebene Klasse eine Programmierschnittstelle nicht verfügbar, oder Sie haben ein Projekt von .dll in .exe oder umgekehrt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="73364-103">Either the class you specified in the `GetObject` or `CreateObject` function call has not exposed a programmability interface, or you changed a project from .dll to .exe, or vice versa.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="73364-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="73364-104">To correct this error</span></span>  
  
1. <span data-ttu-id="73364-105">Lesen Sie die Dokumentation zur Anwendung, mit der das Objekt erstellt wurde, um Beschränkungen hinsichtlich des Einsatzes von Automatisierung bei dieser Objektklasse herauszufinden.</span><span class="sxs-lookup"><span data-stu-id="73364-105">Check the documentation of the application that created the object for limitations on the use of automation with this class of object.</span></span>  
  
2. <span data-ttu-id="73364-106">Wenn Sie ein Projekt von .dll in .exe oder umgekehrt geändert haben, müssen Sie die Registrierung der alten .dll oder .exe manuell aufheben.</span><span class="sxs-lookup"><span data-stu-id="73364-106">If you changed a project from .dll to .exe or vice versa, you must manually unregister the old .dll or .exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73364-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="73364-107">See also</span></span>

- [<span data-ttu-id="73364-108">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="73364-108">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="73364-109">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="73364-109">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
