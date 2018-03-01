---
title: Namespaces in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.global
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names [Visual Basic], avoiding conflicts
- naming conflicts [Visual Basic], namespaces
- namespaces [Visual Basic], assemblies
- Visual Basic code, namespaces
- fully qualified names [Visual Basic]
- naming conventions [Visual Basic], naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c18d0a9abb1d8b9e3e22f3b81bf605fb8ed75cfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="namespaces-in-visual-basic"></a><span data-ttu-id="0e347-102">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0e347-102">Namespaces in Visual Basic</span></span>
<span data-ttu-id="0e347-103">Namespaces organisieren die in einer Assembly definierten Objekte.</span><span class="sxs-lookup"><span data-stu-id="0e347-103">Namespaces organize the objects defined in an assembly.</span></span> <span data-ttu-id="0e347-104">Assemblys können mehrere Namespaces enthalten, die wiederum andere Namespaces enthalten können.</span><span class="sxs-lookup"><span data-stu-id="0e347-104">Assemblies can contain multiple namespaces, which can in turn contain other namespaces.</span></span> <span data-ttu-id="0e347-105">Namespaces vermeiden Mehrdeutigkeit und vereinfachen Verweise, wenn Sie große Gruppen von Objekten verwenden, zum Beispiel Klassenbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="0e347-105">Namespaces prevent ambiguity and simplify references when using large groups of objects such as class libraries.</span></span>  
  
 <span data-ttu-id="0e347-106">Zum Beispiel definiert [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] die <xref:System.Windows.Forms.ListBox>-Klasse im <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="0e347-106">For example, the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] defines the <xref:System.Windows.Forms.ListBox> class in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="0e347-107">Das folgende Codefragment zeigt, wie eine Variable mit dem vollqualifizierten Namen für diese Klasse deklariert wird:</span><span class="sxs-lookup"><span data-stu-id="0e347-107">The following code fragment shows how to declare a variable using the fully qualified name for this class:</span></span>  
  
 [!code-vb[VbVbalrApplication#6](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_1.vb)]  
  
## <a name="avoiding-name-collisions"></a><span data-ttu-id="0e347-108">Vermeiden von Namenskonflikten</span><span class="sxs-lookup"><span data-stu-id="0e347-108">Avoiding Name Collisions</span></span>  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]<span data-ttu-id="0e347-109"> -Namespaces beheben ein Problem, das manchmal als *Namespacekonflikte*bezeichnet wird. Dabei wird die Entwicklung einer Klassenbibliothek durch die Verwendung ähnlicher Namen in einer anderen Bibliothek beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="0e347-109"> namespaces address a problem sometimes called *namespace pollution*, in which the developer of a class library is hampered by the use of similar names in another library.</span></span> <span data-ttu-id="0e347-110">Diese Konflikte mit vorhandenen Komponenten werden auch als *Namenskonflikte*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0e347-110">These conflicts with existing components are sometimes called *name collisions*.</span></span>  
  
 <span data-ttu-id="0e347-111">Angenommen, Sie erstellen eine neue Klasse namens `ListBox`, können Sie sie innerhalb des Projekts ohne Qualifikation verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e347-111">For example, if you create a new class named `ListBox`, you can use it inside your project without qualification.</span></span> <span data-ttu-id="0e347-112">Sollten Sie jedoch die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.Windows.Forms.ListBox> -Klasse im gleichen Projekt verwenden, müssen Sie einen vollqualifizierten Verweis verwenden, um den Verweis eindeutig zu machen.</span><span class="sxs-lookup"><span data-stu-id="0e347-112">However, if you want to use the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.Windows.Forms.ListBox> class in the same project, you must use a fully qualified reference to make the reference unique.</span></span> <span data-ttu-id="0e347-113">Wenn der Verweis nicht eindeutig ist, meldet [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] einen Fehler, dass der Name mehrdeutig ist.</span><span class="sxs-lookup"><span data-stu-id="0e347-113">If the reference is not unique, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] produces an error stating that the name is ambiguous.</span></span> <span data-ttu-id="0e347-114">Im folgenden Codebeispiel wird die Deklaration dieser Objekte veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="0e347-114">The following code example demonstrates how to declare these objects:</span></span>  
  
 [!code-vb[VbVbalrApplication#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_2.vb)]  
  
 <span data-ttu-id="0e347-115">Die folgende Abbildung zeigt zwei Namespacehierarchien, beide mit einem Objekt mit dem Namen `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="0e347-115">The following illustration shows two namespace hierarchies, both containing an object named `ListBox`.</span></span>  
  
 <span data-ttu-id="0e347-116">![Namespace-Hierarchie](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.gif "VaNamespaceHierarchy")</span><span class="sxs-lookup"><span data-stu-id="0e347-116">![Namespace Hierarchy](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.gif "vaNamespaceHierarchy")</span></span>  
  
 <span data-ttu-id="0e347-117">Standardmäßig enthält jede mit [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] erstellte ausführbare Datei einen Namespace mit demselben Namen wie für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="0e347-117">By default, every executable file you create with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] contains a namespace with the same name as your project.</span></span> <span data-ttu-id="0e347-118">Wenn Sie zum Beispiel ein Objekt in einem Projekt mit dem Namen `ListBoxProject`definieren, enthält die ausführbare Datei ListBoxProject.exe einen Namespace mit dem Namen `ListBoxProject`.</span><span class="sxs-lookup"><span data-stu-id="0e347-118">For example, if you define an object within a project named `ListBoxProject`, the executable file ListBoxProject.exe contains a namespace called `ListBoxProject`.</span></span>  
  
 <span data-ttu-id="0e347-119">Mehrere Assemblys können den gleichen Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e347-119">Multiple assemblies can use the same namespace.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="0e347-120"> behandelt sie als einen einzigen Satz von Namen.</span><span class="sxs-lookup"><span data-stu-id="0e347-120"> treats them as a single set of names.</span></span> <span data-ttu-id="0e347-121">Zum Beispiel können Sie Klassen für einen Namespace mit dem Namen `SomeNameSpace` in einer Assembly mit dem Namen `Assemb1`definieren, und zusätzliche Klassen für den gleichen Namespace in einer Assembly mit dem Namen `Assemb2`.</span><span class="sxs-lookup"><span data-stu-id="0e347-121">For example, you can define classes for a namespace called `SomeNameSpace` in an assembly named `Assemb1`, and define additional classes for the same namespace from an assembly named `Assemb2`.</span></span>  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="0e347-122">Vollqualifizierte Namen</span><span class="sxs-lookup"><span data-stu-id="0e347-122">Fully Qualified Names</span></span>  
 <span data-ttu-id="0e347-123">Vollqualifizierte Namen sind Objektverweise, denen der Name des Namespace vorangestellt ist, in dem das Objekt definiert ist.</span><span class="sxs-lookup"><span data-stu-id="0e347-123">Fully qualified names are object references that are prefixed with the name of the namespace in which the object is defined.</span></span> <span data-ttu-id="0e347-124">Sie können in anderen Projekten definierte Objekte verwenden, wenn Sie einen Verweis auf die Klasse erstellen (durch Auswahl von **Verweis hinzufügen** aus dem Menü **Projekt** ) und dann den vollqualifizierten Namen für das Objekt im Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e347-124">You can use objects defined in other projects if you create a reference to the class (by choosing **Add Reference** from the **Project** menu) and then use the fully qualified name for the object in your code.</span></span> <span data-ttu-id="0e347-125">Das folgende Codefragment zeigt, wie Sie den vollqualifizierten Namen für ein Objekt aus dem Namespace eines anderen Projekts verwenden:</span><span class="sxs-lookup"><span data-stu-id="0e347-125">The following code fragment shows how to use the fully qualified name for an object from another project's namespace:</span></span>  
  
 [!code-vb[VbVbalrApplication#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_3.vb)]  
  
 <span data-ttu-id="0e347-126">Durch vollqualifizierte Namen werden Namenskonflikte vermieden, da der Compiler feststellen kann, welches Objekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e347-126">Fully qualified names prevent naming conflicts because they make it possible for the compiler to determine which object is being used.</span></span> <span data-ttu-id="0e347-127">Die Namen selbst können jedoch lang und umständlich sein.</span><span class="sxs-lookup"><span data-stu-id="0e347-127">However, the names themselves can get long and cumbersome.</span></span> <span data-ttu-id="0e347-128">Um dies zu umgehen, können Sie die `Imports` -Anweisung für die Definition eines *Alias*verwenden. Diesen abgekürzten Namen können Sie anstelle eines vollqualifizierten Namens verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e347-128">To get around this, you can use the `Imports` statement to define an *alias*—an abbreviated name you can use in place of a fully qualified name.</span></span> <span data-ttu-id="0e347-129">Das folgende Codebeispiel erstellt Aliase für zwei vollqualifizierte Namen und verwendet diese Aliase zur Definition zweier Objekte.</span><span class="sxs-lookup"><span data-stu-id="0e347-129">For example, the following code example creates aliases for two fully qualified names, and uses these aliases to define two objects.</span></span>  
  
 [!code-vb[VbVbalrApplication#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_4.vb)]  
  
 [!code-vb[VbVbalrApplication#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_5.vb)]  
  
 <span data-ttu-id="0e347-130">Wenn Sie die `Imports` -Anweisung ohne Alias verwenden, können Sie alle Namen in diesem Namespace ohne Qualifikation verwenden – vorausgesetzt, sie sind in dem Projekt eindeutig.</span><span class="sxs-lookup"><span data-stu-id="0e347-130">If you use the `Imports` statement without an alias, you can use all the names in that namespace without qualification, provided they are unique to the project.</span></span> <span data-ttu-id="0e347-131">Wenn das Projekt `Imports` -Anweisungen für Namespaces enthält, die Elemente mit gleichem Namen enthalten, müssen Sie Namen, die Sie verwenden, vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="0e347-131">If your project contains `Imports` statements for namespaces that contain items with the same name, you must fully qualify that name when you use it.</span></span> <span data-ttu-id="0e347-132">Nehmen wir an, das Projekt enthält die folgenden beiden `Imports` -Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="0e347-132">Suppose, for example, your project contained the following two `Imports` statements:</span></span>  
  
 [!code-vb[VbVbalrApplication#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_6.vb)]  
  
 <span data-ttu-id="0e347-133">Wenn Sie versuchen, `Class1` zu verwenden ohne diesen Namen voll zu qualifizieren, meldet [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] einen Fehler, dass der Name `Class1` mehrdeutig ist.</span><span class="sxs-lookup"><span data-stu-id="0e347-133">If you attempt to use `Class1` without fully qualifying it, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] produces an error stating that the name `Class1` is ambiguous.</span></span>  
  
## <a name="namespace-level-statements"></a><span data-ttu-id="0e347-134">Namespaceebenen-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="0e347-134">Namespace Level Statements</span></span>  
 <span data-ttu-id="0e347-135">Innerhalb eines Namespace können Sie Elemente wie Module, Schnittstellen, Klassen, Delegaten, Enumerationen, Strukturen und andere Namespaces definieren.</span><span class="sxs-lookup"><span data-stu-id="0e347-135">Within a namespace, you can define items such as modules, interfaces, classes, delegates, enumerations, structures, and other namespaces.</span></span> <span data-ttu-id="0e347-136">Sie können keine Elemente wie Eigenschaften, Prozeduren, Variablen und Ereignisse auf Namespaceebene definieren.</span><span class="sxs-lookup"><span data-stu-id="0e347-136">You cannot define items such as properties, procedures, variables and events at the namespace level.</span></span> <span data-ttu-id="0e347-137">Diese Elemente müssen in Containern, beispielsweise in Modulen, Strukturen oder Klassen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="0e347-137">These items must be declared within containers such as modules, structures, or classes.</span></span>  
  
## <a name="global-keyword-in-fully-qualified-names"></a><span data-ttu-id="0e347-138">Das Schlüsselwort „global“ in vollqualifizierten Namen</span><span class="sxs-lookup"><span data-stu-id="0e347-138">Global Keyword in Fully Qualified Names</span></span>  
 <span data-ttu-id="0e347-139">Wenn Sie eine geschachtelte Hierarchie aus Namespaces definiert haben, kann der Zugriff auf den <xref:System?displayProperty=nameWithType>-Namespace von .NET Framework für Code innerhalb dieser Hierarchie blockiert sein.</span><span class="sxs-lookup"><span data-stu-id="0e347-139">If you have defined a nested hierarchy of namespaces, code inside that hierarchy might be blocked from accessing the <xref:System?displayProperty=nameWithType> namespace of the .NET Framework.</span></span> <span data-ttu-id="0e347-140">Das folgende Beispiel veranschaulicht eine Hierarchie, in der der `SpecialSpace.System`-Namespace den Zugriff auf <xref:System?displayProperty=nameWithType> blockiert.</span><span class="sxs-lookup"><span data-stu-id="0e347-140">The following example illustrates a hierarchy in which the `SpecialSpace.System` namespace blocks access to <xref:System?displayProperty=nameWithType>.</span></span>  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As System.Int32  
                Dim n As System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 <span data-ttu-id="0e347-141">Der Visual Basic-Compiler kann daher den Verweis auf <xref:System.Int32?displayProperty=nameWithType> nicht auflösen, da `SpecialSpace.System` kein `Int32` definiert.</span><span class="sxs-lookup"><span data-stu-id="0e347-141">As a result, the Visual Basic compiler cannot successfully resolve the reference to <xref:System.Int32?displayProperty=nameWithType>, because `SpecialSpace.System` does not define `Int32`.</span></span> <span data-ttu-id="0e347-142">Sie können das Schlüsselwort `Global` verwenden, um die Qualifikationskette in der äußersten Ebene der .NET Framework-Klassenbibliothek zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="0e347-142">You can use the `Global` keyword to start the qualification chain at the outermost level of the .NET Framework class library.</span></span> <span data-ttu-id="0e347-143">Dadurch können Sie den <xref:System?displayProperty=nameWithType>-Namespace oder irgendeinen anderen Namespace in der Klassenbibliothek angeben.</span><span class="sxs-lookup"><span data-stu-id="0e347-143">This allows you to specify the <xref:System?displayProperty=nameWithType> namespace or any other namespace in the class library.</span></span> <span data-ttu-id="0e347-144">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0e347-144">The following example illustrates this.</span></span>  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As Global.System.Int32  
                Dim n As Global.System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 <span data-ttu-id="0e347-145">Sie können `Global` verwenden, um auf andere Namespaces auf Stammebene zuzugreifen, beispielsweise auf <xref:Microsoft.VisualBasic?displayProperty=nameWithType>, und auf jeden anderen Namespace, der dem Projekt zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0e347-145">You can use `Global` to access other root-level namespaces, such as <xref:Microsoft.VisualBasic?displayProperty=nameWithType>, and any namespace associated with your project.</span></span>  
  
## <a name="global-keyword-in-namespace-statements"></a><span data-ttu-id="0e347-146">Global-Schlüsselwort in Namespace-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="0e347-146">Global Keyword in Namespace Statements</span></span>  
 <span data-ttu-id="0e347-147">Sie können auch das Schlüsselwort `Global` in einem [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md)bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0e347-147">You can also use the `Global` keyword in a [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md).</span></span> <span data-ttu-id="0e347-148">Dadurch können Sie einen Namespace aus dem Stammnamespace des Projekts definieren.</span><span class="sxs-lookup"><span data-stu-id="0e347-148">This lets you define a namespace out of the root namespace of your project.</span></span>  
  
 <span data-ttu-id="0e347-149">Alle Namespaces im Projekt basieren auf dem Stammnamespace des Projekts.</span><span class="sxs-lookup"><span data-stu-id="0e347-149">All namespaces in your project are based on the root namespace for the project.</span></span>  <span data-ttu-id="0e347-150">Visual Studio weist den Projektnamen als den Standard-Stammnamespace für den gesamten Code des Projekts zu.</span><span class="sxs-lookup"><span data-stu-id="0e347-150">Visual Studio assigns your project name as the default root namespace for all code in your project.</span></span> <span data-ttu-id="0e347-151">Wenn Ihr Projekt beispielsweise den Namen `ConsoleApplication1`hat, gehören die Programmierelemente zum Namespace `ConsoleApplication1`.</span><span class="sxs-lookup"><span data-stu-id="0e347-151">For example, if your project is named `ConsoleApplication1`, its programming elements belong to namespace `ConsoleApplication1`.</span></span> <span data-ttu-id="0e347-152">Wenn Sie `Namespace Magnetosphere`deklarieren, greifen Verweise auf `Magnetosphere` im Projekt auf `ConsoleApplication1.Magnetosphere`zu.</span><span class="sxs-lookup"><span data-stu-id="0e347-152">If you declare `Namespace Magnetosphere`, references to `Magnetosphere` in the project will access `ConsoleApplication1.Magnetosphere`.</span></span>  
  
 <span data-ttu-id="0e347-153">Die folgenden Beispiele verwenden das Schlüsselwort `Global` , um einen Namespace aus dem Stammnamespace für das Projekt zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0e347-153">The following examples use the `Global` keyword to declare a namespace out of the root namespace for the project.</span></span>  
  
 [!code-vb[VbVbalrApplication#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_7.vb)]  
  
 <span data-ttu-id="0e347-154">In einer Namespace-Deklaration kann `Global` nicht in einem anderen Namespace geschachtelt sein.</span><span class="sxs-lookup"><span data-stu-id="0e347-154">In a namespace declaration, `Global` cannot be nested in another namespace.</span></span>  
  
 <span data-ttu-id="0e347-155">Sie können die [Anwendungsseite, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) anzeigen und Ändern der **Stamm-Namespace** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="0e347-155">You can use the [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) to view and modify the **Root Namespace** of the project.</span></span>  <span data-ttu-id="0e347-156">Bei neuen Projekten erhält der **Stammnamespace** standardmäßig den Namen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="0e347-156">For new projects, the **Root Namespace** defaults to the project name.</span></span> <span data-ttu-id="0e347-157">Damit `Global` der Namespace der obersten Ebene ist, können Sie den **Stammnamespace** -Eintrag löschen, so dass das Feld leer ist.</span><span class="sxs-lookup"><span data-stu-id="0e347-157">To cause `Global` to be the top-level namespace, you can clear the **Root Namespace** entry so that the box is empty.</span></span> <span data-ttu-id="0e347-158">Löschen des **Stammnamespace** beseitigt die Notwendigkeit des Schlüsselworts `Global` in Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="0e347-158">Clearing **Root Namespace** removes the need for the `Global` keyword in namespace declarations.</span></span>  
  
 <span data-ttu-id="0e347-159">Wenn eine `Namespace` -Anweisung einen Namen deklariert, der auch ein Namespace in .NET Framework ist, ist der .NET Framework-Namespace nicht mehr verfügbar, wenn das Schlüsselwort `Global` nicht in einem vollständig qualifizierten Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e347-159">If a `Namespace` statement declares a name that is also a namespace in the .NET Framework, the .NET Framework namespace becomes unavailable if the `Global` keyword is not used in a fully qualified name.</span></span> <span data-ttu-id="0e347-160">Um den Zugriff auf diesen .NET Framework-Namespace ohne die Verwendung des Schlüsselworts `Global` zu aktivieren, können Sie das Schlüsselwort `Global` in die `Namespace` -Anweisung aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="0e347-160">To enable access to that .NET Framework namespace without using the `Global` keyword, you can include the `Global` keyword in the `Namespace` statement.</span></span>  
  
 <span data-ttu-id="0e347-161">Das folgende Beispiel enthält in der Namespacedeklaration `Global` das Schlüsselwort `System.Text` .</span><span class="sxs-lookup"><span data-stu-id="0e347-161">The following example has the `Global` keyword in the `System.Text` namespace declaration.</span></span>  
  
 <span data-ttu-id="0e347-162">Wenn das Schlüsselwort `Global` nicht in der Namespacedeklaration enthalten ist, kann auf <xref:System.Text.StringBuilder> nicht zugegriffen werden, ohne dass `Global.System.Text.StringBuilder`festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="0e347-162">If the `Global` keyword was not present in the namespace declaration, <xref:System.Text.StringBuilder> could not be accessed without specifying `Global.System.Text.StringBuilder`.</span></span> <span data-ttu-id="0e347-163">Für ein Projekt mit dem Namen `ConsoleApplication1`greifen Verweise auf `System.Text` auf `ConsoleApplication1.System.Text` zu, wenn das Schlüsselwort `Global` nicht verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="0e347-163">For a project named `ConsoleApplication1`, references to `System.Text` would access `ConsoleApplication1.System.Text` if the `Global` keyword was not used.</span></span>  
  
 [!code-vb[VbVbalrApplication#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_8.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0e347-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e347-164">See Also</span></span>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
 [<span data-ttu-id="0e347-165">Assemblys und der globale Assemblycache</span><span class="sxs-lookup"><span data-stu-id="0e347-165">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="0e347-166">Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="0e347-166">How to: Create and Use Assemblies Using the Command Line</span></span>](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)  
 [<span data-ttu-id="0e347-167">Verweise und die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0e347-167">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="0e347-168">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="0e347-168">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="0e347-169">Schreiben von Code in Office-Projektmappen</span><span class="sxs-lookup"><span data-stu-id="0e347-169">Writing Code in Office Solutions</span></span>](https://msdn.microsoft.com/library/bb608596)
