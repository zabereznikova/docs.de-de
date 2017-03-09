---
title: "Shared (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Shared"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Shared keyword"
  - "members, shared"
  - "shared members"
  - "nonshared"
  - "shared elements"
  - "elements, shared"
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Shared (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt an, dass mindestens ein deklariertes Programmierelement einer Klasse oder Struktur im Allgemeinen und nicht einer bestimmten Instanz der Klasse bzw. Struktur zugeordnet ist.  
  
## Hinweise  
  
## Verwendung von Shared  
 Durch die Freigabe eines Klassen\- oder Strukturmembers wird dieser allen Instanzen verfügbar gemacht, sodass die einzelnen Instanzen im Gegensatz zu *nicht freigegebenen* Membern nicht über eine eigene Kopie verfügen.  Dies ist z. B. hilfreich, wenn der Wert einer Variablen für die ganze Anwendung gilt.  Wenn Sie diese Variable als `Shared` deklarieren, greifen alle Instanzen auf den gleichen Speicherort zu. Wenn eine Instanz den Wert der Variablen ändert, greifen alle Instanzen auf den aktualisierten Wert zu.  
  
 Durch die Freigabe ändert sich nicht die Zugriffsebene eines Members.  Ein Klassenmember kann z. B. freigegeben und privat \(nur innerhalb der Klasse aufrufbar\) oder nicht freigegeben und öffentlich sein.  Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Regeln  
  
-   **Deklarationskontext.** `Shared` kann nur auf Modulebene verwendet werden.  Dies bedeutet, dass der Deklarationskontext für ein `Shared`\-Element eine Klasse oder Struktur sein muss und keine Quelldatei, kein Namespace oder keine Prozedur sein kann.  
  
-   **Kombinierte Modifizierer.** `Shared` kann nicht zusammen mit [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md) oder [Static](../../../visual-basic/language-reference/modifiers/static.md) in derselben Deklaration verwendet werden.  
  
-   **Zugriff.** Sie können auf ein freigegebenes Element zugreifen, indem Sie es mit seinem Klassen\- oder Strukturnamen und nicht mit dem Variablennamen einer bestimmten Instanz seiner Klasse oder Struktur qualifizieren.  Sie müssen nicht einmal eine Instanz einer Klasse oder Struktur erstellen, um auf seine freigegebenen Member zuzugreifen.  
  
     Im folgenden Beispiel wird die freigegebene <xref:System.Double.IsNaN%2A>\-Prozedur aufgerufen, die durch die <xref:System.Double>\-Struktur verfügbar gemacht wird.  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   **Implizite Freigabe.** Der `Shared`\-Modifizierer kann nicht in einer [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) verwendet werden, Konstanten sind jedoch implizit freigegeben.  Genauso können Sie keinen Member eines Moduls oder einer Schnittstelle als `Shared` deklarieren; sie sind aber implizit freigegeben.  
  
## Verhalten  
  
-   **Speicher.** Eine freigegebene Variable oder ein freigegebenes Ereignis wird nur einmal im Speicher gespeichert. Dies ist unabhängig von der Anzahl von Instanzen, die Sie aus ihrer bzw. seiner Klasse oder Struktur erstellen.  Genauso enthält eine freigegebene Prozedur oder Eigenschaft nur einen Satz lokaler Variablen.  
  
-   **Zugriff über eine Instanzenvariable.** Ein Zugriff auf das freigegebene Element ist möglich, indem das Element mit dem Namen einer Variablen qualifiziert wird, die eine bestimmte Instanz seiner Klasse oder Struktur enthält.  Obwohl dies im Allgemeinen wie erwartet funktioniert, generiert der Compiler eine Warnung und führt den Zugriff über den Klassen\- oder Strukturnamen anstatt über die Variable durch.  
  
-   **Zugriff über einen Instanzenausdruck.** Wenn Sie auf ein freigegebenes Element zugreifen und dabei einen Ausdruck verwenden, der eine Instanz der Klasse oder der Struktur des freigegebenen Elements zurückgibt, führt der Compiler den Zugriff über den Klassen\- oder Strukturnamen durch, anstatt den Ausdruck auszuwerten.  Dies führt zu unerwarteten Ergebnissen, wenn der Ausdruck andere Aktionen ausführen und die Instanz zurückgeben sollte.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
    ```  
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     Im vorhergehenden Beispiel wird in beiden Fällen, in denen der Code über eine Instanz auf die freigegebene Variable `total` zugreift, eine Warnung generiert.  Der Code greift jedes Mal direkt über die `shareTotal`\-Klasse zu und verwendet keine Instanz.  Im Fall des beabsichtigten Aufrufs der `returnClass`\-Prozedur bedeutet dies, dass der Code nicht einmal einen Aufruf von `returnClass` generiert, sodass die zusätzliche Aktion, nämlich das Anzeigen von "Function returnClass\(\) called", nicht ausgeführt wird.  
  
 Der `Shared`\-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Dim\-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Event\-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function\-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator\-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property\-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub\-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Siehe auch  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Static](../../../visual-basic/language-reference/modifiers/static.md)   
 [Lifetime in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)