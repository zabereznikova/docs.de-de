---
title: Attributliste (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: dc1c456c71efb3cc6e60a8fdc77384e65975f110
ms.openlocfilehash: 6aea239e2e0d8a266b8eb6ba2876fb109e077c46
ms.contentlocale: de-de
ms.lasthandoff: 05/15/2017

---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="971c9-102">Attributliste (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="971c9-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="971c9-103">Gibt die Attribute, die auf ein deklariertes Programmierelement angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="971c9-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="971c9-104">Mehrere Attribute werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="971c9-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="971c9-105">Folgendes ist die Syntax für ein Attribut.</span><span class="sxs-lookup"><span data-stu-id="971c9-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="971c9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="971c9-106">Syntax</span></span>  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="971c9-107">Teile</span><span class="sxs-lookup"><span data-stu-id="971c9-107">Parts</span></span>  
 `attributemodifier`  
 <span data-ttu-id="971c9-108">Erforderlich für Attribute, die am Anfang einer Quelldatei angewendet.</span><span class="sxs-lookup"><span data-stu-id="971c9-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="971c9-109">Kann [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) oder [Modul](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="971c9-109">Can be [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) or [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span></span>  
  
 `attributename`  
 <span data-ttu-id="971c9-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="971c9-110">Required.</span></span> <span data-ttu-id="971c9-111">Der Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="971c9-111">Name of the attribute.</span></span>  
  
 `attributearguments`  
 <span data-ttu-id="971c9-112">Optional.</span><span class="sxs-lookup"><span data-stu-id="971c9-112">Optional.</span></span> <span data-ttu-id="971c9-113">Liste der Positionsargumente für dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="971c9-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="971c9-114">Mehrere Argumente werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="971c9-114">Multiple arguments are separated by commas.</span></span>  
  
 `attributeinitializer`  
 <span data-ttu-id="971c9-115">Optional.</span><span class="sxs-lookup"><span data-stu-id="971c9-115">Optional.</span></span> <span data-ttu-id="971c9-116">Liste der Variablen oder Eigenschaft-Initialisierer für dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="971c9-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="971c9-117">Mehrere Initialisierer werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="971c9-117">Multiple initializers are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="971c9-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="971c9-118">Remarks</span></span>  
 <span data-ttu-id="971c9-119">Sie können ein oder mehrere Attribute auf beinahe jedes Programmierelement (Typen, Prozeduren, Eigenschaften usw.) anwenden.</span><span class="sxs-lookup"><span data-stu-id="971c9-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="971c9-120">Attribute werden in den Metadaten der Assembly, und können Sie Ihren Code versehen oder angeben, wie bestimmten Programmierelements verwenden.</span><span class="sxs-lookup"><span data-stu-id="971c9-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="971c9-121">Von Visual Basic und .NET Framework definierten Attribute angewendet werden, und Sie können eigene Attribute definieren.</span><span class="sxs-lookup"><span data-stu-id="971c9-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="971c9-122">Weitere Hinweise zum Verwenden von Attributen finden Sie unter [Attributes Overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="971c9-122">For more information on when to use attributes, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="971c9-123">Informationen über Attributnamen finden Sie unter [Elementnamen deklariert](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="971c9-123">For information on attribute names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="971c9-124">Regeln</span><span class="sxs-lookup"><span data-stu-id="971c9-124">Rules</span></span>  
  
-   <span data-ttu-id="971c9-125">**Platzierung.**</span><span class="sxs-lookup"><span data-stu-id="971c9-125">**Placement.**</span></span> <span data-ttu-id="971c9-126">Sie können Attribute auf die meisten deklarierten Programmierelemente anwenden.</span><span class="sxs-lookup"><span data-stu-id="971c9-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="971c9-127">Um ein oder mehrere Attribute anzuwenden, platzieren Sie ein *Attributblock* am Anfang der Elementdeklaration.</span><span class="sxs-lookup"><span data-stu-id="971c9-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="971c9-128">Jeder Eintrag in der Attributliste gibt ein Attribut aus, die Sie anwenden möchten und die Modifizierer und die Argumente für diesen Aufruf des Attributs verwendete.</span><span class="sxs-lookup"><span data-stu-id="971c9-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
-   <span data-ttu-id="971c9-129">**Spitze Klammern.**</span><span class="sxs-lookup"><span data-stu-id="971c9-129">**Angle Brackets.**</span></span> <span data-ttu-id="971c9-130">Wenn Sie eine Attributliste angeben, müssen Sie es in spitze Klammern einschließen ("`<`"und"`>`").</span><span class="sxs-lookup"><span data-stu-id="971c9-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
-   <span data-ttu-id="971c9-131">**Teil der Deklaration.**</span><span class="sxs-lookup"><span data-stu-id="971c9-131">**Part of the Declaration.**</span></span> <span data-ttu-id="971c9-132">Das Attribut muss Teil der Elementdeklaration keine separate Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="971c9-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="971c9-133">Können Sie die Zeilenfortsetzungszeichenfolge (" `_`") die deklarationsanweisung auf mehrere Zeilen von Quellcode zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="971c9-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
-   <span data-ttu-id="971c9-134">**Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="971c9-134">**Modifiers.**</span></span> <span data-ttu-id="971c9-135">Ein Attributmodifizierer (`Assembly` oder `Module`) ist erforderlich für jedes Attribut auf ein Programmierelement am Anfang einer Quelldatei angewendet.</span><span class="sxs-lookup"><span data-stu-id="971c9-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="971c9-136">Attributmodifizierer dürfen nicht auf Attribute, die auf Elemente, die nicht am Anfang einer Quelldatei angewendet.</span><span class="sxs-lookup"><span data-stu-id="971c9-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
-   <span data-ttu-id="971c9-137">**Argumente.**</span><span class="sxs-lookup"><span data-stu-id="971c9-137">**Arguments.**</span></span> <span data-ttu-id="971c9-138">Alle Variablen oder Eigenschaft-Initialisierer müssen alle positionelle Argumente für ein Attribut vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="971c9-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="971c9-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="971c9-139">Example</span></span>  
 <span data-ttu-id="971c9-140">Im folgenden Beispiel wird das <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut auf eine Skelettdefinition einer `Function` Prozedur.</xref:System.Runtime.InteropServices.DllImportAttribute></span><span class="sxs-lookup"><span data-stu-id="971c9-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 <span data-ttu-id="971c9-141">[!code-vb[VbVbalrStatements&#1;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="971c9-141">[!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]</span></span>  
  
 <span data-ttu-id="971c9-142"><xref:System.Runtime.InteropServices.DllImportAttribute>Gibt an, dass die attributierte Prozedur einen Einstiegspunkt in eine nicht verwaltete Dynamic Link Library (DLL) darstellt.</xref:System.Runtime.InteropServices.DllImportAttribute></span><span class="sxs-lookup"><span data-stu-id="971c9-142"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="971c9-143">Das Attribut stellt den Namen der DLL als positionelle Argumente und andere Informationen als Variable Initialisierer bereit.</span><span class="sxs-lookup"><span data-stu-id="971c9-143">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="971c9-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="971c9-144">See Also</span></span>  
 <span data-ttu-id="971c9-145">[Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) </span><span class="sxs-lookup"><span data-stu-id="971c9-145">[Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) </span></span>  
<span data-ttu-id="971c9-146"> [Modul \<Schlüsselwort >](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span><span class="sxs-lookup"><span data-stu-id="971c9-146"> [Module \<keyword>](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span></span>  
<span data-ttu-id="971c9-147"> [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="971c9-147"> [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="971c9-148"> [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)</span><span class="sxs-lookup"><span data-stu-id="971c9-148"> [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)</span></span>

