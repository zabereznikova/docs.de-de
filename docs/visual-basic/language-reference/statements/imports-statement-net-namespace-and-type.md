---
title: Imports-Anweisung - Namespace von .NET und Datentyp (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 4574bab62ca6d095ab66c17bf186da5f3d79bfb7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826521"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="f3933-102">Imports-Anweisung (.NET-Namespace und Typ)</span><span class="sxs-lookup"><span data-stu-id="f3933-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="f3933-103">Ermöglicht das Typnamen ohne namespacenennung verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="f3933-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3933-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3933-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="f3933-105">Teile</span><span class="sxs-lookup"><span data-stu-id="f3933-105">Parts</span></span>  
  
|<span data-ttu-id="f3933-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="f3933-106">Term</span></span>|<span data-ttu-id="f3933-107">Definition</span><span class="sxs-lookup"><span data-stu-id="f3933-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="f3933-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="f3933-108">Optional.</span></span> <span data-ttu-id="f3933-109">Ein *Importalias* oder Namen, die mit dem Code, um verweisen kann `namespace` anstelle der vollständigen Qualifizierungspfad.</span><span class="sxs-lookup"><span data-stu-id="f3933-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="f3933-110">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="f3933-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="f3933-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f3933-111">Required.</span></span> <span data-ttu-id="f3933-112">Der voll gekennzeichnete Name des Namespace importiert wird.</span><span class="sxs-lookup"><span data-stu-id="f3933-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="f3933-113">Eine Zeichenfolge von Namespaces kann zu allen Ebenen geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="f3933-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="f3933-114">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="f3933-114">Optional.</span></span> <span data-ttu-id="f3933-115">Der Namen eines Programmierelements, die in den Namespace deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="f3933-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="f3933-116">Alle Containerelement kann sein.</span><span class="sxs-lookup"><span data-stu-id="f3933-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3933-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f3933-117">Remarks</span></span>  
 <span data-ttu-id="f3933-118">Die `Imports` Anweisung aktiviert die Typen, die in einem angegebenen Namespace nicht direkt verwiesen werden, enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f3933-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="f3933-119">Sie können einen einzelnen Namespace-Namen oder eine Zeichenfolge von geschachtelten Namespaces angeben.</span><span class="sxs-lookup"><span data-stu-id="f3933-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="f3933-120">Jeden geschachtelten Namespace ist aus dem nächsten höheren Ebene Namespace durch einen Punkt getrennt (`.`), wie im folgende Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f3933-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="f3933-121">Jede Quelldatei kann eine beliebige Anzahl von enthalten `Imports` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="f3933-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="f3933-122">Diese müssen führen Sie die Option-Deklarationen, z. B. die `Option Strict` -Anweisung, und sie müssen vor stehen Deklarationen von Programmierelementen, z. B. `Module` oder `Class` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="f3933-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="f3933-123">Sie können `Imports` nur auf Dateiebene.</span><span class="sxs-lookup"><span data-stu-id="f3933-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="f3933-124">Dies bedeutet, dass der Deklarationskontext für den Import von muss eine Quelldatei und Namespace, Klasse, Struktur, Modul, Schnittstelle, Prozedur oder Block nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="f3933-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="f3933-125">Beachten Sie, dass die `Imports` Anweisung macht nicht Elemente aus anderen Projekten und Assemblys für Ihr Projekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f3933-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="f3933-126">Importieren von nimmt nicht an die Stelle der Festlegen eines Verweises.</span><span class="sxs-lookup"><span data-stu-id="f3933-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="f3933-127">Es wird lediglich entfernt die Notwendigkeit, qualifizieren Sie Namen, die bereits für Ihr Projekt verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f3933-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="f3933-128">Weitere Informationen finden Sie unter "Importieren von enthaltenen Elementen" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="f3933-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3933-129">Sie können implizite definieren `Imports` Anweisungen durch Verwenden der [Seite "Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f3933-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="f3933-130">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen oder Entfernen von importierten Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f3933-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="f3933-131">Importaliase</span><span class="sxs-lookup"><span data-stu-id="f3933-131">Import Aliases</span></span>  
 <span data-ttu-id="f3933-132">Ein *Importalias* definiert den Alias für einen Namespace oder Typ.</span><span class="sxs-lookup"><span data-stu-id="f3933-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="f3933-133">Importaliase sind nützlich, wenn Sie Elemente verwenden, mit dem gleichen Namen, die in einem oder mehreren Namespaces deklariert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f3933-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="f3933-134">Weitere Informationen und ein Beispiel finden Sie unter "Qualifizieren eines Elementnamens" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="f3933-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="f3933-135">Deklarieren Sie nicht Mitglied auf Modulebene mit dem gleichen Namen wie `aliasname`.</span><span class="sxs-lookup"><span data-stu-id="f3933-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="f3933-136">Visual Basic-Compiler wird verwendet, wenn Sie dies tun, `aliasname` nur für den deklarierten Member und nicht mehr als ein Importalias erkannt.</span><span class="sxs-lookup"><span data-stu-id="f3933-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="f3933-137">Obwohl die Syntax für einen Importalias deklarieren, zum Importieren einer XML-Namespacepräfix verwendet wird, unterscheiden sich die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="f3933-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="f3933-138">Ein Importalias kann als ein Ausdruck in Ihrem Code verwendet werden, während ein XML-Namespacepräfix in XML-Literalen oder XML-Achseneigenschaften nur als Präfix für ein qualifiziertes Element oder Attributname verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f3933-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="f3933-139">Elementnamen</span><span class="sxs-lookup"><span data-stu-id="f3933-139">Element Names</span></span>  
 <span data-ttu-id="f3933-140">Wenn Sie angeben `element`, muss darstellen einer *Containerelement*, d. h. ein Programmierelement, das andere Elemente enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="f3933-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="f3933-141">Container-Elemente enthalten Klassen, Strukturen, Module, Schnittstellen und Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="f3933-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="f3933-142">Der Bereich der Elemente zur Verfügung gestellt wurden ein `Imports` Anweisung hängt davon ab, ob Sie angeben `element`.</span><span class="sxs-lookup"><span data-stu-id="f3933-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="f3933-143">Wenn Sie nur angeben `namespace`, alle eindeutig benannte Member dieses Namespace und Mitglieder der Container-Elemente innerhalb dieses Namespace sind ohne Qualifizierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f3933-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="f3933-144">Wenn Sie beide angeben `namespace` und `element`, nur die Elemente des Elements ohne Qualifizierung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f3933-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3933-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f3933-145">Example</span></span>  
 <span data-ttu-id="f3933-146">Das folgende Beispiel gibt alle Ordner im Verzeichnis C:\ mit der <xref:System.IO.DirectoryInfo> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f3933-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="f3933-147">Der Code weist keine `Imports` Anweisungen am Anfang der Datei.</span><span class="sxs-lookup"><span data-stu-id="f3933-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="f3933-148">Aus diesem Grund die `DirectoryInfo`, <xref:System.Text.StringBuilder>, und <xref:Microsoft.VisualBasic.ControlChars.CrLf> Verweise mit den Namespaces alle vollständig qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="f3933-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a><span data-ttu-id="f3933-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f3933-149">Example</span></span>  
 <span data-ttu-id="f3933-150">Das folgende Beispiel schließt `Imports` Anweisungen für die Namespaces auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f3933-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="f3933-151">Aus diesem Grund müssen die Typen nicht mit den Namespaces vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="f3933-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a><span data-ttu-id="f3933-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f3933-152">Example</span></span>  
 <span data-ttu-id="f3933-153">Das folgende Beispiel schließt `Imports` -Anweisungen, die Aliase für den referenzierten Namespace zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f3933-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="f3933-154">Die Typen werden mit den Aliasen qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="f3933-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a><span data-ttu-id="f3933-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f3933-155">Example</span></span>  
 <span data-ttu-id="f3933-156">Das folgende Beispiel schließt `Imports` -Anweisungen, die Aliase für den referenzierten Typen erstellen.</span><span class="sxs-lookup"><span data-stu-id="f3933-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="f3933-157">Aliase werden verwendet, um die Typen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f3933-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a><span data-ttu-id="f3933-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3933-158">See also</span></span>

- [<span data-ttu-id="f3933-159">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f3933-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="f3933-160">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3933-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="f3933-161">Verweise und die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f3933-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="f3933-162">Imports-Anweisung (XML-Namespace)</span><span class="sxs-lookup"><span data-stu-id="f3933-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="f3933-163">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="f3933-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
