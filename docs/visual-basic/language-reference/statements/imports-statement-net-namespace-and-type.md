---
title: Imports-Anweisung (.NET Namespace und Typ) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Imports
- imports
dev_langs:
- VB
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
caps.latest.revision: 40
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: af177874c3278efd348b53a2b74b4d49d6628c61
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="b4c04-102">Imports-Anweisung (.NET-Namespace und Typ)</span><span class="sxs-lookup"><span data-stu-id="b4c04-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="b4c04-103">Ermöglicht Typnamen ohne Kennzeichnung durch einen Namespace verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b4c04-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4c04-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4c04-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="b4c04-105">Teile</span><span class="sxs-lookup"><span data-stu-id="b4c04-105">Parts</span></span>  
  
|<span data-ttu-id="b4c04-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="b4c04-106">Term</span></span>|<span data-ttu-id="b4c04-107">Definition</span><span class="sxs-lookup"><span data-stu-id="b4c04-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="b4c04-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="b4c04-108">Optional.</span></span> <span data-ttu-id="b4c04-109">Ein *importieren Alias* oder den Namen, die mit dem Code, um verweisen kann `namespace` anstelle der vollständigen Qualifizierungspfad.</span><span class="sxs-lookup"><span data-stu-id="b4c04-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="b4c04-110">Finden Sie unter [deklarierten Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="b4c04-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="b4c04-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4c04-111">Required.</span></span> <span data-ttu-id="b4c04-112">Der vollqualifizierte Name des zu importierenden Namespace.</span><span class="sxs-lookup"><span data-stu-id="b4c04-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="b4c04-113">Eine Zeichenfolge mit Namespaces kann auf allen Ebenen geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="b4c04-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="b4c04-114">Optional.</span><span class="sxs-lookup"><span data-stu-id="b4c04-114">Optional.</span></span> <span data-ttu-id="b4c04-115">Der Name eines Programmierelements deklarierten im Namespace.</span><span class="sxs-lookup"><span data-stu-id="b4c04-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="b4c04-116">Containerelement kann sein.</span><span class="sxs-lookup"><span data-stu-id="b4c04-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4c04-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4c04-117">Remarks</span></span>  
 <span data-ttu-id="b4c04-118">Die `Imports` -Anweisung ermöglicht die Typen, die in einem bestimmten Namespace direkte Verweise auf enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b4c04-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="b4c04-119">Sie können einen einzelnen Namespacenamen oder eine Zeichenfolge mit geschachtelten Namespaces angeben.</span><span class="sxs-lookup"><span data-stu-id="b4c04-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="b4c04-120">Jeden geschachtelten Namespace ist aus dem nächsten höherer Ebene Namespace durch einen Punkt getrennt (`.`), wie im folgende Beispiel veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="b4c04-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="b4c04-121">Jede Quelldatei kann eine beliebige Anzahl von enthalten `Imports` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="b4c04-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="b4c04-122">Diese müssen führen Sie die Option-Deklarationen, wie z. B. die `Option Strict` -Anweisung, und sie müssen Deklarationen von Programmierelementen, wie z. B. voranstellen `Module` oder `Class` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="b4c04-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="b4c04-123">Sie können `Imports` nur auf Dateiebene.</span><span class="sxs-lookup"><span data-stu-id="b4c04-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="b4c04-124">Dies bedeutet, dass Deklarationskontext für den Import von muss eine Quelldatei und einen Namespace, Klasse, Struktur, Modul, Schnittstelle, Prozedur oder Block nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b4c04-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="b4c04-125">Beachten Sie, dass die `Imports` Anweisung macht nicht Elemente aus anderen Projekten und Assemblys im Projekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b4c04-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="b4c04-126">Importieren erfolgt der Festlegen eines Verweises.</span><span class="sxs-lookup"><span data-stu-id="b4c04-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="b4c04-127">Es entfernt nur die Notwendigkeit, qualifizieren Sie Namen, die bereits im Projekt verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b4c04-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="b4c04-128">Weitere Informationen finden Sie unter "Importieren von enthaltenden Elementen" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="b4c04-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4c04-129">Sie können implizite definieren `Imports` -Anweisungen mithilfe der [Seite "Verweise", Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b4c04-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="b4c04-130">Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen oder Entfernen von importierten Namespaces (Visual Basic)](http://msdn.microsoft.com/library/44cebec3-0ea0-47c2-8406-4edeab6a997e).</span><span class="sxs-lookup"><span data-stu-id="b4c04-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](http://msdn.microsoft.com/library/44cebec3-0ea0-47c2-8406-4edeab6a997e).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="b4c04-131">Importaliase</span><span class="sxs-lookup"><span data-stu-id="b4c04-131">Import Aliases</span></span>  
 <span data-ttu-id="b4c04-132">Ein *importieren Alias* definiert den Alias für einen Namespace oder Typ.</span><span class="sxs-lookup"><span data-stu-id="b4c04-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="b4c04-133">Importaliase sind nützlich, wenn Sie mithilfe der Elemente mit dem gleichen Namen, die in einem oder mehreren Namespaces deklariert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b4c04-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="b4c04-134">Weitere Informationen und ein Beispiel finden Sie unter "Qualifizieren eines Elementnamens" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="b4c04-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="b4c04-135">Deklarieren Sie nicht Mitglied auf Modulebene mit dem gleichen Namen wie `aliasname`.</span><span class="sxs-lookup"><span data-stu-id="b4c04-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="b4c04-136">Wenn Sie dies tun, Visual Basic-Compiler verwendet `aliasname` nur für den deklarierten Member und darf nicht mehr als ein Importalias erkannt.</span><span class="sxs-lookup"><span data-stu-id="b4c04-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="b4c04-137">Obwohl die Syntax zum Deklarieren eines Importalias für ein XML-Namespacepräfix importieren, verwendet wird, unterscheiden sich die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="b4c04-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="b4c04-138">Ein Importalias kann als Ausdruck in Ihrem Code verwendet werden, während ein XML-Namespacepräfix nur in XML-Literalen oder XML-Achseneigenschaften als Präfix für ein qualifiziertes Element oder Attributname verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b4c04-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="b4c04-139">Elementnamen</span><span class="sxs-lookup"><span data-stu-id="b4c04-139">Element Names</span></span>  
 <span data-ttu-id="b4c04-140">Wenn Sie angeben, `element`, muss darstellen einer *Containerelement*, d. h. ein Programmierelement, das andere Elemente enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="b4c04-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="b4c04-141">Container-Elemente enthalten Klassen, Strukturen, Module, Schnittstellen und Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="b4c04-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="b4c04-142">Der Gültigkeitsbereich der Elemente zur Verfügung gestellt wurden ein `Imports` Anweisung, hängt davon ab, ob angegeben `element`.</span><span class="sxs-lookup"><span data-stu-id="b4c04-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="b4c04-143">Wenn Sie lediglich angeben `namespace`, alle eindeutig benannten Member dieses Namespaces und Member der Containerelemente in diesem Namespace, ohne Qualifizierung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b4c04-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="b4c04-144">Wenn Sie beide angeben `namespace` und `element`, werden nur die Member dieses Elements ohne Qualifizierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b4c04-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4c04-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4c04-145">Example</span></span>  
 <span data-ttu-id="b4c04-146">Das folgende Beispiel gibt alle Ordner im Verzeichnis C:\ mithilfe der <xref:System.IO.DirectoryInfo>Klasse.</xref:System.IO.DirectoryInfo></span><span class="sxs-lookup"><span data-stu-id="b4c04-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="b4c04-147">Der Code verfügt über keine `Imports` -Anweisungen am Anfang der Datei.</span><span class="sxs-lookup"><span data-stu-id="b4c04-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="b4c04-148">Aus diesem Grund die `DirectoryInfo`, <xref:System.Text.StringBuilder>, und <xref:Microsoft.VisualBasic.ControlChars.CrLf>Verweise sind mit den Namespaces alle vollqualifiziert.</xref:Microsoft.VisualBasic.ControlChars.CrLf> </xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="b4c04-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 <span data-ttu-id="b4c04-149">[!code-vb[VbVbalrStatements&#152;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b4c04-149">[!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4c04-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4c04-150">Example</span></span>  
 <span data-ttu-id="b4c04-151">Das folgende Beispiel schließt `Imports` Anweisungen für die Namespaces verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b4c04-151">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="b4c04-152">Daher müssen die Typen nicht mit den Namespaces vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="b4c04-152">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 <span data-ttu-id="b4c04-153">[!code-vb[VbVbalrStatements&#153;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b4c04-153">[!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]</span></span>  
  
 <span data-ttu-id="b4c04-154">[!code-vb[VbVbalrStatements&#154;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b4c04-154">[!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4c04-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4c04-155">Example</span></span>  
 <span data-ttu-id="b4c04-156">Das folgende Beispiel schließt `Imports` -Anweisungen, die Aliase für den referenzierten Namespaces erstellen.</span><span class="sxs-lookup"><span data-stu-id="b4c04-156">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="b4c04-157">Die Typen werden mit den Aliasen qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="b4c04-157">The types are qualified with the aliases.</span></span>  
  
 <span data-ttu-id="b4c04-158">[!code-vb[VbVbalrStatements&#155;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="b4c04-158">[!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]</span></span>  
  
 <span data-ttu-id="b4c04-159">[!code-vb[VbVbalrStatements&#156;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="b4c04-159">[!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4c04-160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4c04-160">Example</span></span>  
 <span data-ttu-id="b4c04-161">Das folgende Beispiel schließt `Imports` -Anweisungen, die Aliase für den referenzierten Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b4c04-161">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="b4c04-162">Aliase werden verwendet, um die Typen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b4c04-162">Aliases are used to specify the types.</span></span>  
  
 <span data-ttu-id="b4c04-163">[!code-vb[VbVbalrStatements&#157;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="b4c04-163">[!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]</span></span>  
  
 <span data-ttu-id="b4c04-164">[!code-vb[VbVbalrStatements&#158;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="b4c04-164">[!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c04-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4c04-165">See Also</span></span>  
 <span data-ttu-id="b4c04-166">[Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b4c04-166">[Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) </span></span>  
<span data-ttu-id="b4c04-167"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="b4c04-167"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="b4c04-168"> [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b4c04-168"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="b4c04-169"> [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="b4c04-169"> [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="b4c04-170"> [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="b4c04-170"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>
