---
title: Attributliste (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: adfb980380bb787280715ca0185950657e174eb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="944d3-102">Attributliste (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="944d3-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="944d3-103">Gibt die Attribute, die auf eine deklarierte Programmierelement angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="944d3-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="944d3-104">Mehrere Attribute werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="944d3-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="944d3-105">Nachfolgend ist die Syntax für ein Attribut.</span><span class="sxs-lookup"><span data-stu-id="944d3-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="944d3-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="944d3-106">Syntax</span></span>  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="944d3-107">Teile</span><span class="sxs-lookup"><span data-stu-id="944d3-107">Parts</span></span>  
 `attributemodifier`  
 <span data-ttu-id="944d3-108">Erforderlich für Attribute, die am Anfang einer Quelldatei angewendet.</span><span class="sxs-lookup"><span data-stu-id="944d3-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="944d3-109">Kann [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) oder [Modul](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="944d3-109">Can be [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) or [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span></span>  
  
 `attributename`  
 <span data-ttu-id="944d3-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="944d3-110">Required.</span></span> <span data-ttu-id="944d3-111">Der Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="944d3-111">Name of the attribute.</span></span>  
  
 `attributearguments`  
 <span data-ttu-id="944d3-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="944d3-112">Optional.</span></span> <span data-ttu-id="944d3-113">Liste der Positionsargumente für dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="944d3-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="944d3-114">Mehrere Argumente werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="944d3-114">Multiple arguments are separated by commas.</span></span>  
  
 `attributeinitializer`  
 <span data-ttu-id="944d3-115">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="944d3-115">Optional.</span></span> <span data-ttu-id="944d3-116">Liste der Variablen oder Eigenschaft-Initialisierer für dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="944d3-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="944d3-117">Mehrere Initialisierer werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="944d3-117">Multiple initializers are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="944d3-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="944d3-118">Remarks</span></span>  
 <span data-ttu-id="944d3-119">Sie können ein oder mehrere Attribute auf fast alle Programmierelement (Typen, Prozeduren, Eigenschaften und So weiter) anwenden.</span><span class="sxs-lookup"><span data-stu-id="944d3-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="944d3-120">Attribute, die in den Metadaten der Assembly angezeigt werden, und können Sie kommentieren von Code oder gibt an, wie ein bestimmtes Programmierelement verwenden.</span><span class="sxs-lookup"><span data-stu-id="944d3-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="944d3-121">Vom Visual Basic und .NET Framework definierten Attribute angewendet werden, und Sie können eigene Attribute definieren.</span><span class="sxs-lookup"><span data-stu-id="944d3-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="944d3-122">Weitere Informationen dazu, wann zum Verwenden von Attributen finden Sie unter [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="944d3-122">For more information on when to use attributes, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="944d3-123">Informationen über Attributnamen finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="944d3-123">For information on attribute names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="944d3-124">Regeln</span><span class="sxs-lookup"><span data-stu-id="944d3-124">Rules</span></span>  
  
-   <span data-ttu-id="944d3-125">**Platzierung.**</span><span class="sxs-lookup"><span data-stu-id="944d3-125">**Placement.**</span></span> <span data-ttu-id="944d3-126">Sie können Attribute, die meisten deklarierten Programmierelementen anwenden.</span><span class="sxs-lookup"><span data-stu-id="944d3-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="944d3-127">Zum Anwenden von einem oder mehreren Attributen, die Sie setzen eine *Attributblock* am Anfang der Deklaration des Elements.</span><span class="sxs-lookup"><span data-stu-id="944d3-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="944d3-128">Jeder Eintrag in der Attributliste gibt ein Attribut, die Sie anwenden möchten und die Modifizierer und die Argumente, die Sie für diesen Aufruf des Attributs verwenden.</span><span class="sxs-lookup"><span data-stu-id="944d3-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
-   <span data-ttu-id="944d3-129">**Spitzen Klammern.**</span><span class="sxs-lookup"><span data-stu-id="944d3-129">**Angle Brackets.**</span></span> <span data-ttu-id="944d3-130">Wenn Sie eine Liste der Attribute angeben, müssen Sie es in spitzen Klammern einschließen ("`<`"und"`>`").</span><span class="sxs-lookup"><span data-stu-id="944d3-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
-   <span data-ttu-id="944d3-131">**Teil der Deklaration.**</span><span class="sxs-lookup"><span data-stu-id="944d3-131">**Part of the Declaration.**</span></span> <span data-ttu-id="944d3-132">Das Attribut muss Teil der Deklaration des Elements, keine separate Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="944d3-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="944d3-133">Sie können die Zeilenfortsetzungszeichenfolge (" `_`") der deklarationsanweisung auf mehrere Quellcodezeilen zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="944d3-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
-   <span data-ttu-id="944d3-134">**Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="944d3-134">**Modifiers.**</span></span> <span data-ttu-id="944d3-135">Ein Attributmodifizierer (`Assembly` oder `Module`) ist erforderlich für jedes Attribut auf ein Programmierelement am Anfang einer Quelldatei angewendet.</span><span class="sxs-lookup"><span data-stu-id="944d3-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="944d3-136">Attributmodifizierer dürfen nicht auf Attribute, die auf Elemente, die nicht am Anfang einer Quelldatei angewendet.</span><span class="sxs-lookup"><span data-stu-id="944d3-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
-   <span data-ttu-id="944d3-137">**Argumente.**</span><span class="sxs-lookup"><span data-stu-id="944d3-137">**Arguments.**</span></span> <span data-ttu-id="944d3-138">Alle Variablen oder Eigenschaft-Initialisierer müssen alle Positionsargumente für ein Attribut vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="944d3-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="944d3-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="944d3-139">Example</span></span>  
 <span data-ttu-id="944d3-140">Das folgende Beispiel wendet die <xref:System.Runtime.InteropServices.DllImportAttribute> -Attribut auf eine rumpfdefinition einer `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="944d3-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <span data-ttu-id="944d3-141"><xref:System.Runtime.InteropServices.DllImportAttribute>Gibt an, dass die attributierte Prozedur einen Einstiegspunkt in eine nicht verwaltete Dynamic Link Library (DLL) darstellt.</span><span class="sxs-lookup"><span data-stu-id="944d3-141"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="944d3-142">Das Attribut stellt den Namen der DLL als positionelle Argumente und den anderen Informationen als Variable Initialisierer.</span><span class="sxs-lookup"><span data-stu-id="944d3-142">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="944d3-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="944d3-143">See Also</span></span>  
 [<span data-ttu-id="944d3-144">Assembly</span><span class="sxs-lookup"><span data-stu-id="944d3-144">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [<span data-ttu-id="944d3-145">Module \<<schlüsselwort></span><span class="sxs-lookup"><span data-stu-id="944d3-145">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="944d3-146">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="944d3-146">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="944d3-147">Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code</span><span class="sxs-lookup"><span data-stu-id="944d3-147">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
