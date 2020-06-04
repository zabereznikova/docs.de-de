---
title: References to Declared Elements
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 23bff2eb098982f67ecb1b709e59096d5259a644
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405182"
---
# <a name="references-to-declared-elements-visual-basic"></a>Verweise auf deklarierte Elemente (Visual Basic)
Wenn sich Ihr Code auf ein deklariertes Element bezieht, entspricht der Visual Basic Compiler dem Namen in Ihrem Verweis auf die entsprechende Deklaration dieses Namens. Wenn mehr als ein Element mit demselben Namen deklariert wird, können Sie steuern, auf welche Elemente verwiesen werden soll, indem Sie den Namen *qualifizieren* .  
  
 Der Compiler versucht, einen namens Verweis auf eine namens Deklaration mit dem *engsten*Gültigkeitsbereich abzugleichen. Dies bedeutet, dass der Code mit dem Code beginnt, der den Verweis durchführt und sich nach aufeinander folgenden Ebenen von enthaltenden Elementen verhält.  
  
 Das folgende Beispiel zeigt Verweise auf zwei Variablen mit demselben Namen. Im Beispiel werden zwei Variablen mit dem Namen `totalCount` auf unterschiedlichen Ebenen des Bereichs im Modul deklariert `container` . Wenn die Prozedur `showCount` `totalCount` ohne Qualifikation angezeigt wird, löst der Visual Basic Compiler den Verweis auf die Deklaration mit dem engsten Gültigkeitsbereich auf, nämlich die lokale Deklaration in `showCount` . Wenn Sie sich `totalCount` für das enthaltende Modul qualifiziert `container` , löst der Compiler den Verweis auf die Deklaration mit dem umfassenderen Bereich auf.  
  
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
  
## <a name="qualifying-an-element-name"></a>Qualifizieren eines Element namens  
 Wenn Sie diesen Suchvorgang außer Kraft setzen und einen Namen angeben möchten, der in einem umfassenderen Bereich deklariert ist, müssen Sie den Namen mit dem enthaltenden Element des umfassenderen Bereichs *qualifizieren* . In einigen Fällen müssen Sie möglicherweise auch das enthaltende Element qualifizieren.  
  
 Das qualifizieren eines Namens bedeutet, dass es in der Quell Anweisung mit Informationen, die bestimmen, wo das Ziel Element definiert ist, vorangestellt wird. Diese Informationen werden als *Qualifizierungs Zeichenfolge*bezeichnet. Es kann einen oder mehrere Namespaces und ein Modul, eine Klasse oder eine Struktur enthalten.  
  
 Die Qualifizierungs Zeichenfolge sollte das Modul, die Klasse oder die Struktur, die das Ziel Element enthält, eindeutig angeben. Der Container kann sich wiederum in einem anderen enthaltenden Element befinden, in der Regel ein Namespace. Möglicherweise müssen Sie mehrere enthaltende Elemente in die Qualifizierungs Zeichenfolge einschließen.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>So greifen Sie auf ein deklariertes Element durch Qualifizierung des Namens zu  
  
1. Bestimmen Sie den Speicherort, an dem das Element definiert wurde. Dies kann einen Namespace oder sogar eine Hierarchie von Namespaces einschließen. Innerhalb des Namespace der untersten Ebene muss das Element in einem Modul, einer Klasse oder einer Struktur enthalten sein.  
  
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
  
2. Bestimmen Sie einen Qualifizierungs Pfad basierend auf dem Speicherort des Ziel Elements. Beginnen Sie mit dem Namespace der höchsten Ebene, fahren Sie mit dem Namespace der untersten Ebene fort, und beenden Sie mit dem Modul, der Klasse oder der Struktur, die das Ziel Element enthält. Jedes Element im Pfad muss das nachfolgendes Element enthalten.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3. Bereiten Sie die Qualifizierungs Zeichenfolge für das Ziel Element vor. Platzieren Sie einen Punkt ( `.` ) hinter jedem Element im Pfad. Die Anwendung muss Zugriff auf jedes Element in ihrer Qualifizierungs Zeichenfolge haben.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. Schreiben Sie den Ausdruck oder die Zuweisungsanweisung, die auf das Ziel Element verweist, auf normale Weise.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. Stellen Sie dem Ziel Elementnamen die Qualifizierungs Zeichenfolge voran. Der Name sollte unmittelbar auf den Zeitraum ( `.` ) folgen, der auf das Modul, die Klasse oder die Struktur folgt, das das Element enthält.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. Der Compiler verwendet die Qualifizierungs Zeichenfolge, um eine eindeutige, eindeutige Deklaration zu finden, der der Verweis auf das Ziel Element entsprechen kann.  
  
 Möglicherweise müssen Sie auch einen Namen Verweis qualifizieren, wenn die Anwendung Zugriff auf mehr als ein Programmier Element hat, das denselben Namen hat. Beispielsweise enthalten die <xref:System.Windows.Forms> <xref:System.Web.UI.WebControls> Namespaces und eine- `Label` Klasse ( <xref:System.Windows.Forms.Label?displayProperty=nameWithType> und <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType> ). Wenn Ihre Anwendung sowohl verwendet, als auch eine eigene Klasse definiert `Label` , müssen Sie die unterschiedlichen Objekte unterscheiden `Label` . Fügen Sie den Namespace oder den importtalias in die Variablen Deklaration ein. Im folgenden Beispiel wird der importieralias verwendet.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Member anderer enthaltender Elemente  
 Wenn Sie einen nicht freigegebenen Member einer anderen Klasse oder Struktur verwenden, müssen Sie zuerst den Elementnamen mit einer Variablen oder einem Ausdruck qualifizieren, die auf eine Instanz der Klasse oder Struktur zeigt. Im folgenden Beispiel `demoClass` ist eine Instanz einer Klasse mit dem Namen `class1` .  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 Sie können den Klassennamen nicht verwenden, um einen Member zu qualifizieren, der nicht frei [gegeben](../../../language-reference/modifiers/shared.md)ist. Sie müssen zunächst eine Instanz in einer Objektvariablen erstellen (in diesem Fall `demoClass` ) und dann mit dem Variablennamen darauf verweisen.  
  
 Wenn eine Klasse oder Struktur über einen `Shared` Member verfügt, können Sie diesen Member entweder mit dem Klassen-oder Struktur Namen oder mit einer Variablen oder einem Ausdruck qualifizieren, die auf eine Instanz verweist.  
  
 Ein Modul weist keine separaten Instanzen auf, und alle seine Member sind `Shared` standardmäßig. Daher qualifizieren Sie einen Modulmember mit dem Modulnamen.  
  
 Das folgende Beispiel zeigt qualifizierte Verweise auf Modulmember-Prozeduren. Im Beispiel werden zwei `Sub` Prozeduren mit dem Namen `perform` in verschiedenen Modulen in einem Projekt deklariert. Jeder kann ohne Qualifikation innerhalb seines eigenen Moduls angegeben werden, muss jedoch qualifiziert werden, wenn von einer anderen Stelle darauf verwiesen wird. Da der abschließende Verweis in `module3` nicht qualifiziert `perform` ist, kann der Compiler diesen Verweis nicht auflösen.  
  
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
  
## <a name="references-to-projects"></a>Verweise auf Projekte  
 Um [öffentliche](../../../language-reference/modifiers/public.md) Elemente zu verwenden, die in einem anderen Projekt definiert sind, müssen Sie zuerst einen *Verweis* auf die Assembly oder Typbibliothek dieses Projekts festlegen. Um einen Verweis festzulegen, klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** , oder verwenden Sie die Befehlszeilen [-Compileroption-Reference (Visual Basic)](../../../reference/command-line-compiler/reference.md) .  
  
 Beispielsweise können Sie das XML-Objektmodell des .NET Framework verwenden. Wenn Sie einen Verweis auf den- <xref:System.Xml> Namespace festgelegt haben, können Sie seine Klassen deklarieren und verwenden, wie z <xref:System.Xml.XmlDocument> . b.. Im folgenden Beispiel wird <xref:System.Xml.XmlDocument> verwendet.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Importieren enthaltender Elemente  
 Sie können die [Imports-Anweisung (.NET-Namespace und-Typ)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) verwenden, um die Namespaces zu *importieren* , die die Module oder Klassen enthalten, die Sie verwenden möchten. Dies ermöglicht es Ihnen, auf die Elemente zu verweisen, die in einem importierten Namespace definiert sind, ohne ihre Namen vollständig zu qualifizieren. Im folgenden Beispiel wird das vorherige Beispiel neu geschrieben, um den- <xref:System.Xml> Namespace zu importieren.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Außerdem kann die- `Imports` Anweisung einen *importieralias* für jeden importierten Namespace definieren. Dadurch kann der Quellcode kürzer und leichter lesbar werden. Im folgenden Beispiel wird das vorherige Beispiel neu geschrieben, sodass es `xD` als Alias für den- <xref:System.Xml> Namespace verwendet wird.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 Die- `Imports` Anweisung macht keine Elemente aus anderen Projekten verfügbar, die für Ihre Anwendung verfügbar sind. Das heißt, es wird kein Verweis festgelegt. Durch das Importieren eines Namespace entfällt die Anforderung, die Namen zu qualifizieren, die in diesem Namespace definiert sind.  
  
 Sie können auch die- `Imports` Anweisung verwenden, um Module, Klassen, Strukturen und Enumerationen zu importieren. Sie können dann die Member dieser importierten Elemente ohne Qualifikation verwenden. Sie müssen jedoch immer nicht freigegebene Member von Klassen und Strukturen mit einer Variablen oder einem Ausdruck qualifizieren, die zu einer Instanz der Klasse oder Struktur ausgewertet wird.  
  
## <a name="naming-guidelines"></a>Richtlinien für die Benennung  
 Wenn Sie zwei oder mehr Programmier Elemente mit demselben Namen definieren, kann eine *namens Mehrdeutigkeit* auftreten, wenn der Compiler versucht, einen Verweis auf diesen Namen aufzulösen. Wenn sich mehr als eine Definition im Gültigkeitsbereich befindet oder wenn sich keine Definition im Gültigkeitsbereich befindet, ist der Verweis nicht auflösbar. Ein Beispiel finden Sie auf dieser Hilfeseite unter "Qualified Reference example".  
  
 Sie können die Mehrdeutigkeit von Namen vermeiden, indem Sie allen Elementen eindeutige Namen geben. Anschließend können Sie einen Verweis auf jedes Element erstellen, ohne seinen Namen mit einem Namespace, Modul oder einer Klasse qualifizieren zu müssen. Außerdem verringern Sie die Wahrscheinlichkeit, dass versehentlich auf das falsche Element verwiesen wird.  
  
## <a name="shadowing"></a>Shadowing  
 Wenn zwei Programmier Elemente denselben Namen haben, kann einer von Ihnen einen ausblenden oder einen *Schatten*der anderen verwenden. Ein Shadowing Element ist für den Verweis nicht verfügbar. Wenn Ihr Code den schattiert-Elementnamen verwendet, wird er stattdessen vom Visual Basic Compiler in das Shadowing-Element aufgelöst. Eine ausführlichere Erläuterung mit Beispielen finden Sie unter [shadowingin Visual Basic](shadowing.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Declared Element Names](declared-element-names.md)
- [Merkmale deklarierter Elemente](declared-element-characteristics.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
- [Variablen](../variables/index.md)
- [Imports-Anweisung (.NET-Namespace und Typ)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [New-Operator](../../../language-reference/operators/new-operator.md)
- [Öffentlich](../../../language-reference/modifiers/public.md)
