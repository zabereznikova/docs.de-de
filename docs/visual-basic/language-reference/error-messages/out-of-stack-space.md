---
title: Nicht genügend Stapelspeicher
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: 9ae604a9727413f2705d42a4b68f5a50b7dd3feb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349184"
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="44fa6-102">Nicht genügend Stapelspeicher (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44fa6-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="44fa6-103">Der Stapel ist ein Arbeitsbereich des Arbeitsspeichers, der dynamisch mit den Anforderungen Ihres ausführenden Programms vergrößert und verkleinert wird.</span><span class="sxs-lookup"><span data-stu-id="44fa6-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="44fa6-104">Die Grenzen wurden überschritten.</span><span class="sxs-lookup"><span data-stu-id="44fa6-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="44fa6-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="44fa6-105">To correct this error</span></span>  
  
1. <span data-ttu-id="44fa6-106">Überprüfen Sie, ob Prozeduren zu tief geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="44fa6-106">Check that procedures are not nested too deeply.</span></span>  
  
2. <span data-ttu-id="44fa6-107">Stellen Sie sicher, dass rekursive Prozeduren richtig</span><span class="sxs-lookup"><span data-stu-id="44fa6-107">Make sure recursive procedures terminate properly.</span></span>  
  
3. <span data-ttu-id="44fa6-108">Wenn lokale Variablen mehr lokalen Variablen Speicher benötigen, als verfügbar ist, versuchen Sie, einige Variablen auf Modulebene zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="44fa6-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="44fa6-109">Sie können auch alle Variablen in der Prozedur static deklarieren, indem Sie dem `Property`-, `Sub`-oder `Function`-Schlüsselwort mit `Static`vorangestellt sind.</span><span class="sxs-lookup"><span data-stu-id="44fa6-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="44fa6-110">Oder Sie können die `Static`-Anweisung verwenden, um einzelne statische Variablen innerhalb von Prozeduren zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="44fa6-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4. <span data-ttu-id="44fa6-111">Definieren Sie einige der Zeichen folgen fester Länge als Zeichen folgen variabler Länge neu, da Zeichen folgen fester Länge mehr Stapel Speicher als Zeichen folgen variabler Länge verwenden.</span><span class="sxs-lookup"><span data-stu-id="44fa6-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="44fa6-112">Sie können auch die Zeichenfolge auf Modulebene definieren, an der kein Stapel Speicherplatz erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="44fa6-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5. <span data-ttu-id="44fa6-113">Überprüfen Sie die Anzahl der aufgerufenen `DoEvents` Funktionsaufrufe, indem Sie im Dialogfeld `Calls` anzeigen, welche Prozeduren auf dem Stapel aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="44fa6-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6. <span data-ttu-id="44fa6-114">Stellen Sie sicher, dass Sie keine "Ereignis Cascade" verursacht haben, indem Sie ein Ereignis auslösen, das eine bereits auf dem Stapel bereits aufgerufenen Ereignis Prozedur aufruft.</span><span class="sxs-lookup"><span data-stu-id="44fa6-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="44fa6-115">Eine Ereignis Kaskadierung ähnelt einem nicht abgeschlossenen rekursiven Prozedur Aufruf, aber Sie ist weniger offensichtlich, da der-Befehl durch Visual Basic statt eines expliziten Aufrufes im Code erfolgt.</span><span class="sxs-lookup"><span data-stu-id="44fa6-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="44fa6-116">Verwenden Sie das Dialogfeld `Calls`, um anzuzeigen, welche Prozeduren auf dem Stapel aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="44fa6-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44fa6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44fa6-117">See also</span></span>

- [<span data-ttu-id="44fa6-118">Fenster "Arbeitsspeicher"</span><span class="sxs-lookup"><span data-stu-id="44fa6-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
