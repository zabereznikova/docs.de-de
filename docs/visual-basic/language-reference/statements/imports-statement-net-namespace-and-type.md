---
title: Imports-Anweisung-.NET-Namespace und-Typ (Visual Basic)
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
ms.openlocfilehash: a0b7a6a5fd16dc0daa620e6b490ddfdeb0e7c80e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912390"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="417f5-102">Imports-Anweisung (.NET-Namespace und Typ)</span><span class="sxs-lookup"><span data-stu-id="417f5-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="417f5-103">Ermöglicht, dass Typnamen ohne Namespace Qualifikation referenziert werden.</span><span class="sxs-lookup"><span data-stu-id="417f5-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="417f5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="417f5-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="417f5-105">Teile</span><span class="sxs-lookup"><span data-stu-id="417f5-105">Parts</span></span>  
  
|<span data-ttu-id="417f5-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="417f5-106">Term</span></span>|<span data-ttu-id="417f5-107">Definition</span><span class="sxs-lookup"><span data-stu-id="417f5-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="417f5-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="417f5-108">Optional.</span></span> <span data-ttu-id="417f5-109">Ein *importieralias* oder-Name, auf `namespace` den Code anstelle der vollständigen Qualifikations Zeichenfolge verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="417f5-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="417f5-110">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="417f5-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="417f5-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="417f5-111">Required.</span></span> <span data-ttu-id="417f5-112">Der voll qualifizierte Name des zu importierenden Namespace.</span><span class="sxs-lookup"><span data-stu-id="417f5-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="417f5-113">Kann eine Zeichenfolge von Namespaces sein, die auf eine beliebige Ebene eingebettet ist.</span><span class="sxs-lookup"><span data-stu-id="417f5-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="417f5-114">Optional.</span><span class="sxs-lookup"><span data-stu-id="417f5-114">Optional.</span></span> <span data-ttu-id="417f5-115">Der Name eines Programmier Elements, das im-Namespace deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="417f5-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="417f5-116">Kann ein beliebiges Containerelement sein.</span><span class="sxs-lookup"><span data-stu-id="417f5-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="417f5-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="417f5-117">Remarks</span></span>  
 <span data-ttu-id="417f5-118">Die `Imports` -Anweisung ermöglicht, dass in einem bestimmten Namespace enthaltene Typen direkt referenziert werden.</span><span class="sxs-lookup"><span data-stu-id="417f5-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="417f5-119">Sie können einen einzelnen Namespace Namen oder eine Zeichenfolge von schsted Namespaces angeben.</span><span class="sxs-lookup"><span data-stu-id="417f5-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="417f5-120">Jeder untergeordnete Namespace wird von dem nächsthöheren Namespace der höheren Ebene um einen Zeitraum`.`() getrennt, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="417f5-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="417f5-121">Jede Quelldatei kann eine beliebige Anzahl von `Imports` -Anweisungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="417f5-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="417f5-122">Diese müssen allen Options Deklarationen folgen, wie z `Option Strict` . b. der-Anweisung, und Sie müssen vor allen Deklarationen `Module` von `Class` Programmier Elementen wie-oder-Anweisungen stehen.</span><span class="sxs-lookup"><span data-stu-id="417f5-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="417f5-123">Sie können nur `Imports` auf Dateiebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="417f5-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="417f5-124">Dies bedeutet, dass der Deklarations Kontext für Importe eine Quelldatei sein muss und kein Namespace, keine Klasse, keine Struktur, kein Modul, keine Schnittstelle, keine Prozedur oder kein Block sein kann.</span><span class="sxs-lookup"><span data-stu-id="417f5-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="417f5-125">Beachten Sie, `Imports` dass die-Anweisung keine Elemente aus anderen Projekten und Assemblys für Ihr Projekt verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="417f5-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="417f5-126">Beim Importieren wird kein Verweis festgelegt.</span><span class="sxs-lookup"><span data-stu-id="417f5-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="417f5-127">Es entfällt nur die Notwendigkeit, Namen zu qualifizieren, die bereits für Ihr Projekt verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="417f5-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="417f5-128">Weitere Informationen finden Sie unter "Importieren enthaltender Elemente" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="417f5-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="417f5-129">Sie können implizite `Imports` Anweisungen mithilfe der Seite " [Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)definieren.</span><span class="sxs-lookup"><span data-stu-id="417f5-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="417f5-130">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen oder entfernen importierter Namespaces (](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="417f5-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="417f5-131">Importaliase</span><span class="sxs-lookup"><span data-stu-id="417f5-131">Import Aliases</span></span>  
 <span data-ttu-id="417f5-132">Ein *importieralias* definiert den Alias für einen Namespace oder Typ.</span><span class="sxs-lookup"><span data-stu-id="417f5-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="417f5-133">Import Aliase sind nützlich, wenn Sie Elemente mit demselben Namen verwenden müssen, die in einem oder mehreren Namespaces deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="417f5-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="417f5-134">Weitere Informationen und ein Beispiel finden Sie unter "qualifizieren eines Element namens" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="417f5-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="417f5-135">Sie sollten keinen Member auf Modulebene mit dem gleichen Namen wie `aliasname`angeben.</span><span class="sxs-lookup"><span data-stu-id="417f5-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="417f5-136">Wenn Sie dies tun, verwendet `aliasname` der Visual Basic-Compiler nur für den deklarierten Member und erkennt ihn nicht mehr als importieralias.</span><span class="sxs-lookup"><span data-stu-id="417f5-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="417f5-137">Obwohl die Syntax, die zum Deklarieren eines importierungsalias verwendet wird, wie zum Importieren eines XML-Namespace Präfixes verwendet wird, unterscheiden sich die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="417f5-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="417f5-138">Ein importieralias kann als Ausdruck in Ihrem Code verwendet werden, wohingegen ein XML-Namespace Präfix nur in XML-Literalen oder XML-Achsen Eigenschaften als Präfix für einen qualifizierten Element-oder Attributnamen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="417f5-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="417f5-139">Elementnamen</span><span class="sxs-lookup"><span data-stu-id="417f5-139">Element Names</span></span>  
 <span data-ttu-id="417f5-140">Wenn Sie angeben `element`, muss es ein *Containerelement*, d. h. ein Programmier Element, das andere Elemente enthalten kann, darstellen.</span><span class="sxs-lookup"><span data-stu-id="417f5-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="417f5-141">Container Elemente enthalten Klassen, Strukturen, Module, Schnittstellen und Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="417f5-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="417f5-142">Der Bereich der Elemente, die von einer `Imports` -Anweisung zur Verfügung gestellt werden, hängt davon ab, ob Sie angeben. `element`</span><span class="sxs-lookup"><span data-stu-id="417f5-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="417f5-143">Wenn Sie nur `namespace`angeben, sind alle eindeutig benannten Member dieses Namespace und Member von Container Elementen in diesem Namespace ohne Qualifizierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="417f5-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="417f5-144">Wenn Sie sowohl `namespace` als auch `element`angeben, sind nur die Member dieses Elements ohne Qualifizierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="417f5-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="417f5-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="417f5-145">Example</span></span>  
 <span data-ttu-id="417f5-146">Im folgenden Beispiel werden alle Ordner in "C:\" zurückgegeben. Verzeichnis mithilfe der <xref:System.IO.DirectoryInfo> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="417f5-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="417f5-147">Der Code enthält keine `Imports` -Anweisungen am Anfang der Datei.</span><span class="sxs-lookup"><span data-stu-id="417f5-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="417f5-148">Daher sind die `DirectoryInfo`Verweise <xref:System.Text.StringBuilder>, und <xref:Microsoft.VisualBasic.ControlChars.CrLf> vollständig mit den Namespaces qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="417f5-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a><span data-ttu-id="417f5-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="417f5-149">Example</span></span>  
 <span data-ttu-id="417f5-150">Das folgende Beispiel enthält `Imports` Anweisungen für die Namespaces, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="417f5-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="417f5-151">Daher müssen die Typen nicht vollständig mit den Namespaces qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="417f5-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a><span data-ttu-id="417f5-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="417f5-152">Example</span></span>  
 <span data-ttu-id="417f5-153">Das folgende Beispiel enthält `Imports` Anweisungen, die Aliase für die Namespaces erstellen, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="417f5-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="417f5-154">Die Typen werden mit den Aliasen qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="417f5-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a><span data-ttu-id="417f5-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="417f5-155">Example</span></span>  
 <span data-ttu-id="417f5-156">Das folgende Beispiel enthält `Imports` Anweisungen, die Aliase für die Typen erstellen, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="417f5-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="417f5-157">Aliase werden verwendet, um die Typen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="417f5-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a><span data-ttu-id="417f5-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="417f5-158">See also</span></span>

- [<span data-ttu-id="417f5-159">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="417f5-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="417f5-160">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="417f5-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="417f5-161">Verweise und die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="417f5-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="417f5-162">Imports-Anweisung (XML-Namespace)</span><span class="sxs-lookup"><span data-stu-id="417f5-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="417f5-163">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="417f5-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
