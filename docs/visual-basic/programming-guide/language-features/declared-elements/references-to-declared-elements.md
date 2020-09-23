---
title: References to Declared Elements
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: af5be47335b6d48bd6c0bccc30b8db15c9912807
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085879"
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="8064c-102">Verweise auf deklarierte Elemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8064c-102">References to Declared Elements (Visual Basic)</span></span>

<span data-ttu-id="8064c-103">Wenn sich Ihr Code auf ein deklariertes Element bezieht, entspricht der Visual Basic Compiler dem Namen in Ihrem Verweis auf die entsprechende Deklaration dieses Namens.</span><span class="sxs-lookup"><span data-stu-id="8064c-103">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="8064c-104">Wenn mehr als ein Element mit demselben Namen deklariert wird, können Sie steuern, auf welche Elemente verwiesen werden soll, indem Sie den Namen *qualifizieren* .</span><span class="sxs-lookup"><span data-stu-id="8064c-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="8064c-105">Der Compiler versucht, einen namens Verweis auf eine namens Deklaration mit dem *engsten*Gültigkeitsbereich abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="8064c-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="8064c-106">Dies bedeutet, dass der Code mit dem Code beginnt, der den Verweis durchführt und sich nach aufeinander folgenden Ebenen von enthaltenden Elementen verhält.</span><span class="sxs-lookup"><span data-stu-id="8064c-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="8064c-107">Das folgende Beispiel zeigt Verweise auf zwei Variablen mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="8064c-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="8064c-108">Im Beispiel werden zwei Variablen mit dem Namen `totalCount` auf unterschiedlichen Ebenen des Bereichs im Modul deklariert `container` .</span><span class="sxs-lookup"><span data-stu-id="8064c-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="8064c-109">Wenn die Prozedur `showCount` `totalCount` ohne Qualifikation angezeigt wird, löst der Visual Basic Compiler den Verweis auf die Deklaration mit dem engsten Gültigkeitsbereich auf, nämlich die lokale Deklaration in `showCount` .</span><span class="sxs-lookup"><span data-stu-id="8064c-109">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="8064c-110">Wenn Sie sich `totalCount` für das enthaltende Modul qualifiziert `container` , löst der Compiler den Verweis auf die Deklaration mit dem umfassenderen Bereich auf.</span><span class="sxs-lookup"><span data-stu-id="8064c-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
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
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="8064c-111">Qualifizieren eines Element namens</span><span class="sxs-lookup"><span data-stu-id="8064c-111">Qualifying an Element Name</span></span>  

 <span data-ttu-id="8064c-112">Wenn Sie diesen Suchvorgang außer Kraft setzen und einen Namen angeben möchten, der in einem umfassenderen Bereich deklariert ist, müssen Sie den Namen mit dem enthaltenden Element des umfassenderen Bereichs *qualifizieren* .</span><span class="sxs-lookup"><span data-stu-id="8064c-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="8064c-113">In einigen Fällen müssen Sie möglicherweise auch das enthaltende Element qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="8064c-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="8064c-114">Das qualifizieren eines Namens bedeutet, dass es in der Quell Anweisung mit Informationen, die bestimmen, wo das Ziel Element definiert ist, vorangestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8064c-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="8064c-115">Diese Informationen werden als *Qualifizierungs Zeichenfolge*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="8064c-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="8064c-116">Es kann einen oder mehrere Namespaces und ein Modul, eine Klasse oder eine Struktur enthalten.</span><span class="sxs-lookup"><span data-stu-id="8064c-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="8064c-117">Die Qualifizierungs Zeichenfolge sollte das Modul, die Klasse oder die Struktur, die das Ziel Element enthält, eindeutig angeben.</span><span class="sxs-lookup"><span data-stu-id="8064c-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="8064c-118">Der Container kann sich wiederum in einem anderen enthaltenden Element befinden, in der Regel ein Namespace.</span><span class="sxs-lookup"><span data-stu-id="8064c-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="8064c-119">Möglicherweise müssen Sie mehrere enthaltende Elemente in die Qualifizierungs Zeichenfolge einschließen.</span><span class="sxs-lookup"><span data-stu-id="8064c-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="8064c-120">So greifen Sie auf ein deklariertes Element durch Qualifizierung des Namens zu</span><span class="sxs-lookup"><span data-stu-id="8064c-120">To access a declared element by qualifying its name</span></span>  
  
1. <span data-ttu-id="8064c-121">Bestimmen Sie den Speicherort, an dem das Element definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8064c-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="8064c-122">Dies kann einen Namespace oder sogar eine Hierarchie von Namespaces einschließen.</span><span class="sxs-lookup"><span data-stu-id="8064c-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="8064c-123">Innerhalb des Namespace der untersten Ebene muss das Element in einem Modul, einer Klasse oder einer Struktur enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="8064c-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
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
  
2. <span data-ttu-id="8064c-124">Bestimmen Sie einen Qualifizierungs Pfad basierend auf dem Speicherort des Ziel Elements.</span><span class="sxs-lookup"><span data-stu-id="8064c-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="8064c-125">Beginnen Sie mit dem Namespace der höchsten Ebene, fahren Sie mit dem Namespace der untersten Ebene fort, und beenden Sie mit dem Modul, der Klasse oder der Struktur, die das Ziel Element enthält.</span><span class="sxs-lookup"><span data-stu-id="8064c-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="8064c-126">Jedes Element im Pfad muss das nachfolgendes Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="8064c-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="8064c-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="8064c-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3. <span data-ttu-id="8064c-128">Bereiten Sie die Qualifizierungs Zeichenfolge für das Ziel Element vor.</span><span class="sxs-lookup"><span data-stu-id="8064c-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="8064c-129">Platzieren Sie einen Punkt ( `.` ) hinter jedem Element im Pfad.</span><span class="sxs-lookup"><span data-stu-id="8064c-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="8064c-130">Die Anwendung muss Zugriff auf jedes Element in ihrer Qualifizierungs Zeichenfolge haben.</span><span class="sxs-lookup"><span data-stu-id="8064c-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. <span data-ttu-id="8064c-131">Schreiben Sie den Ausdruck oder die Zuweisungsanweisung, die auf das Ziel Element verweist, auf normale Weise.</span><span class="sxs-lookup"><span data-stu-id="8064c-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. <span data-ttu-id="8064c-132">Stellen Sie dem Ziel Elementnamen die Qualifizierungs Zeichenfolge voran.</span><span class="sxs-lookup"><span data-stu-id="8064c-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="8064c-133">Der Name sollte unmittelbar auf den Zeitraum ( `.` ) folgen, der auf das Modul, die Klasse oder die Struktur folgt, das das Element enthält.</span><span class="sxs-lookup"><span data-stu-id="8064c-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. <span data-ttu-id="8064c-134">Der Compiler verwendet die Qualifizierungs Zeichenfolge, um eine eindeutige, eindeutige Deklaration zu finden, der der Verweis auf das Ziel Element entsprechen kann.</span><span class="sxs-lookup"><span data-stu-id="8064c-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="8064c-135">Möglicherweise müssen Sie auch einen Namen Verweis qualifizieren, wenn die Anwendung Zugriff auf mehr als ein Programmier Element hat, das denselben Namen hat.</span><span class="sxs-lookup"><span data-stu-id="8064c-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="8064c-136">Beispielsweise enthalten die <xref:System.Windows.Forms> <xref:System.Web.UI.WebControls> Namespaces und eine- `Label` Klasse ( <xref:System.Windows.Forms.Label?displayProperty=nameWithType> und <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="8064c-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="8064c-137">Wenn Ihre Anwendung sowohl verwendet, als auch eine eigene Klasse definiert `Label` , müssen Sie die unterschiedlichen Objekte unterscheiden `Label` .</span><span class="sxs-lookup"><span data-stu-id="8064c-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="8064c-138">Fügen Sie den Namespace oder den importtalias in die Variablen Deklaration ein.</span><span class="sxs-lookup"><span data-stu-id="8064c-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="8064c-139">Im folgenden Beispiel wird der importieralias verwendet.</span><span class="sxs-lookup"><span data-stu-id="8064c-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="8064c-140">Member anderer enthaltender Elemente</span><span class="sxs-lookup"><span data-stu-id="8064c-140">Members of Other Containing Elements</span></span>  

 <span data-ttu-id="8064c-141">Wenn Sie einen nicht freigegebenen Member einer anderen Klasse oder Struktur verwenden, müssen Sie zuerst den Elementnamen mit einer Variablen oder einem Ausdruck qualifizieren, die auf eine Instanz der Klasse oder Struktur zeigt.</span><span class="sxs-lookup"><span data-stu-id="8064c-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="8064c-142">Im folgenden Beispiel `demoClass` ist eine Instanz einer Klasse mit dem Namen `class1` .</span><span class="sxs-lookup"><span data-stu-id="8064c-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="8064c-143">Sie können den Klassennamen nicht verwenden, um einen Member zu qualifizieren, der nicht frei [gegeben](../../../language-reference/modifiers/shared.md)ist.</span><span class="sxs-lookup"><span data-stu-id="8064c-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="8064c-144">Sie müssen zunächst eine Instanz in einer Objektvariablen erstellen (in diesem Fall `demoClass` ) und dann mit dem Variablennamen darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="8064c-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="8064c-145">Wenn eine Klasse oder Struktur über einen `Shared` Member verfügt, können Sie diesen Member entweder mit dem Klassen-oder Struktur Namen oder mit einer Variablen oder einem Ausdruck qualifizieren, die auf eine Instanz verweist.</span><span class="sxs-lookup"><span data-stu-id="8064c-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="8064c-146">Ein Modul weist keine separaten Instanzen auf, und alle seine Member sind `Shared` standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="8064c-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="8064c-147">Daher qualifizieren Sie einen Modulmember mit dem Modulnamen.</span><span class="sxs-lookup"><span data-stu-id="8064c-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="8064c-148">Das folgende Beispiel zeigt qualifizierte Verweise auf Modulmember-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="8064c-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="8064c-149">Im Beispiel werden zwei `Sub` Prozeduren mit dem Namen `perform` in verschiedenen Modulen in einem Projekt deklariert.</span><span class="sxs-lookup"><span data-stu-id="8064c-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="8064c-150">Jeder kann ohne Qualifikation innerhalb seines eigenen Moduls angegeben werden, muss jedoch qualifiziert werden, wenn von einer anderen Stelle darauf verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8064c-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="8064c-151">Da der abschließende Verweis in `module3` nicht qualifiziert `perform` ist, kann der Compiler diesen Verweis nicht auflösen.</span><span class="sxs-lookup"><span data-stu-id="8064c-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
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
  
## <a name="references-to-projects"></a><span data-ttu-id="8064c-152">Verweise auf Projekte</span><span class="sxs-lookup"><span data-stu-id="8064c-152">References to Projects</span></span>  

 <span data-ttu-id="8064c-153">Um [öffentliche](../../../language-reference/modifiers/public.md) Elemente zu verwenden, die in einem anderen Projekt definiert sind, müssen Sie zuerst einen *Verweis* auf die Assembly oder Typbibliothek dieses Projekts festlegen.</span><span class="sxs-lookup"><span data-stu-id="8064c-153">To use [Public](../../../language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="8064c-154">Um einen Verweis festzulegen, klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** , oder verwenden Sie die Befehlszeilen [-Compileroption-Reference (Visual Basic)](../../../reference/command-line-compiler/reference.md) .</span><span class="sxs-lookup"><span data-stu-id="8064c-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [-reference (Visual Basic)](../../../reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="8064c-155">Beispielsweise können Sie das XML-Objektmodell des .NET Framework verwenden.</span><span class="sxs-lookup"><span data-stu-id="8064c-155">For example, you can use the XML object model of the .NET Framework.</span></span> <span data-ttu-id="8064c-156">Wenn Sie einen Verweis auf den- <xref:System.Xml> Namespace festgelegt haben, können Sie seine Klassen deklarieren und verwenden, wie z <xref:System.Xml.XmlDocument> . b..</span><span class="sxs-lookup"><span data-stu-id="8064c-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="8064c-157">Im folgenden Beispiel wird <xref:System.Xml.XmlDocument> verwendet.</span><span class="sxs-lookup"><span data-stu-id="8064c-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="8064c-158">Importieren enthaltender Elemente</span><span class="sxs-lookup"><span data-stu-id="8064c-158">Importing Containing Elements</span></span>  

 <span data-ttu-id="8064c-159">Sie können die [Imports-Anweisung (.NET-Namespace und-Typ)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) verwenden, um die Namespaces zu *importieren* , die die Module oder Klassen enthalten, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8064c-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="8064c-160">Dies ermöglicht es Ihnen, auf die Elemente zu verweisen, die in einem importierten Namespace definiert sind, ohne ihre Namen vollständig zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="8064c-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="8064c-161">Im folgenden Beispiel wird das vorherige Beispiel neu geschrieben, um den- <xref:System.Xml> Namespace zu importieren.</span><span class="sxs-lookup"><span data-stu-id="8064c-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="8064c-162">Außerdem kann die- `Imports` Anweisung einen *importieralias* für jeden importierten Namespace definieren.</span><span class="sxs-lookup"><span data-stu-id="8064c-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="8064c-163">Dadurch kann der Quellcode kürzer und leichter lesbar werden.</span><span class="sxs-lookup"><span data-stu-id="8064c-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="8064c-164">Im folgenden Beispiel wird das vorherige Beispiel neu geschrieben, sodass es `xD` als Alias für den- <xref:System.Xml> Namespace verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8064c-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="8064c-165">Die- `Imports` Anweisung macht keine Elemente aus anderen Projekten verfügbar, die für Ihre Anwendung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8064c-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="8064c-166">Das heißt, es wird kein Verweis festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8064c-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="8064c-167">Durch das Importieren eines Namespace entfällt die Anforderung, die Namen zu qualifizieren, die in diesem Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="8064c-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="8064c-168">Sie können auch die- `Imports` Anweisung verwenden, um Module, Klassen, Strukturen und Enumerationen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="8064c-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="8064c-169">Sie können dann die Member dieser importierten Elemente ohne Qualifikation verwenden.</span><span class="sxs-lookup"><span data-stu-id="8064c-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="8064c-170">Sie müssen jedoch immer nicht freigegebene Member von Klassen und Strukturen mit einer Variablen oder einem Ausdruck qualifizieren, die zu einer Instanz der Klasse oder Struktur ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="8064c-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="8064c-171">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="8064c-171">Naming Guidelines</span></span>  

 <span data-ttu-id="8064c-172">Wenn Sie zwei oder mehr Programmier Elemente mit demselben Namen definieren, kann eine *namens Mehrdeutigkeit* auftreten, wenn der Compiler versucht, einen Verweis auf diesen Namen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="8064c-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="8064c-173">Wenn sich mehr als eine Definition im Gültigkeitsbereich befindet oder wenn sich keine Definition im Gültigkeitsbereich befindet, ist der Verweis nicht auflösbar.</span><span class="sxs-lookup"><span data-stu-id="8064c-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="8064c-174">Ein Beispiel finden Sie auf dieser Hilfeseite unter "Qualified Reference example".</span><span class="sxs-lookup"><span data-stu-id="8064c-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="8064c-175">Sie können die Mehrdeutigkeit von Namen vermeiden, indem Sie allen Elementen eindeutige Namen geben.</span><span class="sxs-lookup"><span data-stu-id="8064c-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="8064c-176">Anschließend können Sie einen Verweis auf jedes Element erstellen, ohne seinen Namen mit einem Namespace, Modul oder einer Klasse qualifizieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="8064c-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="8064c-177">Außerdem verringern Sie die Wahrscheinlichkeit, dass versehentlich auf das falsche Element verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8064c-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="8064c-178">Shadowing</span><span class="sxs-lookup"><span data-stu-id="8064c-178">Shadowing</span></span>  

 <span data-ttu-id="8064c-179">Wenn zwei Programmier Elemente denselben Namen haben, kann einer von Ihnen einen ausblenden oder einen *Schatten*der anderen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8064c-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="8064c-180">Ein Shadowing Element ist für den Verweis nicht verfügbar. Wenn Ihr Code den schattiert-Elementnamen verwendet, wird er stattdessen vom Visual Basic Compiler in das Shadowing-Element aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="8064c-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="8064c-181">Eine ausführlichere Erläuterung mit Beispielen finden Sie unter [shadowingin Visual Basic](shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="8064c-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8064c-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8064c-182">See also</span></span>

- [<span data-ttu-id="8064c-183">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="8064c-183">Declared Element Names</span></span>](declared-element-names.md)
- [<span data-ttu-id="8064c-184">Merkmale deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="8064c-184">Declared Element Characteristics</span></span>](declared-element-characteristics.md)
- [<span data-ttu-id="8064c-185">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="8064c-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="8064c-186">Variablen</span><span class="sxs-lookup"><span data-stu-id="8064c-186">Variables</span></span>](../variables/index.md)
- [<span data-ttu-id="8064c-187">Imports-Anweisung (.NET-Namespace und Typ)</span><span class="sxs-lookup"><span data-stu-id="8064c-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="8064c-188">New-Operator</span><span class="sxs-lookup"><span data-stu-id="8064c-188">New Operator</span></span>](../../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="8064c-189">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="8064c-189">Public</span></span>](../../../language-reference/modifiers/public.md)
