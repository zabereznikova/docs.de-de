---
title: End &lt;Schlüsselwort&gt; -Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 8137434bfd8c26144d78b1761b784cdba4894eaf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a><span data-ttu-id="9be63-102">End &lt;Schlüsselwort&gt; -Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9be63-102">End &lt;keyword&gt; Statement (Visual Basic)</span></span>
<span data-ttu-id="9be63-103">Wenn ein zusätzliches Schlüsselwort folgt, beendet die Definition des der Anweisungsblock durch dieses Schlüsselwort eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9be63-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9be63-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9be63-104">Syntax</span></span>  
  
```  
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
  
## <a name="parts"></a><span data-ttu-id="9be63-105">Teile</span><span class="sxs-lookup"><span data-stu-id="9be63-105">Parts</span></span>  
 `End`  
 <span data-ttu-id="9be63-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9be63-106">Required.</span></span> <span data-ttu-id="9be63-107">Beendet die Definition des Programmierelements.</span><span class="sxs-lookup"><span data-stu-id="9be63-107">Terminates the definition of the programming element.</span></span>  
  
 `AddHandler`  
 <span data-ttu-id="9be63-108">Erforderlich, um eine `AddHandler` Zugriffsmethode, die durch eine entsprechende begonnen `AddHandler` -Anweisung in einer benutzerdefinierten [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-108">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Class`  
 <span data-ttu-id="9be63-109">Erforderlich, um die Definition einer Klasse, durch eine entsprechende begonnen [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-109">Required to terminate a class definition begun by a matching [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
 `Enum`  
 <span data-ttu-id="9be63-110">Erforderlich, um eine durch eine entsprechende begonnen aufzählungsdefinition [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-110">Required to terminate an enumeration definition begun by a matching [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
 `Event`  
 <span data-ttu-id="9be63-111">Erforderlich, um eine `Custom` Ereignisdefinition begonnen, die durch eine entsprechende [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-111">Required to terminate a `Custom` event definition begun by a matching [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Function`  
 <span data-ttu-id="9be63-112">Erforderlich, um eine `Function` Prozedurdefinition durch eine entsprechende begonnen [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-112">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="9be63-113">Wenn die Ausführung findet eine `End``Function` -Anweisung, die Steuerung an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9be63-113">If execution encounters an `End``Function` statement, control returns to the calling code.</span></span>  
  
 `Get`  
 <span data-ttu-id="9be63-114">Erforderlich, um eine `Property` Prozedurdefinition durch eine entsprechende begonnen [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-114">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md).</span></span> <span data-ttu-id="9be63-115">Wenn die Ausführung findet eine `End``Get` -Anweisung, die Steuerung an die Anweisung mit dem Wert der Eigenschaft angefordert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9be63-115">If execution encounters an `End``Get` statement, control returns to the statement requesting the property's value.</span></span>  
  
 `If`  
 <span data-ttu-id="9be63-116">Erforderlich, um eine `If`... `Then`... `Else` -Blockdefinition durch eine entsprechende `If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9be63-116">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="9be63-117">Finden Sie unter [Wenn... Dann... Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-117">See [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span>  
  
 `Interface`  
 <span data-ttu-id="9be63-118">Erforderlich, um eine durch eine entsprechende angefangene Schnittstellendefinition [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-118">Required to terminate an interface definition begun by a matching [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md).</span></span>  
  
 `Module`  
 <span data-ttu-id="9be63-119">Erforderlich, um eine durch eine entsprechende angefangene Moduldefinition [Modulanweisung](../../../visual-basic/language-reference/statements/module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-119">Required to terminate a module definition begun by a matching [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).</span></span>  
  
 `Namespace`  
 <span data-ttu-id="9be63-120">Erforderlich, um eine durch eine entsprechende angefangene Namespacedefinition [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-120">Required to terminate a namespace definition begun by a matching [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md).</span></span>  
  
 `Operator`  
 <span data-ttu-id="9be63-121">Erforderlich, um eine Operatordefinition begonnen, die durch eine entsprechende [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-121">Required to terminate an operator definition begun by a matching [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 `Property`  
 <span data-ttu-id="9be63-122">Erforderlich, um eine Eigenschaftsdefinition durch eine entsprechende begonnen [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-122">Required to terminate a property definition begun by a matching [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
 `RaiseEvent`  
 <span data-ttu-id="9be63-123">Erforderlich, um eine `RaiseEvent` Zugriffsmethode, die durch eine entsprechende begonnen `RaiseEvent` -Anweisung in einer benutzerdefinierten [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-123">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `RemoveHandler`  
 <span data-ttu-id="9be63-124">Erforderlich, um eine `RemoveHandler` Zugriffsmethode, die durch eine entsprechende begonnen `RemoveHandler` -Anweisung in einer benutzerdefinierten [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-124">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Select`  
 <span data-ttu-id="9be63-125">Erforderlich, um eine `Select`... `Case` -Blockdefinition durch eine entsprechende `Select` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9be63-125">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="9be63-126">Finden Sie unter [auswählen... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-126">See [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
 `Set`  
 <span data-ttu-id="9be63-127">Erforderlich, um eine `Property` Prozedurdefinition durch eine entsprechende begonnen [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-127">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md).</span></span> <span data-ttu-id="9be63-128">Wenn die Ausführung findet eine `End``Set` -Anweisung, die Steuerung an die Anweisung aus, durch den Wert der Eigenschaft zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9be63-128">If execution encounters an `End``Set` statement, control returns to the statement setting the property's value.</span></span>  
  
 `Structure`  
 <span data-ttu-id="9be63-129">Erforderlich, um eine durch eine entsprechende angefangene Strukturdefinition [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-129">Required to terminate a structure definition begun by a matching [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
 `Sub`  
 <span data-ttu-id="9be63-130">Erforderlich, um eine `Sub` Prozedurdefinition durch eine entsprechende begonnen [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-130">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span> <span data-ttu-id="9be63-131">Wenn die Ausführung findet eine `End``Sub` -Anweisung, die Steuerung an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9be63-131">If execution encounters an `End``Sub` statement, control returns to the calling code.</span></span>  
  
 `SyncLock`  
 <span data-ttu-id="9be63-132">Erforderlich, um eine `SyncLock` -Blockdefinition durch eine entsprechende `SyncLock` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9be63-132">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="9be63-133">Finden Sie unter [SyncLock-Anweisung](../../../visual-basic/language-reference/statements/synclock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-133">See [SyncLock Statement](../../../visual-basic/language-reference/statements/synclock-statement.md).</span></span>  
  
 `Try`  
 <span data-ttu-id="9be63-134">Erforderlich, um eine `Try`... `Catch`... `Finally` -Blockdefinition durch eine entsprechende `Try` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9be63-134">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="9be63-135">Finden Sie unter [versuchen... Catch... Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-135">See [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 `While`  
 <span data-ttu-id="9be63-136">Erforderlich, um eine `While` Schleife begonnen, die durch eine entsprechende Definition `While` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9be63-136">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="9be63-137">Finden Sie unter [während... While-Anweisung enden](../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-137">See [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
 `With`  
 <span data-ttu-id="9be63-138">Erforderlich, um eine `With` -Blockdefinition durch eine entsprechende `With` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9be63-138">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="9be63-139">Finden Sie unter [mit... With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-139">See [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9be63-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9be63-140">Remarks</span></span>  
 <span data-ttu-id="9be63-141">Die [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md), ohne zusätzliche Schlüsselwort beendet die Ausführung sofort.</span><span class="sxs-lookup"><span data-stu-id="9be63-141">The [End Statement](../../../visual-basic/language-reference/statements/end-statement.md), without an additional keyword, terminates execution immediately.</span></span>  
  
 <span data-ttu-id="9be63-142">Wenn ein Nummernzeichen vorangestellt (`#`), wird die `End` Schlüsselwort beendet einen vorab verarbeitetes Block, der durch die entsprechende Richtlinie eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9be63-142">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  
  
 `#End`  
 <span data-ttu-id="9be63-143">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9be63-143">Required.</span></span> <span data-ttu-id="9be63-144">Beendet die Definition des Präprozessorlauf Blocks.</span><span class="sxs-lookup"><span data-stu-id="9be63-144">Terminates the definition of the preprocessing block.</span></span>  
  
 `#ExternalSource`  
 <span data-ttu-id="9be63-145">Erforderlich, um einen externen Quellblock begonnen, die durch eine entsprechende [#ExternalSource-Direktive](../../../visual-basic/language-reference/directives/externalsource-directive.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-145">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md).</span></span>  
  
 `#If`  
 <span data-ttu-id="9be63-146">Erforderlich, um eine bedingte Kompilierung-Block, der durch eine entsprechende begonnen `#If` Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="9be63-146">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="9be63-147">Finden Sie unter [#If... ... #Else-Direktiven](../../../visual-basic/language-reference/directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-147">See [#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md).</span></span>  
  
 `#Region`  
 <span data-ttu-id="9be63-148">Erforderlich, um ein Quellblock-Region durch eine entsprechende begonnen [#Region-Direktive](../../../visual-basic/language-reference/directives/region-directive.md).</span><span class="sxs-lookup"><span data-stu-id="9be63-148">Required to terminate a source region block begun by a matching [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md).</span></span>  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="9be63-149">Entwicklerhinweise für intelligente Geräte</span><span class="sxs-lookup"><span data-stu-id="9be63-149">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="9be63-150">Die `End` -Anweisung ohne zusätzliche Schlüsselwort wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9be63-150">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be63-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9be63-151">See Also</span></span>  
 [<span data-ttu-id="9be63-152">End-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9be63-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
