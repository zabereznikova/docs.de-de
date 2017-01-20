---
title: "Verweise auf deklarierte Elemente (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Deklarierte Elemente"
  - "Verweise auf deklarierte Elemente"
  - "Qualifizierte Namen"
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Verweise auf deklarierte Elemente (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Wenn der Code auf ein deklariertes Element verweist die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] Compiler mit dem Namen im Verweis der entsprechenden Deklaration mit dem Namen übereinstimmt. Wenn mehr als ein Element mit dem gleichen Namen deklariert wird, können Sie steuern, welches dieser Elemente wird durch Verweise auf *qualifizierenden* seinen Namen.  
  
 Der Compiler versucht, einen Namensverweis einen Namen mit entsprechen den *engsten Gültigkeitsbereich*. Dies bedeutet, dass es beginnt mit dem Code, der den Verweis und arbeitet nach außen aufeinander folgende Ebenen der enthaltenden Elemente.  
  
 Das folgende Beispiel zeigt die Verweise auf zwei Variablen mit dem gleichen Namen. Das Beispiel deklariert zwei Variablen, die jeweils den Namen `totalCount`, auf verschiedenen Ebenen des Bereichs im Modul `container`. Wenn die Prozedur `showCount` zeigt `totalCount` ohne Qualifizierung der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] löst der Compiler den Verweis in die Deklaration mit dem engsten Gültigkeitsbereich auf, nämlich die lokale Deklaration in `showCount`. Wenn qualifizierten `totalCount` mit das enthaltende Modul `container`, löst der Compiler den Verweis in die Deklaration mit einem größeren Bereich.  
  
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
 Wenn Sie diesen Suchprozess überschreiben und ein Namen deklariert in einem breiteren Bereich müssen Sie angeben möchten *qualifizieren* den Namen mit dem enthaltenden Element des weiteren Gültigkeitsbereichs. In einigen Fällen möglicherweise auch das enthaltende Element qualifiziert.  
  
 Qualifizieren Namen Mittel vorangeht in der Source-Anweisung mit Informationen, die angibt, in der Target-Element definiert ist. Diese Informationen werden bezeichnet ein *Qualifizierungspfad*. Eine oder mehrere Namespaces und ein Modul, eine Klasse oder Struktur.  
  
 Der Qualifizierungspfad sollten eindeutig angeben, das Modul, Klasse oder Struktur, die das Zielelement enthält. Der Container kann wiederum in einem anderen enthaltenden Element, in der Regel in einem Namespace befinden. Möglicherweise müssen Sie mehrere enthaltende Elemente in den Qualifizierungspfad aufnehmen.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>Auf ein deklariertes Element durch Angabe ihres Namens zugreifen  
  
1.  Bestimmen Sie den Speicherort aus, in dem das Element definiert wurde. Dies kann einen Namespace oder sogar eine Hierarchie von Namespaces enthalten. Innerhalb des Namespace der untersten Ebene muss das Element in einem Modul, Klasse oder Struktur enthalten sein.  
  
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
  
2.  Bestimmen Sie einen Qualifizierungspfad basierend auf der Position des Zielelements. Beginnen Sie mit dem Namespace der obersten Ebene, fahren Sie mit der niedrigsten Ebene-Namespace und endet mit dem Modul, Klasse oder Struktur, die das Zielelement enthält. Jedes Element im Pfad muss es sich um das Element enthalten, das darauf folgt.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3.  Den Qualifizierungspfad für das Zielelement. Punkt (`.`) nach jedem Element im Pfad. Die Anwendung muss Zugriff auf jedes Element im Qualifizierungspfad haben.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  Schreiben Sie den Ausdruck oder Anweisung verweist auf das Zielelement auf die übliche Weise.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  Stellen Sie den Qualifizierungspfad dem Namen des Zielelements voran. Der Name muss sofort den Zeitraum (`.`), folgt das Modul, Klasse oder Struktur, die das Element enthält.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  Der Compiler verwendet den Qualifizierungspfad eine klare, eindeutige Deklaration gefunden, es den Ziel-Elementverweis zuordnen kann.  
  
 Sie möglicherweise auch einen Namensverweis qualifizieren, wenn die Anwendung Zugriff auf mehrere Programmierelemente verfügt, die den gleichen Namen hat. Zum Beispiel die <xref:System.Windows.Forms> und <xref:System.Web.UI.WebControls> beide-Namespaces enthalten eine `Label` Klasse (<xref:System.Windows.Forms.Label?displayProperty=fullName> und <xref:System.Web.UI.WebControls.Label?displayProperty=fullName>). Wenn der Anwendung beide verwendet oder eine eigene definiert `Label` -Klasse, Sie müssen die verschiedenen unterscheiden `Label` Objekte. Schließen Sie den Namespace oder Alias in der Variablendeklaration. Im folgenden Beispiel wird den Importalias.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Mitglieder von anderen Elementen mit  
 Wenn Sie einen nicht freigegebenen Member einer anderen Klasse oder Struktur verwenden, müssen Sie zunächst mit einer Variablen oder Ausdruck, der auf eine Instanz der Klasse oder Struktur zeigt den Elementnamen qualifizieren. Im folgenden Beispiel `demoClass` ist eine Instanz einer Klasse namens `class1`.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 Sie können nicht den Klassennamen selbst verwenden, um einen Member zu qualifizieren, der nicht [Shared](../../../../visual-basic/language-reference/modifiers/shared.md). Sie müssen zunächst eine Instanz in einer Objektvariablen erstellen (in diesem Fall `demoClass`) und anschließend mit dem Variablennamen darauf verweisen.  
  
 Wenn eine Klasse oder Struktur hat ein `Shared` Element können Sie diesen Member entweder mit der Klasse oder Struktur oder mit einer Variablen oder Ausdruck, der auf eine Instanz verweist qualifizieren.  
  
 Ein Modul besitzt keine separaten Instanzen, und alle Member sind `Shared` standardmäßig. Deshalb qualifizieren Sie einen Modulmember mit dem Modulnamen.  
  
 Das folgende Beispiel zeigt gekennzeichnete Verweise auf Module-Element-Prozeduren. Das Beispiel deklariert zwei `Sub` Verfahren, mit dem Namen `perform`, in verschiedenen Modulen eines Projekts. Jede kann ohne Qualifizierung innerhalb des eigenen Moduls angegeben werden, jedoch muss qualifiziert werden, wenn keiner anderen Stelle auf die verwiesen wird. Da der letzte Verweis in `module3` nicht geeignet ist, `perform`, kann der Compiler diesen Verweis nicht auflösen.  
  
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
 Verwenden [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) Elemente, die in einem anderen Projekt definiert werden, müssen Sie zunächst Festlegen einer *Verweis* auf Assembly oder die Typbibliothek des Projekts. Um einen Verweis festlegen möchten, klicken Sie auf **Verweis hinzufügen** auf die **Projekt** Menü, oder verwenden Sie die [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) Befehlszeilen-Compileroption.  
  
 Sie können z. B. das XML-Objektmodell der [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]. Wenn Sie einen Verweis auf die <xref:System.Xml> -Namespace können Sie deklarieren und verwenden Sie eine der Klassen, wie z. B. <xref:System.Xml.XmlDocument>. Im folgenden Beispiel wird <xref:System.Xml.XmlDocument>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Importieren von enthaltenden Elementen  
 Können Sie die [Imports-Anweisung (.NET Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) zu *importieren* Namespaces, die enthalten Module oder Klassen, die Sie verwenden möchten. Dadurch können Sie zum Verweisen auf die definierten Elemente in einem importierten Namespace ohne vollständige Qualifizierung ihrer Namen. Im folgende Beispiel ändert die im vorherige Beispiel zum Importieren der <xref:System.Xml> Namespace.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Darüber hinaus die `Imports` Anweisung können eine *Importieren Alias* für jeden importierten Namespace. Dadurch kann den Quellcode kürzer und leichter lesbar zu sein. Im folgende Beispiel ändert die im vorherige Beispiel verwendet `xD` als Alias für die <xref:System.Xml> Namespace.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 Die `Imports` Anweisung macht nicht Elemente aus anderen Projekten Ihrer Anwendung zur Verfügung. Also ist es nicht das Festlegen eines Verweises stattfinden. Importieren eines Namespace nur beseitigt die Notwendigkeit, die in diesem Namespace definierten Namen zu qualifizieren.  
  
 Sie können auch die `Imports` Anweisung zum Importieren von Modulen, Klassen, Strukturen und Enumerationen. Anschließend können die Member der importierten Elemente ohne Qualifizierung. Allerdings müssen Sie immer qualifizieren nicht freigegebene Member von Klassen und Strukturen mit einer Variable oder einen Ausdruck, der eine Instanz der Klasse oder Struktur ergibt.  
  
## <a name="naming-guidelines"></a>Richtlinien für die Benennung  
 Wenn Sie zwei oder mehrere Programmierelemente definieren, die den gleichen Namen haben, eine *Namen Mehrdeutigkeit* zu führen, wenn der Compiler versucht, einen Verweis auf diesen Namen aufzulösen. Wenn mehr als eine Definition befindet sich im Gültigkeitsbereich oder keine Definition im Gültigkeitsbereich befinden, wird des Verweis nicht aufgelöst werden kann. Ein Beispiel finden Sie unter "Qualifizierten Verweis-Beispiel" auf dieser Hilfeseite.  
  
 Mehrdeutigkeit bei Namen können Sie vermeiden, indem alle Elemente einen eindeutige Namen zuweisen. Anschließend können Sie auf jedes beliebige Element verweisen ohne seinen Namen mit einem Namespace, Modul oder Klasse zu qualifizieren. Sie reduzieren außerdem die Chancen, dass versehentlich auf das falsche Element verweisen.  
  
## <a name="shadowing"></a>Shadowing  
 Wenn zwei Programmierelemente denselben Namen haben, eine davon kann auszublenden, oder *Schatten*, eine. Ein gespiegeltes Element ist nicht verfügbar für Verweis. Stattdessen, wenn der Code verwendet den Namen gespiegelte Element der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] Compiler löst den Verweis in das spiegelnde Element. Eine ausführlichere Erläuterung mit Beispielen finden Sie unter [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [NIB Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Imports-Anweisung (.NET Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [New-Operator](../../../../visual-basic/language-reference/operators/new-operator.md)   
 [Öffentliche](../../../../visual-basic/language-reference/modifiers/public.md)