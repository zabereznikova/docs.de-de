---
title: End <keyword>-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 87f4724cc036e6e0bdf0b558854a4034f45b9ab5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343740"
---
# <a name="end-keyword-statement-visual-basic"></a><span data-ttu-id="f4fdb-102">End \<-Schlüsselwort > Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4fdb-102">End \<keyword> Statement (Visual Basic)</span></span>

<span data-ttu-id="f4fdb-103">Wenn ein zusätzliches Schlüsselwort folgt, beendet die Definition des von diesem Schlüsselwort eingeführten Anweisungsblocks.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="f4fdb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4fdb-104">Syntax</span></span>

```vb
End AddHandler
End Class
End Enum
End Event
End Function
End Get
End If
End Interface
End Module
End Namespace
End Operator
End Property
End RaiseEvent  
End RemoveHandler  
End Select
End Set
End Structure
End Sub
End SyncLock
End Try
End While
End With  
```  
  
## <a name="parts"></a><span data-ttu-id="f4fdb-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="f4fdb-105">Parts</span></span>

|<span data-ttu-id="f4fdb-106">-Komponente</span><span class="sxs-lookup"><span data-stu-id="f4fdb-106">Part</span></span>|<span data-ttu-id="f4fdb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4fdb-107">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="f4fdb-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="f4fdb-108">Required.</span></span> <span data-ttu-id="f4fdb-109">Beendet die Definition des Programmier Elements.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-109">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="f4fdb-110">Erforderlich, um einen `AddHandler` Accessor zu beenden, der durch eine übereinstimmende `AddHandler` Anweisung in einer benutzerdefinierten [Ereignis Anweisung](event-statement.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-110">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="f4fdb-111">Erforderlich, um eine Klassendefinition zu beenden, die von einer entsprechenden [Class-Anweisung](class-statement.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-111">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="f4fdb-112">Erforderlich, um eine Enumerationsdefinition zu beenden, die von einer entsprechenden [enum-Anweisung](enum-statement.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-112">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="f4fdb-113">Erforderlich, um eine `Custom` Ereignis Definition zu beenden, die von einer entsprechenden [Ereignis Anweisung](event-statement.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-113">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="f4fdb-114">Erforderlich, um eine `Function` Prozedur Definition zu beenden, die von einer übereinstimmenden [Funktions Anweisung](function-statement.md)gestartet wurde</span><span class="sxs-lookup"><span data-stu-id="f4fdb-114">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="f4fdb-115">Wenn die Ausführung auf eine `End Function` Anweisung trifft, wird die Steuerung an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-115">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="f4fdb-116">Erforderlich, um eine `Property` Prozedur Definition zu beenden, die von einer passenden [Get-Anweisung](get-statement.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-116">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="f4fdb-117">Wenn die Ausführung auf eine `End Get` Anweisung trifft, kehrt die Steuerung zur Anweisung zurück, die den Wert der Eigenschaft anfordert.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-117">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="f4fdb-118">Erforderlich, um eine `If`...`Then`...`Else` Block Definition zu beenden, die von einer übereinstimmenden `If` Anweisung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-118">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="f4fdb-119">Prüfen Sie, [ob... Dann... Else-Anweisung](if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f4fdb-119">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="f4fdb-120">Erforderlich, um eine Schnittstellen Definition zu beenden, die mit einer übereinstimmenden [Schnittstellen Anweisung](interface-statement.md)begonnen wurde</span><span class="sxs-lookup"><span data-stu-id="f4fdb-120">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="f4fdb-121">Erforderlich, um eine Modul Definition zu beenden, die von einer entsprechenden [Modul Anweisung](module-statement.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-121">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="f4fdb-122">Erforderlich, um eine Namespace Definition zu beenden, die von einer entsprechenden [Namespace-Anweisung](namespace-statement.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-122">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="f4fdb-123">Erforderlich, um eine Operator Definition zu beenden, die von einer entsprechenden [Operator Anweisung](operator-statement.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-123">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="f4fdb-124">Erforderlich, um eine Eigenschafts Definition zu beenden, die von einer entsprechenden [Eigenschafts Anweisung](property-statement.md)gestartet wurde</span><span class="sxs-lookup"><span data-stu-id="f4fdb-124">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="f4fdb-125">Erforderlich, um einen `RaiseEvent` Accessor zu beenden, der durch eine übereinstimmende `RaiseEvent` Anweisung in einer benutzerdefinierten [Ereignis Anweisung](event-statement.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-125">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="f4fdb-126">Erforderlich, um einen `RemoveHandler` Accessor zu beenden, der durch eine übereinstimmende `RemoveHandler` Anweisung in einer benutzerdefinierten [Ereignis Anweisung](event-statement.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-126">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="f4fdb-127">Erforderlich, um eine `Select`...`Case` Block Definition zu beenden, die von einer übereinstimmenden `Select` Anweisung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-127">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="f4fdb-128">Siehe [auswählen... Case-Anweisung](select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f4fdb-128">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="f4fdb-129">Erforderlich, um eine `Property` Prozedur Definition zu beenden, die von einer entsprechenden [Set-Anweisung](set-statement.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-129">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="f4fdb-130">Wenn die Ausführung auf eine `End Set` Anweisung trifft, kehrt die Steuerung zur-Anweisung zurück, die den Wert der Eigenschaft festlegt.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-130">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="f4fdb-131">Erforderlich, um eine Struktur Definition zu beenden, die von einer entsprechenden [Structure-Anweisung](structure-statement.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-131">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="f4fdb-132">Erforderlich, um eine `Sub` Prozedur Definition zu beenden, die von einer entsprechenden [unter Anweisung](sub-statement.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-132">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="f4fdb-133">Wenn die Ausführung auf eine `End Sub` Anweisung trifft, wird die Steuerung an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-133">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="f4fdb-134">Erforderlich, um eine `SyncLock` Block Definition zu beenden, die von einer übereinstimmenden `SyncLock` Anweisung gestartet wird</span><span class="sxs-lookup"><span data-stu-id="f4fdb-134">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="f4fdb-135">Siehe [SyncLock-Anweisung](synclock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f4fdb-135">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="f4fdb-136">Erforderlich, um eine `Try`...`Catch`...`Finally` Block Definition zu beenden, die von einer übereinstimmenden `Try` Anweisung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-136">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="f4fdb-137">Siehe [ausprobieren... Catch... Abschließend-Anweisung](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f4fdb-137">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="f4fdb-138">Erforderlich, um eine `While` Schleifen Definition zu beenden, die von einer entsprechenden `While` Anweisung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-138">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="f4fdb-139">Siehe [while... End While-Anweisung](while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f4fdb-139">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="f4fdb-140">Erforderlich, um eine `With` Block Definition zu beenden, die von einer übereinstimmenden `With` Anweisung gestartet wird</span><span class="sxs-lookup"><span data-stu-id="f4fdb-140">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="f4fdb-141">Weitere Informationen finden Sie [unter... End with-Anweisung](with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f4fdb-141">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="f4fdb-142">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="f4fdb-142">Directives</span></span>

<span data-ttu-id="f4fdb-143">Wenn ein Nummern Zeichen (`#`) vorangestellt ist, beendet das `End`-Schlüsselwort einen Vorverarbeitungs Block, der von der entsprechenden-Direktive eingeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-143">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="f4fdb-144">-Komponente</span><span class="sxs-lookup"><span data-stu-id="f4fdb-144">Part</span></span>|<span data-ttu-id="f4fdb-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4fdb-145">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="f4fdb-146">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="f4fdb-146">Required.</span></span> <span data-ttu-id="f4fdb-147">Beendet die Definition des Vorverarbeitungs Blocks.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-147">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="f4fdb-148">Erforderlich, um einen externen Quell Block zu beenden, der durch eine übereinstimmende [#ExternalSource-Direktive](../directives/externalsource-directive.md)</span><span class="sxs-lookup"><span data-stu-id="f4fdb-148">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="f4fdb-149">Erforderlich, um einen Block für die bedingte Kompilierung zu beenden, der durch eine übereinstimmende `#If`</span><span class="sxs-lookup"><span data-stu-id="f4fdb-149">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="f4fdb-150">Siehe [#If... Dann... #else Direktiven](../directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="f4fdb-150">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="f4fdb-151">Muss einen Quell Regions Block beenden, der durch eine übereinstimmende [#Region-Direktive](../directives/region-directive.md)gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-151">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="f4fdb-152">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f4fdb-152">Remarks</span></span>

<span data-ttu-id="f4fdb-153">Die [End-Anweisung](end-statement.md)ohne zusätzliches Schlüsselwort beendet die Ausführung sofort.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-153">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="f4fdb-154">Entwickler Hinweise zu intelligenten Geräten</span><span class="sxs-lookup"><span data-stu-id="f4fdb-154">Smart Device Developer Notes</span></span>  

<span data-ttu-id="f4fdb-155">Die `End`-Anweisung ohne zusätzliches Schlüsselwort wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f4fdb-155">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4fdb-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4fdb-156">See also</span></span>

- [<span data-ttu-id="f4fdb-157">End-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f4fdb-157">End Statement</span></span>](end-statement.md)
