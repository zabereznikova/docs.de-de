---
title: Verweise auf deklarierte Elemente (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 0fca02ab2dcb507c1129f18f31a25c7809fc9710
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917955"
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="8cb6e-102">Verweise auf deklarierte Elemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8cb6e-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="8cb6e-103">Wenn Ihr Code auf einem deklarierten Element verweist, wird von Visual Basic-Compiler dem Namen in den Verweis auf die entsprechende Deklaration mit dem Namen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-103">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="8cb6e-104">Wenn mehr als ein Element mit demselben Namen deklariert wird, können Sie steuern, welches dieser Elemente wird auf das SKD *qualifizierenden* seinen Namen.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="8cb6e-105">Der Compiler versucht wird, entsprechend einen Namensverweis auf eine Namensdeklaration mit der *engsten Gültigkeitsbereich*.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="8cb6e-106">Dies bedeutet, dass es beginnt mit dem Code, der den Verweis und funktioniert nach außen durch aufeinander folgende Ebenen von, die Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="8cb6e-107">Im folgenden Beispiel werden Verweise auf zwei Variablen mit dem gleichen Namen.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="8cb6e-108">Das Beispiel deklariert zwei Variablen, die in jeder benannten `totalCount`, auf verschiedenen Ebenen des Bereichs im Modul `container`.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="8cb6e-109">Wenn die Prozedur `showCount` zeigt `totalCount` ohne Qualifikation verwenden – Visual Basic-Compiler den Verweis auf die Deklaration mit dem engsten Gültigkeitsbereich, nämlich die lokale Deklaration in löst `showCount`.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-109">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="8cb6e-110">Wenn dies qualifiziert `totalCount` mit das enthaltende Modul `container`, der Compiler löst den Verweis auf die Deklaration mit einem größeren Bereich.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
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
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="8cb6e-111">Qualifizieren eines Elementnamens</span><span class="sxs-lookup"><span data-stu-id="8cb6e-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="8cb6e-112">Wenn Sie möchten diesen Suchprozess überschreiben, und geben Sie ein Namen deklariert, in einen größeren Umfang, müssen Sie *qualifizieren* den Namen der mit dem enthaltenden Element des größeren Bereichs.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="8cb6e-113">In einigen Fällen möglicherweise Sie auch das enthaltende Element qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="8cb6e-114">Qualifizieren Namen Mittel vorhergehenden in der Source-Anweisung mit Informationen, die angibt, in denen das Target-Element definiert ist.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="8cb6e-115">Diese Informationen wird aufgerufen, eine *qualifizierungszeichenfolge*.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="8cb6e-116">Eine oder mehrere Namespaces und ein Modul, eine Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="8cb6e-117">Der Qualifizierungspfad sollten eindeutig angeben, das Modul, Klasse oder Struktur, die den Target-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="8cb6e-118">Der Container kann wiederum in ein anderes Element enthalten, in der Regel in einem Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="8cb6e-119">Sie müssen möglicherweise mehrere enthaltende Elemente in der qualifizierungszeichenfolge enthalten.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="8cb6e-120">Auf ein deklariertes Element durch Angabe ihres Namens zugreifen</span><span class="sxs-lookup"><span data-stu-id="8cb6e-120">To access a declared element by qualifying its name</span></span>  
  
1. <span data-ttu-id="8cb6e-121">Bestimmen Sie den Speicherort, in dem das Element definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="8cb6e-122">Das kann es sich um einen Namespace oder sogar eine Hierarchie von Namespaces einschließen.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="8cb6e-123">In der untersten Ebene-Namespace muss das Element in einem Modul, Klasse oder Struktur enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
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
  
2. <span data-ttu-id="8cb6e-124">Bestimmen eines Qualifizierungspfads abhängig vom Standort für das Zielelement an.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="8cb6e-125">Beginnen Sie mit der Namespace der obersten Ebene, fahren Sie mit der Namespace der untersten Ebene fort und endet mit dem Modul, Klasse oder Struktur, die den Target-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="8cb6e-126">Jedes Element im Pfad muss es sich um das Element enthalten, das darauf folgt.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="8cb6e-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="8cb6e-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3. <span data-ttu-id="8cb6e-128">Vorbereiten der qualifizierungszeichenfolge für das Zielelement an.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="8cb6e-129">Platzieren Sie einen Zeitraum (`.`) nach dem jedes Element im Pfad.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="8cb6e-130">Ihre Anwendung muss Zugriff auf jedes Element in der qualifizierungszeichenfolge verfügen.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. <span data-ttu-id="8cb6e-131">Schreiben Sie den Ausdruck oder eine zuweisungsanweisung verweisen auf die übliche Weise an das Zielelement.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. <span data-ttu-id="8cb6e-132">Stellen Sie den Ziel-Elementnamen mit der qualifizierungszeichenfolge voran.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="8cb6e-133">Der Name sollte unmittelbar folgen auf den Punkt (`.`), folgt das Modul, Klasse oder Struktur, die das Element enthält.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. <span data-ttu-id="8cb6e-134">Der Compiler verwendet den Qualifizierungspfad eine klare, eindeutige Deklaration gefunden, den Ziel-Elementverweis verglichen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="8cb6e-135">Sie müssen möglicherweise auch einem Namensverweis auf zu qualifizieren, wenn die Anwendung den Zugriff auf mehr als ein Programmierelement ein Element verfügt, die den gleichen Namen hat.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="8cb6e-136">Z. B. die <xref:System.Windows.Forms> und <xref:System.Web.UI.WebControls> Namespaces, die beide enthalten eine `Label` Klasse (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> und <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="8cb6e-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="8cb6e-137">Wenn Ihre Anwendung sowohl verwendet, oder eine eigene definiert `Label` -Klasse, Sie müssen die verschiedenen unterscheiden `Label` Objekte.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="8cb6e-138">Schließen Sie den Namespace oder Alias, in die Variablendeklaration.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="8cb6e-139">Im folgenden Beispiel wird den Importalias.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="8cb6e-140">Mitglieder der anderen enthaltenen Elementen</span><span class="sxs-lookup"><span data-stu-id="8cb6e-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="8cb6e-141">Wenn Sie einen nicht freigegebenen Member einer anderen Klasse oder Struktur verwenden, müssen Sie zunächst den Namen des Members mit einer Variablen oder einen Ausdruck, der mit einer Instanz der Klasse oder Struktur verweist qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="8cb6e-142">Im folgenden Beispiel `demoClass` ist eine Instanz einer Klasse namens `class1`.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="8cb6e-143">Sie können nicht den Klassennamen selbst verwenden, um ein Element zu qualifizieren, die nicht [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="8cb6e-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="8cb6e-144">Sie müssen zuerst eine Instanz in eine Objektvariable erstellen (in diesem Fall `demoClass`) und dann durch den Namen der Variablen darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="8cb6e-145">Wenn eine Klasse oder Struktur verfügt über eine `Shared` Member, Sie können diesen Member mit dem Namen Klasse oder Struktur oder mit einer Variablen oder einen Ausdruck, der mit einer Instanz verweist qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="8cb6e-146">Ein Modul keinen separaten Instanzen und alle Member sind `Shared` standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="8cb6e-147">Aus diesem Grund sind Sie ein Modul-Element mit dem Modulnamen berechtigt.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="8cb6e-148">Das folgende Beispiel zeigt die gekennzeichnete Verweise auf Module Member und Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="8cb6e-149">Das Beispiel deklariert zwei `Sub` Prozeduren sowohl für benannte `perform`, in anderen Modulen in einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="8cb6e-150">Jeder kann ohne Qualifikation in ein eigenes Modul angegeben werden, aber es muss qualifiziert werden, wenn Sie von anderer Stelle auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="8cb6e-151">Da der letzte Verweis in `module3` Dienstgarantien nicht `perform`, der Compiler diesen Verweis kann nicht aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
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
  
## <a name="references-to-projects"></a><span data-ttu-id="8cb6e-152">Verweise auf Projekte</span><span class="sxs-lookup"><span data-stu-id="8cb6e-152">References to Projects</span></span>  
 <span data-ttu-id="8cb6e-153">Mit [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) Elemente, die in einem anderen Projekt definiert werden, müssen Sie zunächst Festlegen einer *Verweis* auf das Projekt die Assembly bzw. Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="8cb6e-154">Klicken Sie zum Festlegen eines Verweises **Verweis hinzufügen** auf die **Projekt** Menü, oder verwenden Sie die [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) Befehlszeilencompiler-Option.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="8cb6e-155">Sie können z. B. das XML-Objektmodell verwenden die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8cb6e-155">For example, you can use the XML object model of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="8cb6e-156">Wenn Sie einen Verweis auf die <xref:System.Xml> -Namespace können Sie deklarieren und verwenden Sie eine der Klassen, z. B. <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="8cb6e-157">Im folgenden Beispiel wird <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="8cb6e-158">Importieren, die Elemente enthält</span><span class="sxs-lookup"><span data-stu-id="8cb6e-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="8cb6e-159">Können Sie die [Imports-Anweisung (.NET-Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) zu *importieren* die Namespaces, die enthalten Module oder Klassen, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="8cb6e-160">Dadurch können Sie zum Verweisen auf die Elemente in einem importierten Namespace ohne vollständige Qualifizierung ihrer Namen definiert.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="8cb6e-161">Im folgende Beispiel ändert das vorherige Beispiel importieren Sie die <xref:System.Xml> Namespace.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="8cb6e-162">Darüber hinaus die `Imports` Anweisung kann definieren, ein *Importalias* für jeden importierten Namespace.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="8cb6e-163">Dies kann den Quellcode kürzer und leichter lesbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="8cb6e-164">Im folgende Beispiel ändert das vorherige Beispiel verwenden Sie `xD` als Alias für die <xref:System.Xml> Namespace.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="8cb6e-165">Die `Imports` Anweisung macht nicht Elemente aus anderen Projekten Ihrer Anwendung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="8cb6e-166">D.h., dauert es nicht den Platz der Festlegen eines Verweises.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="8cb6e-167">Importieren eines Namespace gerade entfällt die Anforderung, die in diesem Namespace definierten Namen qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="8cb6e-168">Sie können auch die `Imports` Anweisung zum Importieren der Module, Klassen, Strukturen und Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="8cb6e-169">Sie können dann die Elemente der importierten Elemente ohne Qualifikation verwenden.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="8cb6e-170">Allerdings müssen Sie immer qualifizieren nicht freigegebene Member von Klassen und Strukturen mit einer Variablen oder einen Ausdruck, der eine Instanz der Klasse oder Struktur ergibt.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="8cb6e-171">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="8cb6e-171">Naming Guidelines</span></span>  
 <span data-ttu-id="8cb6e-172">Wenn Sie zwei oder mehrere Programmierelemente definieren, die den gleichen Namen haben eine *Namen Mehrdeutigkeit* kann dazu führen, wenn der Compiler versucht, einen Verweis auf diesen Namen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="8cb6e-173">Wenn mehr als eine Definition befindet sich im Gültigkeitsbereich, oder keine Definition im Bereich der Verweis ist, nicht aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="8cb6e-174">Ein Beispiel finden Sie unter "Qualifizierten Verweis Example" auf dieser Hilfeseite.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="8cb6e-175">Sie Mehrdeutigkeit bei Namen vermeiden, sodass alle Ihre Elemente eindeutige Namen.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="8cb6e-176">Klicken Sie dann können Sie Verweis auf ein Element erstellen, ohne seinen Namen mit dem ein Namespace-, Modul- oder -Klasse zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="8cb6e-177">Sie reduziert auch die Wahrscheinlichkeit, dass versehentlich das falsche Element auf.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="8cb6e-178">Shadowing</span><span class="sxs-lookup"><span data-stu-id="8cb6e-178">Shadowing</span></span>  
 <span data-ttu-id="8cb6e-179">Wenn zwei Programmierelemente mit demselben Namen gemeinsam nutzen, eine davon kann auszublenden, oder *Schatten*, der andere Controller.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="8cb6e-180">Ein schattiertes Element steht nicht als Referenz; Stattdessen löst, wenn Ihr Code den Elementnamen für die Shadowing durchgeführt wurde verwendet, die Visual Basic-Compiler es auf das shadowing-Element.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="8cb6e-181">Eine ausführlichere Erläuterung anhand von Beispielen, finden Sie unter [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="8cb6e-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cb6e-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cb6e-182">See also</span></span>

- [<span data-ttu-id="8cb6e-183">Namen deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="8cb6e-183">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="8cb6e-184">Merkmale deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="8cb6e-184">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="8cb6e-185">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="8cb6e-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="8cb6e-186">Variablen</span><span class="sxs-lookup"><span data-stu-id="8cb6e-186">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="8cb6e-187">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="8cb6e-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="8cb6e-188">New-Operator</span><span class="sxs-lookup"><span data-stu-id="8cb6e-188">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="8cb6e-189">Public</span><span class="sxs-lookup"><span data-stu-id="8cb6e-189">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
