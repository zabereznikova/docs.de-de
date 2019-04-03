---
title: Verweise auf deklarierte Elemente (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 5aea43c2dab4eb44ab40449ee6e970a28fdc4abb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821451"
---
# <a name="references-to-declared-elements-visual-basic"></a>Verweise auf deklarierte Elemente (Visual Basic)
Wenn Ihr Code auf einem deklarierten Element verweist, wird von Visual Basic-Compiler dem Namen in den Verweis auf die entsprechende Deklaration mit dem Namen übereinstimmt. Wenn mehr als ein Element mit demselben Namen deklariert wird, können Sie steuern, welches dieser Elemente wird auf das SKD *qualifizierenden* seinen Namen.  
  
 Der Compiler versucht wird, entsprechend einen Namensverweis auf eine Namensdeklaration mit der *engsten Gültigkeitsbereich*. Dies bedeutet, dass es beginnt mit dem Code, der den Verweis und funktioniert nach außen durch aufeinander folgende Ebenen von, die Elemente enthält.  
  
 Im folgenden Beispiel werden Verweise auf zwei Variablen mit dem gleichen Namen. Das Beispiel deklariert zwei Variablen, die in jeder benannten `totalCount`, auf verschiedenen Ebenen des Bereichs im Modul `container`. Wenn die Prozedur `showCount` zeigt `totalCount` ohne Qualifikation verwenden – Visual Basic-Compiler den Verweis auf die Deklaration mit dem engsten Gültigkeitsbereich, nämlich die lokale Deklaration in löst `showCount`. Wenn dies qualifiziert `totalCount` mit das enthaltende Modul `container`, der Compiler löst den Verweis auf die Deklaration mit einem größeren Bereich.  
  
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
 Wenn Sie möchten diesen Suchprozess überschreiben, und geben Sie ein Namen deklariert, in einen größeren Umfang, müssen Sie *qualifizieren* den Namen der mit dem enthaltenden Element des größeren Bereichs. In einigen Fällen möglicherweise Sie auch das enthaltende Element qualifiziert.  
  
 Qualifizieren Namen Mittel vorhergehenden in der Source-Anweisung mit Informationen, die angibt, in denen das Target-Element definiert ist. Diese Informationen wird aufgerufen, eine *qualifizierungszeichenfolge*. Eine oder mehrere Namespaces und ein Modul, eine Klasse oder Struktur.  
  
 Der Qualifizierungspfad sollten eindeutig angeben, das Modul, Klasse oder Struktur, die den Target-Element enthält. Der Container kann wiederum in ein anderes Element enthalten, in der Regel in einem Namespace befinden. Sie müssen möglicherweise mehrere enthaltende Elemente in der qualifizierungszeichenfolge enthalten.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>Auf ein deklariertes Element durch Angabe ihres Namens zugreifen  
  
1.  Bestimmen Sie den Speicherort, in dem das Element definiert wurde. Das kann es sich um einen Namespace oder sogar eine Hierarchie von Namespaces einschließen. In der untersten Ebene-Namespace muss das Element in einem Modul, Klasse oder Struktur enthalten sein.  
  
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
  
2.  Bestimmen eines Qualifizierungspfads abhängig vom Standort für das Zielelement an. Beginnen Sie mit der Namespace der obersten Ebene, fahren Sie mit der Namespace der untersten Ebene fort und endet mit dem Modul, Klasse oder Struktur, die den Target-Element enthält. Jedes Element im Pfad muss es sich um das Element enthalten, das darauf folgt.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3.  Vorbereiten der qualifizierungszeichenfolge für das Zielelement an. Platzieren Sie einen Zeitraum (`.`) nach dem jedes Element im Pfad. Ihre Anwendung muss Zugriff auf jedes Element in der qualifizierungszeichenfolge verfügen.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  Schreiben Sie den Ausdruck oder eine zuweisungsanweisung verweisen auf die übliche Weise an das Zielelement.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  Stellen Sie den Ziel-Elementnamen mit der qualifizierungszeichenfolge voran. Der Name sollte unmittelbar folgen auf den Punkt (`.`), folgt das Modul, Klasse oder Struktur, die das Element enthält.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  Der Compiler verwendet den Qualifizierungspfad eine klare, eindeutige Deklaration gefunden, den Ziel-Elementverweis verglichen werden kann.  
  
 Sie müssen möglicherweise auch einem Namensverweis auf zu qualifizieren, wenn die Anwendung den Zugriff auf mehr als ein Programmierelement ein Element verfügt, die den gleichen Namen hat. Z. B. die <xref:System.Windows.Forms> und <xref:System.Web.UI.WebControls> Namespaces, die beide enthalten eine `Label` Klasse (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> und <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>). Wenn Ihre Anwendung sowohl verwendet, oder eine eigene definiert `Label` -Klasse, Sie müssen die verschiedenen unterscheiden `Label` Objekte. Schließen Sie den Namespace oder Alias, in die Variablendeklaration. Im folgenden Beispiel wird den Importalias.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Mitglieder der anderen enthaltenen Elementen  
 Wenn Sie einen nicht freigegebenen Member einer anderen Klasse oder Struktur verwenden, müssen Sie zunächst den Namen des Members mit einer Variablen oder einen Ausdruck, der mit einer Instanz der Klasse oder Struktur verweist qualifizieren. Im folgenden Beispiel `demoClass` ist eine Instanz einer Klasse namens `class1`.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 Sie können nicht den Klassennamen selbst verwenden, um ein Element zu qualifizieren, die nicht [Shared](../../../../visual-basic/language-reference/modifiers/shared.md). Sie müssen zuerst eine Instanz in eine Objektvariable erstellen (in diesem Fall `demoClass`) und dann durch den Namen der Variablen darauf verweisen.  
  
 Wenn eine Klasse oder Struktur verfügt über eine `Shared` Member, Sie können diesen Member mit dem Namen Klasse oder Struktur oder mit einer Variablen oder einen Ausdruck, der mit einer Instanz verweist qualifizieren.  
  
 Ein Modul keinen separaten Instanzen und alle Member sind `Shared` standardmäßig. Aus diesem Grund sind Sie ein Modul-Element mit dem Modulnamen berechtigt.  
  
 Das folgende Beispiel zeigt die gekennzeichnete Verweise auf Module Member und Prozeduren. Das Beispiel deklariert zwei `Sub` Prozeduren sowohl für benannte `perform`, in anderen Modulen in einem Projekt. Jeder kann ohne Qualifikation in ein eigenes Modul angegeben werden, aber es muss qualifiziert werden, wenn Sie von anderer Stelle auf die verwiesen wird. Da der letzte Verweis in `module3` Dienstgarantien nicht `perform`, der Compiler diesen Verweis kann nicht aufgelöst werden.  
  
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
 Mit [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) Elemente, die in einem anderen Projekt definiert werden, müssen Sie zunächst Festlegen einer *Verweis* auf das Projekt die Assembly bzw. Typbibliothek. Klicken Sie zum Festlegen eines Verweises **Verweis hinzufügen** auf die **Projekt** Menü, oder verwenden Sie die [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) Befehlszeilencompiler-Option.  
  
 Sie können z. B. das XML-Objektmodell verwenden die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Wenn Sie einen Verweis auf die <xref:System.Xml> -Namespace können Sie deklarieren und verwenden Sie eine der Klassen, z. B. <xref:System.Xml.XmlDocument>. Im folgenden Beispiel wird <xref:System.Xml.XmlDocument>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Importieren, die Elemente enthält  
 Können Sie die [Imports-Anweisung (.NET-Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) zu *importieren* die Namespaces, die enthalten Module oder Klassen, die Sie verwenden möchten. Dadurch können Sie zum Verweisen auf die Elemente in einem importierten Namespace ohne vollständige Qualifizierung ihrer Namen definiert. Im folgende Beispiel ändert das vorherige Beispiel importieren Sie die <xref:System.Xml> Namespace.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Darüber hinaus die `Imports` Anweisung kann definieren, ein *Importalias* für jeden importierten Namespace. Dies kann den Quellcode kürzer und leichter lesbar zu machen. Im folgende Beispiel ändert das vorherige Beispiel verwenden Sie `xD` als Alias für die <xref:System.Xml> Namespace.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 Die `Imports` Anweisung macht nicht Elemente aus anderen Projekten Ihrer Anwendung zur Verfügung. D.h., dauert es nicht den Platz der Festlegen eines Verweises. Importieren eines Namespace gerade entfällt die Anforderung, die in diesem Namespace definierten Namen qualifizieren.  
  
 Sie können auch die `Imports` Anweisung zum Importieren der Module, Klassen, Strukturen und Enumerationen. Sie können dann die Elemente der importierten Elemente ohne Qualifikation verwenden. Allerdings müssen Sie immer qualifizieren nicht freigegebene Member von Klassen und Strukturen mit einer Variablen oder einen Ausdruck, der eine Instanz der Klasse oder Struktur ergibt.  
  
## <a name="naming-guidelines"></a>Richtlinien für die Benennung  
 Wenn Sie zwei oder mehrere Programmierelemente definieren, die den gleichen Namen haben eine *Namen Mehrdeutigkeit* kann dazu führen, wenn der Compiler versucht, einen Verweis auf diesen Namen aufzulösen. Wenn mehr als eine Definition befindet sich im Gültigkeitsbereich, oder keine Definition im Bereich der Verweis ist, nicht aufgelöst werden kann. Ein Beispiel finden Sie unter "Qualifizierten Verweis Example" auf dieser Hilfeseite.  
  
 Sie Mehrdeutigkeit bei Namen vermeiden, sodass alle Ihre Elemente eindeutige Namen. Klicken Sie dann können Sie Verweis auf ein Element erstellen, ohne seinen Namen mit dem ein Namespace-, Modul- oder -Klasse zu qualifizieren. Sie reduziert auch die Wahrscheinlichkeit, dass versehentlich das falsche Element auf.  
  
## <a name="shadowing"></a>Shadowing  
 Wenn zwei Programmierelemente mit demselben Namen gemeinsam nutzen, eine davon kann auszublenden, oder *Schatten*, der andere Controller. Ein schattiertes Element steht nicht als Referenz; Stattdessen löst, wenn Ihr Code den Elementnamen für die Shadowing durchgeführt wurde verwendet, die Visual Basic-Compiler es auf das shadowing-Element. Eine ausführlichere Erläuterung anhand von Beispielen, finden Sie unter [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="see-also"></a>Siehe auch

- [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
- [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Imports-Anweisung (.NET-Namespace und -Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [New-Operator](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Public](../../../../visual-basic/language-reference/modifiers/public.md)
