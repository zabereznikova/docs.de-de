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
---
# <a name="references-to-declared-elements-visual-basic"></a>Verweise auf deklarierte Elemente (Visual Basic)
Wenn Ihr Code eine deklarierte Element verweist, wird der Name in den Verweis auf die entsprechende Deklaration mit diesem Namen von Visual Basic-Compiler abgeglichen. Wenn mehr als ein Element mit demselben Namen deklariert wird, können Sie steuern, welche dieser Elemente sind von verwiesen wird *qualifizierenden* seinen Namen.  
  
 Der Compiler versucht, einen Namensverweis auf eine Namensdeklaration mit entsprechen den *engsten Gültigkeitsbereich*. Dies bedeutet, dass es beginnt mit dem Code, der den Verweis und außen durch aufeinander folgende Ebenen von, die Elemente enthält.  
  
 Das folgende Beispiel zeigt die Verweise auf zwei Variablen mit dem gleichen Namen. Das Beispiel deklariert zwei Variablen, die jeweils den Namen `totalCount`, auf verschiedenen Ebenen des Gültigkeitsbereichs im Modul `container`. Wenn die Prozedur `showCount` zeigt `totalCount` ohne Qualifizierung, löst Visual Basic-Compiler den Verweis auf die Deklaration mit dem engsten Gültigkeitsbereich, nämlich die lokale Deklaration in `showCount`. Wenn dies qualifiziert `totalCount` mit das enthaltende Modul `container`, löst der Compiler den Verweis auf die Deklaration mit einem größeren Bereich.  
  
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
  
## <a name="qualifying-an-element-name"></a>Qualifizieren eines Elementnamens  
 Wenn Sie möchten diesen Suchprozess überschreiben und geben Sie ein Namen deklariert in einen größeren Bereich müssen Sie *qualifizieren* den Namen mit dem enthaltenden Element des größeren Bereich. In einigen Fällen müssen Sie möglicherweise das enthaltende Element qualifiziert.  
  
 Qualifizieren Namen Mittel vorhergehenden in der quellanweisung mit Informationen, die identifizieren, in denen das Target-Element definiert ist. Diese Informationen wird aufgerufen, eine *qualifizierungszeichenfolge*. Eine oder mehrere Namespaces und ein Modul, eine Klasse oder Struktur.  
  
 Der qualifizierungszeichenfolge sollte eindeutig Geben Sie das Modul, Klasse oder Struktur, die den Target-Element enthält. Der Container kann wiederum in ein anderes Element enthält, in der Regel in einem Namespace befinden. Sie müssen möglicherweise mehrere enthaltende Elemente in der qualifizierungszeichenfolge enthalten.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>Auf ein deklarierte Element durch seinen Namen qualifizieren  
  
1.  Bestimmen Sie den Speicherort, in dem das Element definiert wurde. Dies könnte es sich um einen Namespace oder sogar eine Hierarchie von Namespaces enthalten. Innerhalb des Namespaces untersten Ebene muss das Element in einem Modul, Klasse oder Struktur enthalten sein.  
  
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
  
2.  Bestimmen Sie einen Qualifizierungspfad standortabhängig für den Target-Element. Beginnen Sie mit der Namespace der obersten Ebene, fahren Sie mit der niedrigsten Ebene Namespace und enden mit dem Modul, Klasse oder Struktur, die den Target-Element enthält. Jedes Element im Pfad muss das Element enthalten, das darauf folgt.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3.  Vorbereiten der qualifizierungszeichenfolge für den Target-Element. Platzieren Sie einen Punkt (`.`) nach dem jedes Element im Pfad. Ihre Anwendung muss Zugriff auf jedes Element in der qualifizierungszeichenfolge verfügen.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  Schreiben Sie den Ausdruck oder eine zuweisungsanweisung verweisen auf das Zielelement auf die übliche Weise.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  Der Name des Ziels mit der qualifizierungszeichenfolge vorangestellt werden. Der Name sollte unmittelbar folgen auf den Punkt (`.`), folgt das Modul, Klasse oder Struktur, die das Element enthält.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  Der Compiler verwendet den Qualifizierungspfad eine klare, eindeutige Deklaration gefunden, den Ziel-Elementverweis verglichen werden kann.  
  
 Außerdem müssen Sie möglicherweise einen Namensverweis zu qualifizieren, wenn die Anwendung den Zugriff auf mehr als ein Programmierelement, die den gleichen Namen hat. Z. B. die <xref:System.Windows.Forms> und <xref:System.Web.UI.WebControls> Namespaces beide enthalten eine `Label` Klasse (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> und <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>). Wenn Ihre Anwendung sowohl verwendet oder wenn sie eine eigene definiert `Label` -Klasse, Sie müssen die verschiedenen unterscheiden `Label` Objekte. Schließen Sie den Namespace oder Alias in der Variablendeklaration. Im folgenden Beispiel wird den Importalias.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Mitglieder von anderen Elementen mit  
 Wenn Sie einen nicht freigegebenen Member einer anderen Klasse oder Struktur verwenden, müssen Sie zuerst den Elementnamen mit einer Variable oder ein Ausdruck, der auf eine Instanz der Klasse oder Struktur zeigt qualifizieren. Im folgenden Beispiel `demoClass` ist eine Instanz einer Klasse mit dem Namen `class1`.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 Sie können nicht den Klassennamen selbst verwenden, um ein Element zu qualifizieren, der nicht [Shared](../../../../visual-basic/language-reference/modifiers/shared.md). Erstellen Sie zunächst eine Instanz in einer Object-Variablen (in diesem Fall `demoClass`), und klicken Sie dann den Variablennamen verweisen.  
  
 Wenn eine Klasse oder Struktur verfügt über eine `Shared` Member auf, Sie können diesen Member mit den Namen der Klasse oder Struktur oder mit einer Variable oder ein Ausdruck, der auf eine Instanz verweist qualifizieren.  
  
 Ein Modul keinen separaten Instanzen und alle seine Member sind `Shared` standardmäßig. Aus diesem Grund qualifizieren Sie ein Modul-Element mit den Namen des Moduls.  
  
 Das folgende Beispiel zeigt gekennzeichnete Verweise auf Modulmemberprozeduren. Das Beispiel deklariert zwei `Sub` Prozeduren, die beiden benannten `perform`, in anderen Modulen in einem Projekt. Jeweils kann ohne Qualifizierung innerhalb seiner eigenen Modul angegeben werden, jedoch muss qualifiziert werden, wenn an anderer Stelle verwiesen. Da der letzte Verweis in `module3` nicht geeignet ist, `perform`, der Compiler kann nicht aufgelöst werden, die auf verweisen.  
  
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
 Mit [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) Elemente, die in einem anderen Projekt definiert werden, müssen Sie zunächst Festlegen einer *Verweis* auf dieses Projekt Assembly bzw. Typbibliothek. Klicken Sie zum Festlegen eines Verweises auf **Verweis hinzufügen** auf die **Projekt** Menü, oder verwenden Sie die [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) Befehlszeilen-Compileroption.  
  
 Sie können z. B. das XML-Objektmodell das [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Wenn Sie einen Verweis auf die <xref:System.Xml> -Namespace können Sie deklarieren und verwenden Sie die Klassen, z. B. <xref:System.Xml.XmlDocument>. Im folgenden Beispiel wird <xref:System.Xml.XmlDocument>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Importieren von Elementen mit  
 Können Sie die [Imports-Anweisung (.NET Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) auf *importieren* die Namespaces, die enthalten Module oder Klassen, die Sie verwenden möchten. Dadurch können Sie zum Verweisen auf die Elemente in einem importierten Namespace ohne vollständige Qualifizierung ihrer Namen definiert. Im folgende Beispiel ändert das vorherige Beispiel importieren Sie die <xref:System.Xml> Namespace.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Darüber hinaus die `Imports` definieren-Anweisung kann eine *Importalias* für jeden importierten Namespace. Dadurch kann der Quellcode kürzer und leichter lesbar sein. Im folgende Beispiel ändert das vorherige Beispiel verwenden `xD` als Alias für die <xref:System.Xml> Namespace.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 Die `Imports` Anweisung nimmt Elemente aus anderen Projekten für Ihre Anwendung verfügbar. D. h., dauert es nicht die Stelle der einen Verweis festlegen. Importieren eines Namespaces nur entfällt die Anforderung, die in diesem Namespace definierten Namen zu qualifizieren.  
  
 Sie können auch die `Imports` Anweisung, um Module, Klassen, Strukturen und Enumerationen zu importieren. Sie können dann die Elemente der importierten Elemente ohne Qualifizierung verwenden. Allerdings müssen Sie immer qualifizieren nicht freigegebene Member von Klassen und Strukturen mit einer Variable oder ein Ausdruck, der eine Instanz der Klasse oder Struktur ergibt.  
  
## <a name="naming-guidelines"></a>Richtlinien für die Benennung  
 Wenn Sie mindestens zwei Programmierelemente definieren, die den gleichen Namen haben ein *benennen Mehrdeutigkeit* kann dazu führen, wenn der Compiler versucht, einen Verweis auf diesen Namen aufzulösen. Wenn mehr als eine Definition befindet sich im Bereich oder keine Definition im Gültigkeitsbereich befindet, der Verweis nicht aufgelöst ist. Ein Beispiel finden Sie unter "Qualifizierten Verweis Beispiel" auf dieser Hilfeseite.  
  
 Sie können die Mehrdeutigkeit bei Namen vermeiden, durch die Vergabe alle Ihre Elemente eindeutiger Namen. Sie können dann Verweis auf jedes Element erstellen, ohne dessen Namen einen Namespace, einem Modul oder einer Klasse zu qualifizieren. Sie reduzieren außerdem die Chancen einer versehentlich auf dem falschen Element verweisen.  
  
## <a name="shadowing"></a>Shadowing  
 Wenn zwei Programmierelemente denselben Namen tragen, eine von ihnen kann auszublenden, oder *Schatten*, eine andere. Ein schattiertes Element steht nicht zur Referenz; Stattdessen löst, wenn Ihr Code den Shadowing Elementnamen verwendet, Visual Basic-Compiler es auf das shadowing-Element. Eine ausführlichere Erläuterung mit Beispielen, finden Sie unter [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)  
 [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [New-Operator](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [Public](../../../../visual-basic/language-reference/modifiers/public.md)
