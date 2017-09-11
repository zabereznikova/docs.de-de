---
title: Verweise auf deklarierte Elemente (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
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
- declared elements
- references, declared elements
- qualified names
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
caps.latest.revision: 19
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
ms.openlocfilehash: 5de39ac5c30b1cff2a8bfd0cd606dee33c078514
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="24d6e-102">Verweise auf deklarierte Elemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24d6e-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="24d6e-103">Wenn der Code auf ein deklariertes Element verweist die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler mit dem Namen im Verweis der entsprechenden Deklaration mit dem Namen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="24d6e-103">When your code refers to a declared element, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="24d6e-104">Wenn mehr als ein Element mit dem gleichen Namen deklariert wird, können Sie steuern, welches dieser Elemente wird durch Verweise auf *qualifizierenden* seinen Namen.</span><span class="sxs-lookup"><span data-stu-id="24d6e-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="24d6e-105">Der Compiler versucht, einen Namensverweis einen Namen mit entsprechen den *engsten Gültigkeitsbereich*.</span><span class="sxs-lookup"><span data-stu-id="24d6e-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="24d6e-106">Dies bedeutet, dass es beginnt mit dem Code, der den Verweis und arbeitet nach außen aufeinander folgende Ebenen der enthaltenden Elemente.</span><span class="sxs-lookup"><span data-stu-id="24d6e-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="24d6e-107">Das folgende Beispiel zeigt die Verweise auf zwei Variablen mit dem gleichen Namen.</span><span class="sxs-lookup"><span data-stu-id="24d6e-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="24d6e-108">Das Beispiel deklariert zwei Variablen, die jeweils den Namen `totalCount`, auf verschiedenen Ebenen des Bereichs im Modul `container`.</span><span class="sxs-lookup"><span data-stu-id="24d6e-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="24d6e-109">Wenn die Prozedur `showCount` zeigt `totalCount` ohne Qualifizierung der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] löst der Compiler den Verweis in die Deklaration mit dem engsten Gültigkeitsbereich auf, nämlich die lokale Deklaration in `showCount`.</span><span class="sxs-lookup"><span data-stu-id="24d6e-109">When the procedure `showCount` displays `totalCount` without qualification, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="24d6e-110">Wenn qualifizierten `totalCount` mit das enthaltende Modul `container`, löst der Compiler den Verweis in die Deklaration mit einem größeren Bereich.</span><span class="sxs-lookup"><span data-stu-id="24d6e-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="24d6e-111">Qualifizieren eines Elementnamens</span><span class="sxs-lookup"><span data-stu-id="24d6e-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="24d6e-112">Wenn Sie diesen Suchprozess überschreiben und ein Namen deklariert in einem breiteren Bereich müssen Sie angeben möchten *qualifizieren* den Namen mit dem enthaltenden Element des weiteren Gültigkeitsbereichs.</span><span class="sxs-lookup"><span data-stu-id="24d6e-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="24d6e-113">In einigen Fällen möglicherweise auch das enthaltende Element qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="24d6e-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="24d6e-114">Qualifizieren Namen Mittel vorangeht in der Source-Anweisung mit Informationen, die angibt, in der Target-Element definiert ist.</span><span class="sxs-lookup"><span data-stu-id="24d6e-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="24d6e-115">Diese Informationen werden bezeichnet ein *Qualifizierungspfad*.</span><span class="sxs-lookup"><span data-stu-id="24d6e-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="24d6e-116">Eine oder mehrere Namespaces und ein Modul, eine Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="24d6e-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="24d6e-117">Der Qualifizierungspfad sollten eindeutig angeben, das Modul, Klasse oder Struktur, die das Zielelement enthält.</span><span class="sxs-lookup"><span data-stu-id="24d6e-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="24d6e-118">Der Container kann wiederum in einem anderen enthaltenden Element, in der Regel in einem Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="24d6e-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="24d6e-119">Möglicherweise müssen Sie mehrere enthaltende Elemente in den Qualifizierungspfad aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="24d6e-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="24d6e-120">Auf ein deklariertes Element durch Angabe ihres Namens zugreifen</span><span class="sxs-lookup"><span data-stu-id="24d6e-120">To access a declared element by qualifying its name</span></span>  
  
1.  <span data-ttu-id="24d6e-121">Bestimmen Sie den Speicherort aus, in dem das Element definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="24d6e-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="24d6e-122">Dies kann einen Namespace oder sogar eine Hierarchie von Namespaces enthalten.</span><span class="sxs-lookup"><span data-stu-id="24d6e-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="24d6e-123">Innerhalb des Namespace der untersten Ebene muss das Element in einem Modul, Klasse oder Struktur enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="24d6e-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2.  <span data-ttu-id="24d6e-124">Bestimmen Sie einen Qualifizierungspfad basierend auf der Position des Zielelements.</span><span class="sxs-lookup"><span data-stu-id="24d6e-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="24d6e-125">Beginnen Sie mit dem Namespace der obersten Ebene, fahren Sie mit der niedrigsten Ebene-Namespace und endet mit dem Modul, Klasse oder Struktur, die das Zielelement enthält.</span><span class="sxs-lookup"><span data-stu-id="24d6e-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="24d6e-126">Jedes Element im Pfad muss es sich um das Element enthalten, das darauf folgt.</span><span class="sxs-lookup"><span data-stu-id="24d6e-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="24d6e-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="24d6e-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3.  <span data-ttu-id="24d6e-128">Den Qualifizierungspfad für das Zielelement.</span><span class="sxs-lookup"><span data-stu-id="24d6e-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="24d6e-129">Punkt (`.`) nach jedem Element im Pfad.</span><span class="sxs-lookup"><span data-stu-id="24d6e-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="24d6e-130">Die Anwendung muss Zugriff auf jedes Element im Qualifizierungspfad haben.</span><span class="sxs-lookup"><span data-stu-id="24d6e-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  <span data-ttu-id="24d6e-131">Schreiben Sie den Ausdruck oder Anweisung verweist auf das Zielelement auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="24d6e-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  <span data-ttu-id="24d6e-132">Stellen Sie den Qualifizierungspfad dem Namen des Zielelements voran.</span><span class="sxs-lookup"><span data-stu-id="24d6e-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="24d6e-133">Der Name muss sofort den Zeitraum (`.`), folgt das Modul, Klasse oder Struktur, die das Element enthält.</span><span class="sxs-lookup"><span data-stu-id="24d6e-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="24d6e-134">Der Compiler verwendet den Qualifizierungspfad eine klare, eindeutige Deklaration gefunden, es den Ziel-Elementverweis zuordnen kann.</span><span class="sxs-lookup"><span data-stu-id="24d6e-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="24d6e-135">Sie möglicherweise auch einen Namensverweis qualifizieren, wenn die Anwendung Zugriff auf mehrere Programmierelemente verfügt, die den gleichen Namen hat.</span><span class="sxs-lookup"><span data-stu-id="24d6e-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="24d6e-136">Z. B. die <xref:System.Windows.Forms>und <xref:System.Web.UI.WebControls>beide Namespaces enthalten eine `Label` Klasse (<xref:System.Windows.Forms.Label?displayProperty=fullName> und <xref:System.Web.UI.WebControls.Label?displayProperty=fullName>).</xref:System.Web.UI.WebControls.Label?displayProperty=fullName> </xref:System.Windows.Forms.Label?displayProperty=fullName> </xref:System.Web.UI.WebControls> </xref:System.Windows.Forms></span><span class="sxs-lookup"><span data-stu-id="24d6e-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=fullName> and <xref:System.Web.UI.WebControls.Label?displayProperty=fullName>).</span></span> <span data-ttu-id="24d6e-137">Wenn der Anwendung beide verwendet oder eine eigene definiert `Label` -Klasse, Sie müssen die verschiedenen unterscheiden `Label` Objekte.</span><span class="sxs-lookup"><span data-stu-id="24d6e-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="24d6e-138">Schließen Sie den Namespace oder Alias in der Variablendeklaration.</span><span class="sxs-lookup"><span data-stu-id="24d6e-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="24d6e-139">Im folgenden Beispiel wird den Importalias.</span><span class="sxs-lookup"><span data-stu-id="24d6e-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="24d6e-140">Mitglieder von anderen Elementen mit</span><span class="sxs-lookup"><span data-stu-id="24d6e-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="24d6e-141">Wenn Sie einen nicht freigegebenen Member einer anderen Klasse oder Struktur verwenden, müssen Sie zunächst mit einer Variablen oder Ausdruck, der auf eine Instanz der Klasse oder Struktur zeigt den Elementnamen qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="24d6e-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="24d6e-142">Im folgenden Beispiel `demoClass` ist eine Instanz einer Klasse namens `class1`.</span><span class="sxs-lookup"><span data-stu-id="24d6e-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="24d6e-143">Sie können nicht den Klassennamen selbst verwenden, um einen Member zu qualifizieren, der nicht [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="24d6e-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="24d6e-144">Sie müssen zunächst eine Instanz in einer Objektvariablen erstellen (in diesem Fall `demoClass`) und anschließend mit dem Variablennamen darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="24d6e-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="24d6e-145">Wenn eine Klasse oder Struktur hat ein `Shared` Element können Sie diesen Member entweder mit der Klasse oder Struktur oder mit einer Variablen oder Ausdruck, der auf eine Instanz verweist qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="24d6e-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="24d6e-146">Ein Modul besitzt keine separaten Instanzen, und alle Member sind `Shared` standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="24d6e-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="24d6e-147">Deshalb qualifizieren Sie einen Modulmember mit dem Modulnamen.</span><span class="sxs-lookup"><span data-stu-id="24d6e-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="24d6e-148">Das folgende Beispiel zeigt gekennzeichnete Verweise auf Module-Element-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="24d6e-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="24d6e-149">Das Beispiel deklariert zwei `Sub` Verfahren, mit dem Namen `perform`, in verschiedenen Modulen eines Projekts.</span><span class="sxs-lookup"><span data-stu-id="24d6e-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="24d6e-150">Jede kann ohne Qualifizierung innerhalb des eigenen Moduls angegeben werden, jedoch muss qualifiziert werden, wenn keiner anderen Stelle auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="24d6e-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="24d6e-151">Da der letzte Verweis in `module3` nicht geeignet ist, `perform`, kann der Compiler diesen Verweis nicht auflösen.</span><span class="sxs-lookup"><span data-stu-id="24d6e-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a><span data-ttu-id="24d6e-152">Verweise auf Projekte</span><span class="sxs-lookup"><span data-stu-id="24d6e-152">References to Projects</span></span>  
 <span data-ttu-id="24d6e-153">Verwenden [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) Elemente, die in einem anderen Projekt definiert werden, müssen Sie zunächst Festlegen einer *Verweis* auf Assembly oder die Typbibliothek des Projekts.</span><span class="sxs-lookup"><span data-stu-id="24d6e-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="24d6e-154">Um einen Verweis festlegen möchten, klicken Sie auf **Verweis hinzufügen** auf der **Projekt** Menü, oder verwenden Sie die [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) Befehlszeilen-Compileroption.</span><span class="sxs-lookup"><span data-stu-id="24d6e-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="24d6e-155">Sie können z. B. das XML-Objektmodell der [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="24d6e-155">For example, you can use the XML object model of the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="24d6e-156">Wenn Sie einen Verweis auf die <xref:System.Xml>-Namespace können Sie deklarieren und verwenden Sie eine der Klassen, z. B. <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument> </xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="24d6e-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="24d6e-157">Im folgenden Beispiel wird <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument></span><span class="sxs-lookup"><span data-stu-id="24d6e-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="24d6e-158">Importieren von enthaltenden Elementen</span><span class="sxs-lookup"><span data-stu-id="24d6e-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="24d6e-159">Können Sie die [Imports-Anweisung (.NET Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) auf *importieren* Namespaces, die enthalten Module oder Klassen, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="24d6e-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="24d6e-160">Dadurch können Sie zum Verweisen auf die definierten Elemente in einem importierten Namespace ohne vollständige Qualifizierung ihrer Namen.</span><span class="sxs-lookup"><span data-stu-id="24d6e-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="24d6e-161">Im folgende Beispiel ändert die im vorherige Beispiel zum Importieren der <xref:System.Xml>Namespace.</xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="24d6e-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="24d6e-162">Darüber hinaus die `Imports` -Anweisung definieren kann ein *importieren Alias* für jeden importierten Namespace.</span><span class="sxs-lookup"><span data-stu-id="24d6e-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="24d6e-163">Dadurch kann den Quellcode kürzer und leichter lesbar zu sein.</span><span class="sxs-lookup"><span data-stu-id="24d6e-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="24d6e-164">Im folgende Beispiel ändert das vorherige Beispiel verwenden `xD` als Alias für die <xref:System.Xml>Namespace.</xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="24d6e-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="24d6e-165">Die `Imports` Anweisung macht nicht Elemente aus anderen Projekten Ihrer Anwendung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="24d6e-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="24d6e-166">Also ist es nicht das Festlegen eines Verweises stattfinden.</span><span class="sxs-lookup"><span data-stu-id="24d6e-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="24d6e-167">Importieren eines Namespace nur beseitigt die Notwendigkeit, die in diesem Namespace definierten Namen zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="24d6e-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="24d6e-168">Sie können auch die `Imports` Anweisung zum Importieren von Modulen, Klassen, Strukturen und Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="24d6e-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="24d6e-169">Anschließend können die Member der importierten Elemente ohne Qualifizierung.</span><span class="sxs-lookup"><span data-stu-id="24d6e-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="24d6e-170">Allerdings müssen Sie immer qualifizieren nicht freigegebene Member von Klassen und Strukturen mit einer Variable oder einen Ausdruck, der eine Instanz der Klasse oder Struktur ergibt.</span><span class="sxs-lookup"><span data-stu-id="24d6e-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="24d6e-171">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="24d6e-171">Naming Guidelines</span></span>  
 <span data-ttu-id="24d6e-172">Wenn Sie zwei oder mehrere Programmierelemente definieren, die den gleichen Namen haben, eine *Namen Mehrdeutigkeit* zu führen, wenn der Compiler versucht, einen Verweis auf diesen Namen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="24d6e-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="24d6e-173">Wenn mehr als eine Definition befindet sich im Gültigkeitsbereich oder keine Definition im Gültigkeitsbereich befinden, wird des Verweis nicht aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="24d6e-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="24d6e-174">Ein Beispiel finden Sie unter "Qualifizierten Verweis-Beispiel" auf dieser Hilfeseite.</span><span class="sxs-lookup"><span data-stu-id="24d6e-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="24d6e-175">Mehrdeutigkeit bei Namen können Sie vermeiden, indem alle Elemente einen eindeutige Namen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="24d6e-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="24d6e-176">Anschließend können Sie auf jedes beliebige Element verweisen ohne seinen Namen mit einem Namespace, Modul oder Klasse zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="24d6e-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="24d6e-177">Sie reduzieren außerdem die Chancen, dass versehentlich auf das falsche Element verweisen.</span><span class="sxs-lookup"><span data-stu-id="24d6e-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="24d6e-178">Shadowing</span><span class="sxs-lookup"><span data-stu-id="24d6e-178">Shadowing</span></span>  
 <span data-ttu-id="24d6e-179">Wenn zwei Programmierelemente denselben Namen haben, eine davon kann auszublenden, oder *Schatten*, eine.</span><span class="sxs-lookup"><span data-stu-id="24d6e-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="24d6e-180">Ein gespiegeltes Element ist nicht verfügbar für Verweis. Stattdessen, wenn der Code verwendet den Namen gespiegelte Element der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler löst den Verweis in das spiegelnde Element.</span><span class="sxs-lookup"><span data-stu-id="24d6e-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="24d6e-181">Eine ausführlichere Erläuterung mit Beispielen finden Sie unter [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="24d6e-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24d6e-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24d6e-182">See Also</span></span>  
 <span data-ttu-id="24d6e-183">[Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="24d6e-183">[Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="24d6e-184"> [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="24d6e-184"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="24d6e-185"> [NIB Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span><span class="sxs-lookup"><span data-stu-id="24d6e-185"> [NIB How to: Modify Project Properties and Configuration Settings](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span></span>  
<span data-ttu-id="24d6e-186"> [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span><span class="sxs-lookup"><span data-stu-id="24d6e-186"> [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span></span>  
<span data-ttu-id="24d6e-187"> [Imports-Anweisung (.NET-Namespace und -Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="24d6e-187"> [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="24d6e-188"> [New-Operator](../../../../visual-basic/language-reference/operators/new-operator.md) </span><span class="sxs-lookup"><span data-stu-id="24d6e-188"> [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) </span></span>  
<span data-ttu-id="24d6e-189"> [Public](../../../../visual-basic/language-reference/modifiers/public.md)</span><span class="sxs-lookup"><span data-stu-id="24d6e-189"> [Public](../../../../visual-basic/language-reference/modifiers/public.md)</span></span>
