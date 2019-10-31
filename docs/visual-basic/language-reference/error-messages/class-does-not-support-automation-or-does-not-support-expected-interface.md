---
title: Klasse unterstützt keine Automatisierung oder unterstützt die erwartete Schnittstelle nicht
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: d249648748249af438ee6228cccc8e74f68407fb
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197532"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a><span data-ttu-id="44f39-102">Klasse unterstützt keine Automatisierung oder unterstützt die erwartete Schnittstelle nicht</span><span class="sxs-lookup"><span data-stu-id="44f39-102">Class does not support Automation or does not support expected interface</span></span>
<span data-ttu-id="44f39-103">Entweder macht die im Funktionsaufruf `GetObject` oder `CreateObject` angegebene Klasse eine Programmierschnittstelle nicht verfügbar, oder Sie haben ein Projekt von .dll in .exe oder umgekehrt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="44f39-103">Either the class you specified in the `GetObject` or `CreateObject` function call has not exposed a programmability interface, or you changed a project from .dll to .exe, or vice versa.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="44f39-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="44f39-104">To correct this error</span></span>  
  
1. <span data-ttu-id="44f39-105">Lesen Sie die Dokumentation zur Anwendung, mit der das Objekt erstellt wurde, um Beschränkungen hinsichtlich des Einsatzes von Automatisierung bei dieser Objektklasse herauszufinden.</span><span class="sxs-lookup"><span data-stu-id="44f39-105">Check the documentation of the application that created the object for limitations on the use of automation with this class of object.</span></span>  
  
2. <span data-ttu-id="44f39-106">Wenn Sie ein Projekt von .dll in .exe oder umgekehrt geändert haben, müssen Sie die Registrierung der alten .dll oder .exe manuell aufheben.</span><span class="sxs-lookup"><span data-stu-id="44f39-106">If you changed a project from .dll to .exe or vice versa, you must manually unregister the old .dll or .exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44f39-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44f39-107">See also</span></span>

- [<span data-ttu-id="44f39-108">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="44f39-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="44f39-109">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="44f39-109">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
