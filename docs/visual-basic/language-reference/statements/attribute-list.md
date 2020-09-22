---
title: Attributliste
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: e566239c56efa8ca8e83bff92486fec4c434e92b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874735"
---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="5c2e0-102">Attributliste (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c2e0-102">Attribute List (Visual Basic)</span></span>

<span data-ttu-id="5c2e0-103">Gibt die Attribute an, die auf ein deklariertes Programmier Element angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="5c2e0-104">Mehrere Attribute werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="5c2e0-105">Im folgenden finden Sie die Syntax für ein Attribut.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c2e0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c2e0-106">Syntax</span></span>  
  
```vb  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="5c2e0-107">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="5c2e0-107">Parts</span></span>  

|||
|---|---|
|`attributemodifier`|<span data-ttu-id="5c2e0-108">Erforderlich für Attribute, die am Anfang einer Quelldatei angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="5c2e0-109">Kann eine [Assembly](../modifiers/assembly.md) oder ein [Modul](../modifiers/module-keyword.md)sein.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-109">Can be [Assembly](../modifiers/assembly.md) or [Module](../modifiers/module-keyword.md).</span></span>|
|`attributename`| <span data-ttu-id="5c2e0-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-110">Required.</span></span> <span data-ttu-id="5c2e0-111">Der Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-111">Name of the attribute.</span></span>|
|`attributearguments`|<span data-ttu-id="5c2e0-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-112">Optional.</span></span> <span data-ttu-id="5c2e0-113">Liste der positionellen Argumente für dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="5c2e0-114">Mehrere Argumente werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-114">Multiple arguments are separated by commas.</span></span>|
|`attributeinitializer`|<span data-ttu-id="5c2e0-115">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-115">Optional.</span></span> <span data-ttu-id="5c2e0-116">Liste der Variablen-oder Eigenschafteninitialisierer für dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="5c2e0-117">Mehrere Initialisierer werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-117">Multiple initializers are separated by commas.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="5c2e0-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5c2e0-118">Remarks</span></span>  

 <span data-ttu-id="5c2e0-119">Sie können ein oder mehrere Attribute auf fast alle Programmier Elemente anwenden (Typen, Prozeduren, Eigenschaften usw.).</span><span class="sxs-lookup"><span data-stu-id="5c2e0-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="5c2e0-120">Attribute werden in den Metadaten der Assembly angezeigt, und Sie können Ihnen helfen, Ihren Code zu kommentieren oder anzugeben, wie ein bestimmtes Programmier Element verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="5c2e0-121">Sie können Attribute anwenden, die durch Visual Basic und die .NET Framework definiert sind, und Sie können eigene Attribute definieren.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="5c2e0-122">Weitere Informationen dazu, wann Attribute verwendet werden sollten, finden Sie unter [Übersicht über Attribute](../../programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="5c2e0-122">For more information on when to use attributes, see [Attributes overview](../../programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="5c2e0-123">Weitere Informationen zu Attributnamen finden Sie unter [deklarierte Element Namen](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="5c2e0-123">For information on attribute names, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="5c2e0-124">Regeln</span><span class="sxs-lookup"><span data-stu-id="5c2e0-124">Rules</span></span>  
  
- <span data-ttu-id="5c2e0-125">**Praktika.**</span><span class="sxs-lookup"><span data-stu-id="5c2e0-125">**Placement.**</span></span> <span data-ttu-id="5c2e0-126">Sie können Attribute auf die meisten deklarierten Programmier Elemente anwenden.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="5c2e0-127">Zum Anwenden eines oder mehrerer Attribute platzieren Sie einen *Attribut Block* am Anfang der Element Deklaration.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="5c2e0-128">Jeder Eintrag in der Attribut Liste gibt ein Attribut an, das Sie anwenden möchten, sowie den Modifizierer und die Argumente, die Sie für diesen Aufruf des Attributs verwenden.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
- <span data-ttu-id="5c2e0-129">**Spitze Klammern.**</span><span class="sxs-lookup"><span data-stu-id="5c2e0-129">**Angle Brackets.**</span></span> <span data-ttu-id="5c2e0-130">Wenn Sie eine Attribut Liste angeben, müssen Sie Sie in spitzen Klammern (" `<` " und " `>` ") einschließen.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
- <span data-ttu-id="5c2e0-131">**Teil der Deklaration.**</span><span class="sxs-lookup"><span data-stu-id="5c2e0-131">**Part of the Declaration.**</span></span> <span data-ttu-id="5c2e0-132">Das Attribut muss Teil der Element Deklaration und keine separate Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="5c2e0-133">Sie können die Zeilen Fortsetzungs Sequenz (" `_` ") verwenden, um die Deklarations Anweisung auf mehrere Quell Codezeilen zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
- <span data-ttu-id="5c2e0-134">**Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="5c2e0-134">**Modifiers.**</span></span> <span data-ttu-id="5c2e0-135">Ein Attributmodifizierer ( `Assembly` oder `Module` ) ist für jedes Attribut erforderlich, das auf ein Programmier Element am Anfang einer Quelldatei angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="5c2e0-136">Attributmodifiziererer sind für Attribute, die auf Elemente angewendet werden, die sich nicht am Anfang einer Quelldatei befinden, nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
- <span data-ttu-id="5c2e0-137">**Argumentation.**</span><span class="sxs-lookup"><span data-stu-id="5c2e0-137">**Arguments.**</span></span> <span data-ttu-id="5c2e0-138">Alle positionellen Argumente für ein Attribut müssen allen Variablen-oder eigenschafteninitialisierern vorangestellt sein.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c2e0-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c2e0-139">Example</span></span>  

 <span data-ttu-id="5c2e0-140">Im folgenden Beispiel wird das- <xref:System.Runtime.InteropServices.DllImportAttribute> Attribut auf eine Skeleton-Definition einer- `Function` Prozedur angewendet.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]  
  
 <span data-ttu-id="5c2e0-141"><xref:System.Runtime.InteropServices.DllImportAttribute> Gibt an, dass die attributierte Prozedur einen Einstiegspunkt in einer nicht verwalteten DLL (Dynamic-Link Library) darstellt.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-141"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="5c2e0-142">Das Attribut stellt den DLL-Namen als Positions Argument und die anderen Informationen als Variableninitialisierer bereit.</span><span class="sxs-lookup"><span data-stu-id="5c2e0-142">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c2e0-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c2e0-143">See also</span></span>

- [<span data-ttu-id="5c2e0-144">Assembly</span><span class="sxs-lookup"><span data-stu-id="5c2e0-144">Assembly</span></span>](../modifiers/assembly.md)
- [<span data-ttu-id="5c2e0-145">Mond \<keyword></span><span class="sxs-lookup"><span data-stu-id="5c2e0-145">Module \<keyword></span></span>](../modifiers/module-keyword.md)
- [<span data-ttu-id="5c2e0-146">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="5c2e0-146">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="5c2e0-147">Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code</span><span class="sxs-lookup"><span data-stu-id="5c2e0-147">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
