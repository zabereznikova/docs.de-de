---
title: Imports-Anweisung (.NET-Namespace und Typ)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Imports
- imports
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
caps.latest.revision: "40"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 46cc78c2fd039fb56fd4d1b797f2d09cbe95d317
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="2de01-102">Imports-Anweisung (.NET-Namespace und Typ)</span><span class="sxs-lookup"><span data-stu-id="2de01-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="2de01-103">Ermöglicht das Typnamen ohne Namespacequalifikation referenziert werden.</span><span class="sxs-lookup"><span data-stu-id="2de01-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2de01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2de01-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="2de01-105">Teile</span><span class="sxs-lookup"><span data-stu-id="2de01-105">Parts</span></span>  
  
|<span data-ttu-id="2de01-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="2de01-106">Term</span></span>|<span data-ttu-id="2de01-107">Definition</span><span class="sxs-lookup"><span data-stu-id="2de01-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="2de01-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="2de01-108">Optional.</span></span> <span data-ttu-id="2de01-109">Ein *Importalias* oder Namen, die mit dem Code, um verweisen kann `namespace` anstelle der vollständigen Qualifizierungspfad.</span><span class="sxs-lookup"><span data-stu-id="2de01-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="2de01-110">Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="2de01-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="2de01-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2de01-111">Required.</span></span> <span data-ttu-id="2de01-112">Der vollqualifizierte Name des zu importierenden Namespaces.</span><span class="sxs-lookup"><span data-stu-id="2de01-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="2de01-113">Eine Zeichenfolge von Namespaces kann auf beliebigen Ebenen geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="2de01-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="2de01-114">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="2de01-114">Optional.</span></span> <span data-ttu-id="2de01-115">Der Name eines Programmierelements deklarierten im Namespace.</span><span class="sxs-lookup"><span data-stu-id="2de01-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="2de01-116">Ein Containerelement kann sein.</span><span class="sxs-lookup"><span data-stu-id="2de01-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2de01-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2de01-117">Remarks</span></span>  
 <span data-ttu-id="2de01-118">Die `Imports` -Anweisung ermöglicht es, Typen, die in einem bestimmten Namespace direkt verwiesen wird, enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2de01-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="2de01-119">Sie können einen einzelnen Namespace-Namen oder eine Zeichenfolge von geschachtelten Namespaces angeben.</span><span class="sxs-lookup"><span data-stu-id="2de01-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="2de01-120">Jeden geschachtelten Namespace wird vom nächsten höheren Ebene Namespace durch einen Punkt getrennt (`.`), wie im folgende Beispiel veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="2de01-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="2de01-121">Jeder Quelldatei kann eine beliebige Anzahl von enthalten `Imports` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="2de01-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="2de01-122">Diese müssen führen Sie die Option-Deklarationen, z. B. die `Option Strict` -Anweisung, und sie müssen vor stehen Deklarationen von Programmierelementen, z. B. `Module` oder `Class` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="2de01-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="2de01-123">Sie können `Imports` nur auf Dateiebene.</span><span class="sxs-lookup"><span data-stu-id="2de01-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="2de01-124">Dies bedeutet, dass der Deklarationskontext für den Import von eine Quelldatei muss und nicht mit Namespace, Klasse, Struktur, Modul, Schnittstelle, Prozedur oder Block.</span><span class="sxs-lookup"><span data-stu-id="2de01-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="2de01-125">Beachten Sie, dass die `Imports` Anweisung nimmt Elemente aus anderen Projekten und Assemblys für Ihr Projekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2de01-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="2de01-126">Importieren von ist nicht das Festlegen eines Verweises stattfinden.</span><span class="sxs-lookup"><span data-stu-id="2de01-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="2de01-127">Es erübrigt es sich nur um Namen zu qualifizieren, die bereits im Projekt verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2de01-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="2de01-128">Weitere Informationen finden Sie unter "Importieren von enthaltenen Elementen" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="2de01-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2de01-129">Sie können implizite definieren `Imports` -Anweisungen mithilfe der [Seite "Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2de01-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="2de01-130">Weitere Informationen finden Sie unter [wie: Hinzufügen oder Entfernen von importierten Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2de01-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="2de01-131">Importaliase</span><span class="sxs-lookup"><span data-stu-id="2de01-131">Import Aliases</span></span>  
 <span data-ttu-id="2de01-132">Ein *Importalias* den Alias für einen Namespace oder Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="2de01-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="2de01-133">Importaliase sind nützlich, wenn Sie mithilfe der Elemente mit dem gleichen Namen, die in einem oder mehreren Namespaces deklariert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="2de01-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="2de01-134">Weitere Informationen und ein Beispiel finden Sie unter "Qualifizieren eines Elementnamens" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="2de01-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="2de01-135">Sie sollten nicht deklarieren, ein Element auf Modulebene mit dem gleichen Namen wie `aliasname`.</span><span class="sxs-lookup"><span data-stu-id="2de01-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="2de01-136">Wenn Sie dies tun, Visual Basic-Compiler verwendet `aliasname` nur für den deklarierten Member und nicht länger als ein Importalias erkannt.</span><span class="sxs-lookup"><span data-stu-id="2de01-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="2de01-137">Obwohl die Syntax zum Deklarieren von ein Importalias verwendet wie zum Importieren einer XML-Namespacepräfix verwendet wird, unterscheiden sich die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="2de01-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="2de01-138">Ein Importalias kann als ein Ausdruck in Ihrem Code verwendet werden, während ein XML-Namespacepräfix nur in XML-Literalen oder XML-Achseneigenschaften als Präfix für eine qualifiziertes Element oder Attribut verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2de01-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="2de01-139">Elementnamen</span><span class="sxs-lookup"><span data-stu-id="2de01-139">Element Names</span></span>  
 <span data-ttu-id="2de01-140">Wenn Sie angeben `element`, muss darstellen einer *Containerelement*, d. h. ein Programmierelement, das andere Elemente enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="2de01-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="2de01-141">Containerelemente enthalten Klassen, Strukturen, Modulen, Schnittstellen und Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="2de01-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="2de01-142">Der Bereich der Elemente zur Verfügung gestellt wurden ein `Imports` Anweisung hängt davon ab, ob Sie angeben `element`.</span><span class="sxs-lookup"><span data-stu-id="2de01-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="2de01-143">Wenn Sie nur angeben, `namespace`, alle eindeutig benannten Member dieses Namespace und Mitglieder der Containerelemente in diesem Namespace, ohne Qualifizierung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2de01-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="2de01-144">Wenn Sie beide angeben `namespace` und `element`nur die Elemente dieses Elements ohne Qualifizierung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2de01-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2de01-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2de01-145">Example</span></span>  
 <span data-ttu-id="2de01-146">Das folgende Beispiel gibt alle Ordner im Verzeichnis C:\ mithilfe der <xref:System.IO.DirectoryInfo> Klasse.</span><span class="sxs-lookup"><span data-stu-id="2de01-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="2de01-147">Der Code hat keine `Imports` Anweisungen am Anfang der Datei.</span><span class="sxs-lookup"><span data-stu-id="2de01-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="2de01-148">Aus diesem Grund die `DirectoryInfo`, <xref:System.Text.StringBuilder>, und <xref:Microsoft.VisualBasic.ControlChars.CrLf> Verweise mit Namespaces vollständig qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="2de01-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="2de01-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2de01-149">Example</span></span>  
 <span data-ttu-id="2de01-150">Das folgende Beispiel schließt `Imports` Anweisungen für die Namespaces verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2de01-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="2de01-151">Aus diesem Grund müssen die Typen nicht mit den Namespaces vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="2de01-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]  
  
 [!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="2de01-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2de01-152">Example</span></span>  
 <span data-ttu-id="2de01-153">Das folgende Beispiel schließt `Imports` -Anweisungen, die Aliase für die referenzierten Namespaces erstellen.</span><span class="sxs-lookup"><span data-stu-id="2de01-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="2de01-154">Die Typen werden mit den Aliasen qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="2de01-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]  
  
 [!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="2de01-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2de01-155">Example</span></span>  
 <span data-ttu-id="2de01-156">Das folgende Beispiel schließt `Imports` -Anweisungen, die Aliase für den referenzierten Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2de01-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="2de01-157">Aliase werden verwendet, um die Typen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2de01-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]  
  
 [!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2de01-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2de01-158">See Also</span></span>  
 [<span data-ttu-id="2de01-159">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2de01-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="2de01-160">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2de01-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="2de01-161">Verweise und die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2de01-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="2de01-162">Imports-Anweisung (XML-Namespace)</span><span class="sxs-lookup"><span data-stu-id="2de01-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [<span data-ttu-id="2de01-163">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="2de01-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
