---
title: Verweise auf deklarierte Elemente (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 18f9920891e35517efe7adcfd4c03e03ac771478
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655810"
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="2dba5-102">Verweise auf deklarierte Elemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2dba5-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="2dba5-103">Wenn Ihr Code eine deklarierte Element verweist, wird der Name in den Verweis auf die entsprechende Deklaration mit diesem Namen von Visual Basic-Compiler abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="2dba5-103">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="2dba5-104">Wenn mehr als ein Element mit demselben Namen deklariert wird, können Sie steuern, welche dieser Elemente sind von verwiesen wird *qualifizierenden* seinen Namen.</span><span class="sxs-lookup"><span data-stu-id="2dba5-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="2dba5-105">Der Compiler versucht, einen Namensverweis auf eine Namensdeklaration mit entsprechen den *engsten Gültigkeitsbereich*.</span><span class="sxs-lookup"><span data-stu-id="2dba5-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="2dba5-106">Dies bedeutet, dass es beginnt mit dem Code, der den Verweis und außen durch aufeinander folgende Ebenen von, die Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="2dba5-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="2dba5-107">Das folgende Beispiel zeigt die Verweise auf zwei Variablen mit dem gleichen Namen.</span><span class="sxs-lookup"><span data-stu-id="2dba5-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="2dba5-108">Das Beispiel deklariert zwei Variablen, die jeweils den Namen `totalCount`, auf verschiedenen Ebenen des Gültigkeitsbereichs im Modul `container`.</span><span class="sxs-lookup"><span data-stu-id="2dba5-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="2dba5-109">Wenn die Prozedur `showCount` zeigt `totalCount` ohne Qualifizierung, löst Visual Basic-Compiler den Verweis auf die Deklaration mit dem engsten Gültigkeitsbereich, nämlich die lokale Deklaration in `showCount`.</span><span class="sxs-lookup"><span data-stu-id="2dba5-109">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="2dba5-110">Wenn dies qualifiziert `totalCount` mit das enthaltende Modul `container`, löst der Compiler den Verweis auf die Deklaration mit einem größeren Bereich.</span><span class="sxs-lookup"><span data-stu-id="2dba5-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
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
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="2dba5-111">Qualifizieren eines Elementnamens</span><span class="sxs-lookup"><span data-stu-id="2dba5-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="2dba5-112">Wenn Sie möchten diesen Suchprozess überschreiben und geben Sie ein Namen deklariert in einen größeren Bereich müssen Sie *qualifizieren* den Namen mit dem enthaltenden Element des größeren Bereich.</span><span class="sxs-lookup"><span data-stu-id="2dba5-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="2dba5-113">In einigen Fällen müssen Sie möglicherweise das enthaltende Element qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="2dba5-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="2dba5-114">Qualifizieren Namen Mittel vorhergehenden in der quellanweisung mit Informationen, die identifizieren, in denen das Target-Element definiert ist.</span><span class="sxs-lookup"><span data-stu-id="2dba5-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="2dba5-115">Diese Informationen wird aufgerufen, eine *qualifizierungszeichenfolge*.</span><span class="sxs-lookup"><span data-stu-id="2dba5-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="2dba5-116">Eine oder mehrere Namespaces und ein Modul, eine Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="2dba5-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="2dba5-117">Der qualifizierungszeichenfolge sollte eindeutig Geben Sie das Modul, Klasse oder Struktur, die den Target-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="2dba5-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="2dba5-118">Der Container kann wiederum in ein anderes Element enthält, in der Regel in einem Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="2dba5-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="2dba5-119">Sie müssen möglicherweise mehrere enthaltende Elemente in der qualifizierungszeichenfolge enthalten.</span><span class="sxs-lookup"><span data-stu-id="2dba5-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="2dba5-120">Auf ein deklarierte Element durch seinen Namen qualifizieren</span><span class="sxs-lookup"><span data-stu-id="2dba5-120">To access a declared element by qualifying its name</span></span>  
  
1.  <span data-ttu-id="2dba5-121">Bestimmen Sie den Speicherort, in dem das Element definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2dba5-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="2dba5-122">Dies könnte es sich um einen Namespace oder sogar eine Hierarchie von Namespaces enthalten.</span><span class="sxs-lookup"><span data-stu-id="2dba5-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="2dba5-123">Innerhalb des Namespaces untersten Ebene muss das Element in einem Modul, Klasse oder Struktur enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="2dba5-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
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
  
2.  <span data-ttu-id="2dba5-124">Bestimmen Sie einen Qualifizierungspfad standortabhängig für den Target-Element.</span><span class="sxs-lookup"><span data-stu-id="2dba5-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="2dba5-125">Beginnen Sie mit der Namespace der obersten Ebene, fahren Sie mit der niedrigsten Ebene Namespace und enden mit dem Modul, Klasse oder Struktur, die den Target-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="2dba5-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="2dba5-126">Jedes Element im Pfad muss das Element enthalten, das darauf folgt.</span><span class="sxs-lookup"><span data-stu-id="2dba5-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="2dba5-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="2dba5-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3.  <span data-ttu-id="2dba5-128">Vorbereiten der qualifizierungszeichenfolge für den Target-Element.</span><span class="sxs-lookup"><span data-stu-id="2dba5-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="2dba5-129">Platzieren Sie einen Punkt (`.`) nach dem jedes Element im Pfad.</span><span class="sxs-lookup"><span data-stu-id="2dba5-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="2dba5-130">Ihre Anwendung muss Zugriff auf jedes Element in der qualifizierungszeichenfolge verfügen.</span><span class="sxs-lookup"><span data-stu-id="2dba5-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  <span data-ttu-id="2dba5-131">Schreiben Sie den Ausdruck oder eine zuweisungsanweisung verweisen auf das Zielelement auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="2dba5-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  <span data-ttu-id="2dba5-132">Der Name des Ziels mit der qualifizierungszeichenfolge vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2dba5-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="2dba5-133">Der Name sollte unmittelbar folgen auf den Punkt (`.`), folgt das Modul, Klasse oder Struktur, die das Element enthält.</span><span class="sxs-lookup"><span data-stu-id="2dba5-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="2dba5-134">Der Compiler verwendet den Qualifizierungspfad eine klare, eindeutige Deklaration gefunden, den Ziel-Elementverweis verglichen werden kann.</span><span class="sxs-lookup"><span data-stu-id="2dba5-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="2dba5-135">Außerdem müssen Sie möglicherweise einen Namensverweis zu qualifizieren, wenn die Anwendung den Zugriff auf mehr als ein Programmierelement, die den gleichen Namen hat.</span><span class="sxs-lookup"><span data-stu-id="2dba5-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="2dba5-136">Z. B. die <xref:System.Windows.Forms> und <xref:System.Web.UI.WebControls> Namespaces beide enthalten eine `Label` Klasse (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> und <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="2dba5-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="2dba5-137">Wenn Ihre Anwendung sowohl verwendet oder wenn sie eine eigene definiert `Label` -Klasse, Sie müssen die verschiedenen unterscheiden `Label` Objekte.</span><span class="sxs-lookup"><span data-stu-id="2dba5-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="2dba5-138">Schließen Sie den Namespace oder Alias in der Variablendeklaration.</span><span class="sxs-lookup"><span data-stu-id="2dba5-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="2dba5-139">Im folgenden Beispiel wird den Importalias.</span><span class="sxs-lookup"><span data-stu-id="2dba5-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="2dba5-140">Mitglieder von anderen Elementen mit</span><span class="sxs-lookup"><span data-stu-id="2dba5-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="2dba5-141">Wenn Sie einen nicht freigegebenen Member einer anderen Klasse oder Struktur verwenden, müssen Sie zuerst den Elementnamen mit einer Variable oder ein Ausdruck, der auf eine Instanz der Klasse oder Struktur zeigt qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="2dba5-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="2dba5-142">Im folgenden Beispiel `demoClass` ist eine Instanz einer Klasse mit dem Namen `class1`.</span><span class="sxs-lookup"><span data-stu-id="2dba5-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="2dba5-143">Sie können nicht den Klassennamen selbst verwenden, um ein Element zu qualifizieren, der nicht [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="2dba5-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="2dba5-144">Erstellen Sie zunächst eine Instanz in einer Object-Variablen (in diesem Fall `demoClass`), und klicken Sie dann den Variablennamen verweisen.</span><span class="sxs-lookup"><span data-stu-id="2dba5-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="2dba5-145">Wenn eine Klasse oder Struktur verfügt über eine `Shared` Member auf, Sie können diesen Member mit den Namen der Klasse oder Struktur oder mit einer Variable oder ein Ausdruck, der auf eine Instanz verweist qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="2dba5-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="2dba5-146">Ein Modul keinen separaten Instanzen und alle seine Member sind `Shared` standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="2dba5-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="2dba5-147">Aus diesem Grund qualifizieren Sie ein Modul-Element mit den Namen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="2dba5-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="2dba5-148">Das folgende Beispiel zeigt gekennzeichnete Verweise auf Modulmemberprozeduren.</span><span class="sxs-lookup"><span data-stu-id="2dba5-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="2dba5-149">Das Beispiel deklariert zwei `Sub` Prozeduren, die beiden benannten `perform`, in anderen Modulen in einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="2dba5-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="2dba5-150">Jeweils kann ohne Qualifizierung innerhalb seiner eigenen Modul angegeben werden, jedoch muss qualifiziert werden, wenn an anderer Stelle verwiesen.</span><span class="sxs-lookup"><span data-stu-id="2dba5-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="2dba5-151">Da der letzte Verweis in `module3` nicht geeignet ist, `perform`, der Compiler kann nicht aufgelöst werden, die auf verweisen.</span><span class="sxs-lookup"><span data-stu-id="2dba5-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
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
  
## <a name="references-to-projects"></a><span data-ttu-id="2dba5-152">Verweise auf Projekte</span><span class="sxs-lookup"><span data-stu-id="2dba5-152">References to Projects</span></span>  
 <span data-ttu-id="2dba5-153">Mit [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) Elemente, die in einem anderen Projekt definiert werden, müssen Sie zunächst Festlegen einer *Verweis* auf dieses Projekt Assembly bzw. Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="2dba5-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="2dba5-154">Klicken Sie zum Festlegen eines Verweises auf **Verweis hinzufügen** auf die **Projekt** Menü, oder verwenden Sie die [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) Befehlszeilen-Compileroption.</span><span class="sxs-lookup"><span data-stu-id="2dba5-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="2dba5-155">Sie können z. B. das XML-Objektmodell das [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2dba5-155">For example, you can use the XML object model of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="2dba5-156">Wenn Sie einen Verweis auf die <xref:System.Xml> -Namespace können Sie deklarieren und verwenden Sie die Klassen, z. B. <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="2dba5-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="2dba5-157">Im folgenden Beispiel wird <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="2dba5-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="2dba5-158">Importieren von Elementen mit</span><span class="sxs-lookup"><span data-stu-id="2dba5-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="2dba5-159">Können Sie die [Imports-Anweisung (.NET Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) auf *importieren* die Namespaces, die enthalten Module oder Klassen, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="2dba5-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="2dba5-160">Dadurch können Sie zum Verweisen auf die Elemente in einem importierten Namespace ohne vollständige Qualifizierung ihrer Namen definiert.</span><span class="sxs-lookup"><span data-stu-id="2dba5-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="2dba5-161">Im folgende Beispiel ändert das vorherige Beispiel importieren Sie die <xref:System.Xml> Namespace.</span><span class="sxs-lookup"><span data-stu-id="2dba5-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="2dba5-162">Darüber hinaus die `Imports` definieren-Anweisung kann eine *Importalias* für jeden importierten Namespace.</span><span class="sxs-lookup"><span data-stu-id="2dba5-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="2dba5-163">Dadurch kann der Quellcode kürzer und leichter lesbar sein.</span><span class="sxs-lookup"><span data-stu-id="2dba5-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="2dba5-164">Im folgende Beispiel ändert das vorherige Beispiel verwenden `xD` als Alias für die <xref:System.Xml> Namespace.</span><span class="sxs-lookup"><span data-stu-id="2dba5-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="2dba5-165">Die `Imports` Anweisung nimmt Elemente aus anderen Projekten für Ihre Anwendung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2dba5-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="2dba5-166">D. h., dauert es nicht die Stelle der einen Verweis festlegen.</span><span class="sxs-lookup"><span data-stu-id="2dba5-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="2dba5-167">Importieren eines Namespaces nur entfällt die Anforderung, die in diesem Namespace definierten Namen zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="2dba5-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="2dba5-168">Sie können auch die `Imports` Anweisung, um Module, Klassen, Strukturen und Enumerationen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="2dba5-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="2dba5-169">Sie können dann die Elemente der importierten Elemente ohne Qualifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="2dba5-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="2dba5-170">Allerdings müssen Sie immer qualifizieren nicht freigegebene Member von Klassen und Strukturen mit einer Variable oder ein Ausdruck, der eine Instanz der Klasse oder Struktur ergibt.</span><span class="sxs-lookup"><span data-stu-id="2dba5-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="2dba5-171">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="2dba5-171">Naming Guidelines</span></span>  
 <span data-ttu-id="2dba5-172">Wenn Sie mindestens zwei Programmierelemente definieren, die den gleichen Namen haben ein *benennen Mehrdeutigkeit* kann dazu führen, wenn der Compiler versucht, einen Verweis auf diesen Namen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="2dba5-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="2dba5-173">Wenn mehr als eine Definition befindet sich im Bereich oder keine Definition im Gültigkeitsbereich befindet, der Verweis nicht aufgelöst ist.</span><span class="sxs-lookup"><span data-stu-id="2dba5-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="2dba5-174">Ein Beispiel finden Sie unter "Qualifizierten Verweis Beispiel" auf dieser Hilfeseite.</span><span class="sxs-lookup"><span data-stu-id="2dba5-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="2dba5-175">Sie können die Mehrdeutigkeit bei Namen vermeiden, durch die Vergabe alle Ihre Elemente eindeutiger Namen.</span><span class="sxs-lookup"><span data-stu-id="2dba5-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="2dba5-176">Sie können dann Verweis auf jedes Element erstellen, ohne dessen Namen einen Namespace, einem Modul oder einer Klasse zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="2dba5-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="2dba5-177">Sie reduzieren außerdem die Chancen einer versehentlich auf dem falschen Element verweisen.</span><span class="sxs-lookup"><span data-stu-id="2dba5-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="2dba5-178">Shadowing</span><span class="sxs-lookup"><span data-stu-id="2dba5-178">Shadowing</span></span>  
 <span data-ttu-id="2dba5-179">Wenn zwei Programmierelemente denselben Namen tragen, eine von ihnen kann auszublenden, oder *Schatten*, eine andere.</span><span class="sxs-lookup"><span data-stu-id="2dba5-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="2dba5-180">Ein schattiertes Element steht nicht zur Referenz; Stattdessen löst, wenn Ihr Code den Shadowing Elementnamen verwendet, Visual Basic-Compiler es auf das shadowing-Element.</span><span class="sxs-lookup"><span data-stu-id="2dba5-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="2dba5-181">Eine ausführlichere Erläuterung mit Beispielen, finden Sie unter [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="2dba5-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dba5-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2dba5-182">See Also</span></span>  
 [<span data-ttu-id="2dba5-183">Namen deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="2dba5-183">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="2dba5-184">Merkmale deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="2dba5-184">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="2dba5-185">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="2dba5-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="2dba5-186">Variablen</span><span class="sxs-lookup"><span data-stu-id="2dba5-186">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="2dba5-187">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="2dba5-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="2dba5-188">New-Operator</span><span class="sxs-lookup"><span data-stu-id="2dba5-188">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="2dba5-189">Public</span><span class="sxs-lookup"><span data-stu-id="2dba5-189">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
