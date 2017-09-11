---
title: Namespaces in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.global
dev_langs:
- VB
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names, avoiding conflicts
- naming conflicts, namespaces
- namespaces, assemblies
- Visual Basic code, namespaces
- fully qualified names
- naming conventions, naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: bfc9f8f71b5ce5e05b6509ad490354663f894651
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="namespaces-in-visual-basic"></a><span data-ttu-id="a5636-102">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a5636-102">Namespaces in Visual Basic</span></span>
<span data-ttu-id="a5636-103">Namespaces organisieren die in einer Assembly definierten Objekte.</span><span class="sxs-lookup"><span data-stu-id="a5636-103">Namespaces organize the objects defined in an assembly.</span></span> <span data-ttu-id="a5636-104">Assemblys können mehrere Namespaces enthalten, die wiederum andere Namespaces enthalten können.</span><span class="sxs-lookup"><span data-stu-id="a5636-104">Assemblies can contain multiple namespaces, which can in turn contain other namespaces.</span></span> <span data-ttu-id="a5636-105">Namespaces vermeiden Mehrdeutigkeit und vereinfachen Verweise, wenn Sie große Gruppen von Objekten verwenden, zum Beispiel Klassenbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="a5636-105">Namespaces prevent ambiguity and simplify references when using large groups of objects such as class libraries.</span></span>  
  
 <span data-ttu-id="a5636-106">Zum Beispiel die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] definiert die <xref:System.Windows.Forms.ListBox>-Klasse in die <xref:System.Windows.Forms?displayProperty=fullName>Namespace.</xref:System.Windows.Forms?displayProperty=fullName> </xref:System.Windows.Forms.ListBox></span><span class="sxs-lookup"><span data-stu-id="a5636-106">For example, the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] defines the <xref:System.Windows.Forms.ListBox> class in the <xref:System.Windows.Forms?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="a5636-107">Das folgende Codefragment zeigt, wie eine Variable mit dem vollqualifizierten Namen für diese Klasse deklariert wird:</span><span class="sxs-lookup"><span data-stu-id="a5636-107">The following code fragment shows how to declare a variable using the fully qualified name for this class:</span></span>  
  
 <span data-ttu-id="a5636-108">[!code-vb[VbVbalrApplication&6;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a5636-108">[!code-vb[VbVbalrApplication#6](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_1.vb)]</span></span>  
  
## <a name="avoiding-name-collisions"></a><span data-ttu-id="a5636-109">Vermeiden von Namenskonflikten</span><span class="sxs-lookup"><span data-stu-id="a5636-109">Avoiding Name Collisions</span></span>  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]<span data-ttu-id="a5636-110">Namespaces beheben ein Problems bezeichnet *Namespacekonflikte*, in denen der Entwickler einer Klassenbibliothek durch die Verwendung ähnlicher Namen in einer anderen Bibliothek gestört wird.</span><span class="sxs-lookup"><span data-stu-id="a5636-110"> namespaces address a problem sometimes called *namespace pollution*, in which the developer of a class library is hampered by the use of similar names in another library.</span></span> <span data-ttu-id="a5636-111">Diese Konflikte mit vorhandenen Komponenten werden auch als *Namenskonflikte*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a5636-111">These conflicts with existing components are sometimes called *name collisions*.</span></span>  
  
 <span data-ttu-id="a5636-112">Angenommen, Sie erstellen eine neue Klasse namens `ListBox`, können Sie sie innerhalb des Projekts ohne Qualifikation verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5636-112">For example, if you create a new class named `ListBox`, you can use it inside your project without qualification.</span></span> <span data-ttu-id="a5636-113">Allerdings sollten Sie verwenden die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.Windows.Forms.ListBox>Klasse im gleichen Projekt müssen Sie einen vollqualifizierten Verweis verwenden, um den Verweis eindeutig zu machen.</xref:System.Windows.Forms.ListBox></span><span class="sxs-lookup"><span data-stu-id="a5636-113">However, if you want to use the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.Windows.Forms.ListBox> class in the same project, you must use a fully qualified reference to make the reference unique.</span></span> <span data-ttu-id="a5636-114">Wenn der Verweis nicht eindeutig ist, meldet [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] einen Fehler, dass der Name mehrdeutig ist.</span><span class="sxs-lookup"><span data-stu-id="a5636-114">If the reference is not unique, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] produces an error stating that the name is ambiguous.</span></span> <span data-ttu-id="a5636-115">Im folgenden Codebeispiel wird die Deklaration dieser Objekte veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="a5636-115">The following code example demonstrates how to declare these objects:</span></span>  
  
 <span data-ttu-id="a5636-116">[!code-vb[VbVbalrApplication&#7;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a5636-116">[!code-vb[VbVbalrApplication#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_2.vb)]</span></span>  
  
 <span data-ttu-id="a5636-117">Die folgende Abbildung zeigt zwei Namespacehierarchien, beide mit einem Objekt mit dem Namen `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="a5636-117">The following illustration shows two namespace hierarchies, both containing an object named `ListBox`.</span></span>  
  
 <span data-ttu-id="a5636-118">![Namespace-Hierarchie](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.gif "VaNamespaceHierarchy")</span><span class="sxs-lookup"><span data-stu-id="a5636-118">![Namespace Hierarchy](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.gif "vaNamespaceHierarchy")</span></span>  
  
 <span data-ttu-id="a5636-119">Standardmäßig enthält jede mit [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erstellte ausführbare Datei einen Namespace mit demselben Namen wie für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a5636-119">By default, every executable file you create with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] contains a namespace with the same name as your project.</span></span> <span data-ttu-id="a5636-120">Wenn Sie zum Beispiel ein Objekt in einem Projekt mit dem Namen `ListBoxProject`definieren, enthält die ausführbare Datei ListBoxProject.exe einen Namespace mit dem Namen `ListBoxProject`.</span><span class="sxs-lookup"><span data-stu-id="a5636-120">For example, if you define an object within a project named `ListBoxProject`, the executable file ListBoxProject.exe contains a namespace called `ListBoxProject`.</span></span>  
  
 <span data-ttu-id="a5636-121">Mehrere Assemblys können den gleichen Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5636-121">Multiple assemblies can use the same namespace.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="a5636-122"> behandelt sie als einen einzigen Satz von Namen.</span><span class="sxs-lookup"><span data-stu-id="a5636-122"> treats them as a single set of names.</span></span> <span data-ttu-id="a5636-123">Zum Beispiel können Sie Klassen für einen Namespace mit dem Namen `SomeNameSpace` in einer Assembly mit dem Namen `Assemb1` definieren, und zusätzliche Klassen für den gleichen Namespace in einer Assembly mit dem Namen `Assemb2`.</span><span class="sxs-lookup"><span data-stu-id="a5636-123">For example, you can define classes for a namespace called `SomeNameSpace` in an assembly named `Assemb1`, and define additional classes for the same namespace from an assembly named `Assemb2`.</span></span>  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="a5636-124">Vollqualifizierte Namen</span><span class="sxs-lookup"><span data-stu-id="a5636-124">Fully Qualified Names</span></span>  
 <span data-ttu-id="a5636-125">Vollqualifizierte Namen sind Objektverweise, denen der Name des Namespace vorangestellt ist, in dem das Objekt definiert ist.</span><span class="sxs-lookup"><span data-stu-id="a5636-125">Fully qualified names are object references that are prefixed with the name of the namespace in which the object is defined.</span></span> <span data-ttu-id="a5636-126">Sie können in anderen Projekten definierte Objekte verwenden, wenn Sie einen Verweis auf die Klasse erstellen (durch Auswahl von **Verweis hinzufügen** aus dem Menü **Projekt** ) und dann den vollqualifizierten Namen für das Objekt im Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5636-126">You can use objects defined in other projects if you create a reference to the class (by choosing **Add Reference** from the **Project** menu) and then use the fully qualified name for the object in your code.</span></span> <span data-ttu-id="a5636-127">Das folgende Codefragment zeigt, wie Sie den vollqualifizierten Namen für ein Objekt aus dem Namespace eines anderen Projekts verwenden:</span><span class="sxs-lookup"><span data-stu-id="a5636-127">The following code fragment shows how to use the fully qualified name for an object from another project's namespace:</span></span>  
  
 <span data-ttu-id="a5636-128">[!code-vb[VbVbalrApplication&#8;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="a5636-128">[!code-vb[VbVbalrApplication#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_3.vb)]</span></span>  
  
 <span data-ttu-id="a5636-129">Durch vollqualifizierte Namen werden Namenskonflikte vermieden, da der Compiler feststellen kann, welches Objekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a5636-129">Fully qualified names prevent naming conflicts because they make it possible for the compiler to determine which object is being used.</span></span> <span data-ttu-id="a5636-130">Die Namen selbst können jedoch lang und umständlich sein.</span><span class="sxs-lookup"><span data-stu-id="a5636-130">However, the names themselves can get long and cumbersome.</span></span> <span data-ttu-id="a5636-131">Um dies zu umgehen, können Sie die `Imports` -Anweisung für die Definition eines *Alias*verwenden. Diesen abgekürzten Namen können Sie anstelle eines vollqualifizierten Namens verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5636-131">To get around this, you can use the `Imports` statement to define an *alias*—an abbreviated name you can use in place of a fully qualified name.</span></span> <span data-ttu-id="a5636-132">Das folgende Codebeispiel erstellt Aliase für zwei vollqualifizierte Namen und verwendet diese Aliase zur Definition zweier Objekte.</span><span class="sxs-lookup"><span data-stu-id="a5636-132">For example, the following code example creates aliases for two fully qualified names, and uses these aliases to define two objects.</span></span>  
  
 <span data-ttu-id="a5636-133">[!code-vb[VbVbalrApplication&#9;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="a5636-133">[!code-vb[VbVbalrApplication#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_4.vb)]</span></span>  
  
 <span data-ttu-id="a5636-134">[!code-vb[VbVbalrApplication&#10;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="a5636-134">[!code-vb[VbVbalrApplication#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_5.vb)]</span></span>  
  
 <span data-ttu-id="a5636-135">Wenn Sie die `Imports` -Anweisung ohne Alias verwenden, können Sie alle Namen in diesem Namespace ohne Qualifikation verwenden – vorausgesetzt, sie sind in dem Projekt eindeutig.</span><span class="sxs-lookup"><span data-stu-id="a5636-135">If you use the `Imports` statement without an alias, you can use all the names in that namespace without qualification, provided they are unique to the project.</span></span> <span data-ttu-id="a5636-136">Wenn das Projekt `Imports` -Anweisungen für Namespaces enthält, die Elemente mit gleichem Namen enthalten, müssen Sie Namen, die Sie verwenden, vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="a5636-136">If your project contains `Imports` statements for namespaces that contain items with the same name, you must fully qualify that name when you use it.</span></span> <span data-ttu-id="a5636-137">Nehmen wir an, das Projekt enthält die folgenden beiden `Imports` -Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="a5636-137">Suppose, for example, your project contained the following two `Imports` statements:</span></span>  
  
 <span data-ttu-id="a5636-138">[!code-vb[VbVbalrApplication&#11;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="a5636-138">[!code-vb[VbVbalrApplication#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_6.vb)]</span></span>  
  
 <span data-ttu-id="a5636-139">Wenn Sie versuchen, `Class1` zu verwenden ohne diesen Namen voll zu qualifizieren, meldet [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] einen Fehler, dass der Name `Class1` mehrdeutig ist.</span><span class="sxs-lookup"><span data-stu-id="a5636-139">If you attempt to use `Class1` without fully qualifying it, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] produces an error stating that the name `Class1` is ambiguous.</span></span>  
  
## <a name="namespace-level-statements"></a><span data-ttu-id="a5636-140">Namespaceebenen-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="a5636-140">Namespace Level Statements</span></span>  
 <span data-ttu-id="a5636-141">Innerhalb eines Namespace können Sie Elemente wie Module, Schnittstellen, Klassen, Delegaten, Enumerationen, Strukturen und andere Namespaces definieren.</span><span class="sxs-lookup"><span data-stu-id="a5636-141">Within a namespace, you can define items such as modules, interfaces, classes, delegates, enumerations, structures, and other namespaces.</span></span> <span data-ttu-id="a5636-142">Sie können keine Elemente wie Eigenschaften, Prozeduren, Variablen und Ereignisse auf Namespaceebene definieren.</span><span class="sxs-lookup"><span data-stu-id="a5636-142">You cannot define items such as properties, procedures, variables and events at the namespace level.</span></span> <span data-ttu-id="a5636-143">Diese Elemente müssen in Containern, beispielsweise in Modulen, Strukturen oder Klassen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="a5636-143">These items must be declared within containers such as modules, structures, or classes.</span></span>  
  
## <a name="global-keyword-in-fully-qualified-names"></a><span data-ttu-id="a5636-144">Das Schlüsselwort „global“ in vollqualifizierten Namen</span><span class="sxs-lookup"><span data-stu-id="a5636-144">Global Keyword in Fully Qualified Names</span></span>  
 <span data-ttu-id="a5636-145">Wenn Sie eine geschachtelte Hierarchie aus Namespaces definiert haben, Code innerhalb dieser Hierarchie möglicherweise blockiert den Zugriff auf die <xref:System?displayProperty=fullName>-Namespace von .NET Framework.</xref:System?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a5636-145">If you have defined a nested hierarchy of namespaces, code inside that hierarchy might be blocked from accessing the <xref:System?displayProperty=fullName> namespace of the .NET Framework.</span></span> <span data-ttu-id="a5636-146">Das folgende Beispiel veranschaulicht eine Hierarchie, in der die `SpecialSpace.System` Namespace blockiert den Zugriff auf <xref:System?displayProperty=fullName>.</xref:System?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a5636-146">The following example illustrates a hierarchy in which the `SpecialSpace.System` namespace blocks access to <xref:System?displayProperty=fullName>.</span></span>  
  
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
  
 <span data-ttu-id="a5636-147">Visual Basic-Compiler nicht daher auflösen den Verweis auf <xref:System.Int32?displayProperty=fullName>, da `SpecialSpace.System` definiert keine `Int32`.</xref:System.Int32?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a5636-147">As a result, the Visual Basic compiler cannot successfully resolve the reference to <xref:System.Int32?displayProperty=fullName>, because `SpecialSpace.System` does not define `Int32`.</span></span> <span data-ttu-id="a5636-148">Sie können das Schlüsselwort `Global` verwenden, um die Qualifikationskette in der äußersten Ebene der .NET Framework-Klassenbibliothek zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="a5636-148">You can use the `Global` keyword to start the qualification chain at the outermost level of the .NET Framework class library.</span></span> <span data-ttu-id="a5636-149">Dadurch können Sie angeben, die <xref:System?displayProperty=fullName>Namespace oder irgendeinen anderen Namespace in der Klassenbibliothek.</xref:System?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a5636-149">This allows you to specify the <xref:System?displayProperty=fullName> namespace or any other namespace in the class library.</span></span> <span data-ttu-id="a5636-150">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a5636-150">The following example illustrates this.</span></span>  
  
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
  
 <span data-ttu-id="a5636-151">Sie können `Global` andere Namespaces auf Stammebene, z. B. Zugriff auf <xref:Microsoft.VisualBasic?displayProperty=fullName>, und jeden Namespace, der dem Projekt zugeordnet.</xref:Microsoft.VisualBasic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a5636-151">You can use `Global` to access other root-level namespaces, such as <xref:Microsoft.VisualBasic?displayProperty=fullName>, and any namespace associated with your project.</span></span>  
  
## <a name="global-keyword-in-namespace-statements"></a><span data-ttu-id="a5636-152">Global-Schlüsselwort in Namespace-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="a5636-152">Global Keyword in Namespace Statements</span></span>  
 <span data-ttu-id="a5636-153">Sie können auch die `Global` -Schlüsselwort in einer [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a5636-153">You can also use the `Global` keyword in a [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md).</span></span> <span data-ttu-id="a5636-154">Dadurch können Sie einen Namespace aus dem Stammnamespace des Projekts definieren.</span><span class="sxs-lookup"><span data-stu-id="a5636-154">This lets you define a namespace out of the root namespace of your project.</span></span>  
  
 <span data-ttu-id="a5636-155">Alle Namespaces im Projekt basieren auf dem Stammnamespace des Projekts.</span><span class="sxs-lookup"><span data-stu-id="a5636-155">All namespaces in your project are based on the root namespace for the project.</span></span>  <span data-ttu-id="a5636-156">Visual Studio weist den Projektnamen als den Standard-Stammnamespace für den gesamten Code des Projekts zu.</span><span class="sxs-lookup"><span data-stu-id="a5636-156">Visual Studio assigns your project name as the default root namespace for all code in your project.</span></span> <span data-ttu-id="a5636-157">Wenn Ihr Projekt beispielsweise den Namen `ConsoleApplication1`hat, gehören die Programmierelemente zum Namespace `ConsoleApplication1`.</span><span class="sxs-lookup"><span data-stu-id="a5636-157">For example, if your project is named `ConsoleApplication1`, its programming elements belong to namespace `ConsoleApplication1`.</span></span> <span data-ttu-id="a5636-158">Wenn Sie `Namespace Magnetosphere`deklarieren, greifen Verweise auf `Magnetosphere` im Projekt auf `ConsoleApplication1.Magnetosphere`zu.</span><span class="sxs-lookup"><span data-stu-id="a5636-158">If you declare `Namespace Magnetosphere`, references to `Magnetosphere` in the project will access `ConsoleApplication1.Magnetosphere`.</span></span>  
  
 <span data-ttu-id="a5636-159">Die folgenden Beispiele verwenden das Schlüsselwort `Global` , um einen Namespace aus dem Stammnamespace für das Projekt zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a5636-159">The following examples use the `Global` keyword to declare a namespace out of the root namespace for the project.</span></span>  
  
 <span data-ttu-id="a5636-160">[!code-vb[VbVbalrApplication&#22;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="a5636-160">[!code-vb[VbVbalrApplication#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_7.vb)]</span></span>  
  
 <span data-ttu-id="a5636-161">In einer Namespace-Deklaration kann `Global` nicht in einem anderen Namespace geschachtelt sein.</span><span class="sxs-lookup"><span data-stu-id="a5636-161">In a namespace declaration, `Global` cannot be nested in another namespace.</span></span>  
  
 <span data-ttu-id="a5636-162">Können Sie die [Anwendungsseite, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) anzeigen und Ändern der **Stamm-Namespace** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="a5636-162">You can use the [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) to view and modify the **Root Namespace** of the project.</span></span>  <span data-ttu-id="a5636-163">Bei neuen Projekten erhält der **Stammnamespace** standardmäßig den Namen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="a5636-163">For new projects, the **Root Namespace** defaults to the project name.</span></span> <span data-ttu-id="a5636-164">Damit `Global` der Namespace der obersten Ebene ist, können Sie den **Stammnamespace** -Eintrag löschen, so dass das Feld leer ist.</span><span class="sxs-lookup"><span data-stu-id="a5636-164">To cause `Global` to be the top-level namespace, you can clear the **Root Namespace** entry so that the box is empty.</span></span> <span data-ttu-id="a5636-165">Löschen des **Stammnamespace** beseitigt die Notwendigkeit des Schlüsselworts `Global` in Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="a5636-165">Clearing **Root Namespace** removes the need for the `Global` keyword in namespace declarations.</span></span>  
  
 <span data-ttu-id="a5636-166">Wenn eine `Namespace` -Anweisung einen Namen deklariert, der auch ein Namespace in .NET Framework ist, ist der .NET Framework-Namespace nicht mehr verfügbar, wenn das Schlüsselwort `Global` nicht in einem vollständig qualifizierten Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a5636-166">If a `Namespace` statement declares a name that is also a namespace in the .NET Framework, the .NET Framework namespace becomes unavailable if the `Global` keyword is not used in a fully qualified name.</span></span> <span data-ttu-id="a5636-167">Um den Zugriff auf diesen .NET Framework-Namespace ohne die Verwendung des Schlüsselworts `Global` zu aktivieren, können Sie das Schlüsselwort `Global` in die `Namespace` -Anweisung aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="a5636-167">To enable access to that .NET Framework namespace without using the `Global` keyword, you can include the `Global` keyword in the `Namespace` statement.</span></span>  
  
 <span data-ttu-id="a5636-168">Das folgende Beispiel enthält in der Namespacedeklaration `Global` das Schlüsselwort `System.Text` .</span><span class="sxs-lookup"><span data-stu-id="a5636-168">The following example has the `Global` keyword in the `System.Text` namespace declaration.</span></span>  
  
 <span data-ttu-id="a5636-169">Wenn die `Global` Schlüsselwort ist nicht vorhanden, in der Namespacedeklaration <xref:System.Text.StringBuilder>konnte nicht zugegriffen werden, ohne dass `Global.System.Text.StringBuilder`.</xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="a5636-169">If the `Global` keyword was not present in the namespace declaration, <xref:System.Text.StringBuilder> could not be accessed without specifying `Global.System.Text.StringBuilder`.</span></span> <span data-ttu-id="a5636-170">Für ein Projekt mit dem Namen `ConsoleApplication1`greifen Verweise auf `System.Text` auf `ConsoleApplication1.System.Text` zu, wenn das Schlüsselwort `Global` nicht verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a5636-170">For a project named `ConsoleApplication1`, references to `System.Text` would access `ConsoleApplication1.System.Text` if the `Global` keyword was not used.</span></span>  
  
 <span data-ttu-id="a5636-171">[!code-vb[VbVbalrApplication&21;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="a5636-171">[!code-vb[VbVbalrApplication#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_8.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5636-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5636-172">See Also</span></span>  
 <span data-ttu-id="a5636-173"><xref:System.Windows.Forms.ListBox></xref:System.Windows.Forms.ListBox></span><span class="sxs-lookup"><span data-stu-id="a5636-173"><xref:System.Windows.Forms.ListBox></span></span>   
 <span data-ttu-id="a5636-174"><xref:System.Windows.Forms?displayProperty=fullName></xref:System.Windows.Forms?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a5636-174"><xref:System.Windows.Forms?displayProperty=fullName></span></span>   
<span data-ttu-id="a5636-175"> [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="a5636-175"> [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="a5636-176"> [Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) </span><span class="sxs-lookup"><span data-stu-id="a5636-176"> [How to: Create and Use Assemblies Using the Command Line](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) </span></span>  
<span data-ttu-id="a5636-177"> [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a5636-177"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="a5636-178"> [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="a5636-178"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="a5636-179"> [Schreiben von Code in Office-Projektmappen](https://msdn.microsoft.com/library/bb608596)</span><span class="sxs-lookup"><span data-stu-id="a5636-179"> [Writing Code in Office Solutions](https://msdn.microsoft.com/library/bb608596)</span></span>
