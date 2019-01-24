---
title: End &lt;Schlüsselwort&gt; Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: d65c921a1631cd38c4d0d1ab9b34db3d7e43a97e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654840"
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a><span data-ttu-id="4a6cb-102">End &lt;Schlüsselwort&gt; Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a6cb-102">End &lt;keyword&gt; Statement (Visual Basic)</span></span>

<span data-ttu-id="4a6cb-103">Wenn Sie ein zusätzliches Schlüsselwort gefolgt wird, beendet die Definition der Anweisungsblock, der durch dieses Schlüsselwort eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="4a6cb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a6cb-104">Syntax</span></span>

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
  
## <a name="parts"></a><span data-ttu-id="4a6cb-105">Teile</span><span class="sxs-lookup"><span data-stu-id="4a6cb-105">Parts</span></span>

|<span data-ttu-id="4a6cb-106">Segment</span><span class="sxs-lookup"><span data-stu-id="4a6cb-106">Part</span></span>|<span data-ttu-id="4a6cb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a6cb-107">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="4a6cb-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-108">Required.</span></span> <span data-ttu-id="4a6cb-109">Beendet die Definition des Programmierelements.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-109">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="4a6cb-110">Erforderlich, um eine `AddHandler` Accessor begonnen, die durch eine entsprechende `AddHandler` Anweisung in einem benutzerdefinierten [Event-Anweisung](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-110">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="4a6cb-111">Erforderlich, um eine Klassendefinition durch eine entsprechende begonnen [Class-Anweisung](class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-111">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="4a6cb-112">Erforderlich, um eine aufzählungsdefinition begonnen, die durch eine entsprechende [Enum-Anweisung](enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-112">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="4a6cb-113">Erforderlich, um eine `Custom` Ereignisdefinition begonnen, die durch eine entsprechende [Event-Anweisung](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-113">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="4a6cb-114">Erforderlich, um eine `Function` Definition der Prozedur durch eine entsprechende begonnen [Function-Anweisung](function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-114">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="4a6cb-115">Wenn die Ausführung findet eine `End Function` -Anweisung, die Steuerung an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-115">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="4a6cb-116">Erforderlich, um eine `Property` Definition der Prozedur durch eine entsprechende begonnen [Get Statement](get-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-116">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="4a6cb-117">Wenn die Ausführung findet eine `End Get` -Anweisung, die Steuerung an die Anweisung, die Anforderung den Wert der Eigenschaft zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-117">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="4a6cb-118">Erforderlich, um eine `If`... `Then`... `Else` -Blockdefinition durch eine entsprechende `If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-118">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="4a6cb-119">Finden Sie unter [Wenn... Klicken Sie dann... Else-Anweisung](if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-119">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="4a6cb-120">Erforderlich, um eine Schnittstellendefinition begonnen, die durch eine entsprechende [Interface-Anweisung](interface-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-120">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="4a6cb-121">Erforderlich, um eine angefangene durch eine entsprechende Moduldefinition [Module-Anweisung](module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-121">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="4a6cb-122">Erforderlich, um eine Namespace-Definition, die durch eine entsprechende begonnen [Namespace-Anweisung](namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-122">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="4a6cb-123">Erforderlich, um eine Operatordefinition begonnen, die durch eine entsprechende [Operator-Anweisung](operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-123">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="4a6cb-124">Erforderlich, um eine Eigenschaftsdefinition begonnen, die durch eine entsprechende [Property Statement](property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-124">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="4a6cb-125">Erforderlich, um eine `RaiseEvent` Accessor begonnen, die durch eine entsprechende `RaiseEvent` Anweisung in einem benutzerdefinierten [Event-Anweisung](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-125">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="4a6cb-126">Erforderlich, um eine `RemoveHandler` Accessor begonnen, die durch eine entsprechende `RemoveHandler` Anweisung in einem benutzerdefinierten [Event-Anweisung](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-126">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="4a6cb-127">Erforderlich, um eine `Select`... `Case` -Blockdefinition durch eine entsprechende `Select` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-127">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="4a6cb-128">Finden Sie unter [auswählen... Case-Anweisung](select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-128">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="4a6cb-129">Erforderlich, um eine `Property` Definition der Prozedur durch eine entsprechende begonnen [Set-Anweisung](set-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-129">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="4a6cb-130">Wenn die Ausführung findet eine `End Set` -Anweisung, die Steuerung an die Anweisung aus, durch den Wert der Eigenschaft zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-130">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="4a6cb-131">Erforderlich, um eine angefangene durch eine entsprechende Strukturdefinition [Structure-Anweisung](structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-131">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="4a6cb-132">Erforderlich, um eine `Sub` Definition der Prozedur durch eine entsprechende begonnen [Sub-Anweisung](sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-132">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="4a6cb-133">Wenn die Ausführung findet eine `End Sub` -Anweisung, die Steuerung an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-133">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="4a6cb-134">Erforderlich, um eine `SyncLock` -Blockdefinition durch eine entsprechende `SyncLock` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-134">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="4a6cb-135">Finden Sie unter [SyncLock-Anweisung](synclock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-135">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="4a6cb-136">Erforderlich, um eine `Try`... `Catch`... `Finally` -Blockdefinition durch eine entsprechende `Try` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-136">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="4a6cb-137">Finden Sie unter [testen... Catch... Finally-Anweisung](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-137">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="4a6cb-138">Erforderlich, um eine `While` Schleife begonnen, die durch eine entsprechende Definition `While` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-138">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="4a6cb-139">Finden Sie unter [während... While-Anweisung enden](while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-139">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="4a6cb-140">Erforderlich, um eine `With` -Blockdefinition durch eine entsprechende `With` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-140">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="4a6cb-141">Finden Sie unter [mit... With-Anweisung](with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-141">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="4a6cb-142">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="4a6cb-142">Directives</span></span>

<span data-ttu-id="4a6cb-143">Wenn Sie mit einem Nummernzeichen (`#`), wird die `End` Schlüsselwort beendet ein Präprozessorblock eingeführt, durch die entsprechende Direktive.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-143">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="4a6cb-144">Segment</span><span class="sxs-lookup"><span data-stu-id="4a6cb-144">Part</span></span>|<span data-ttu-id="4a6cb-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a6cb-145">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="4a6cb-146">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-146">Required.</span></span> <span data-ttu-id="4a6cb-147">Beendet die Definition des vorverarbeitung-Blocks.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-147">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="4a6cb-148">Erforderlich, um einen externen Quellblock begonnen, die durch eine entsprechende [#ExternalSource-Anweisung](../directives/externalsource-directive.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-148">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="4a6cb-149">Erforderlich, um einen für die bedingte Kompilierung-Block, der durch eine entsprechende begonnen `#If` Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-149">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="4a6cb-150">Finden Sie unter [#If... ... #Else-Anweisungen](../directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-150">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="4a6cb-151">Erforderlich, um ein Quellblock zu Region beenden durch eine entsprechende [#Region-Anweisung](../directives/region-directive.md).</span><span class="sxs-lookup"><span data-stu-id="4a6cb-151">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="4a6cb-152">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4a6cb-152">Remarks</span></span>

<span data-ttu-id="4a6cb-153">Die [End-Anweisung](end-statement.md), ohne zusätzliche Schlüsselwort beendet die Ausführung sofort.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-153">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="4a6cb-154">Hinweise für Entwickler intelligente Geräte</span><span class="sxs-lookup"><span data-stu-id="4a6cb-154">Smart Device Developer Notes</span></span>  

<span data-ttu-id="4a6cb-155">Die `End` Anweisung, ohne zusätzliche Schlüsselwort wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4a6cb-155">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6cb-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a6cb-156">See also</span></span>

- [<span data-ttu-id="4a6cb-157">End-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4a6cb-157">End Statement</span></span>](end-statement.md)
