---
title: "Namespaces in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.global"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Assemblys [Visual Basic], Namespaces"
  - "Namenskonflikte"
  - "Global-Schlüsselwort [Visual Basic]"
  - "Namespacekonflikte"
  - "Namen, Vermeiden von Konflikten"
  - "Namenskonflikte, Namespaces"
  - "Namespaces, Assemblys"
  - "Visual Basic-Code, Namespaces"
  - "Vollqualifizierte Namen"
  - "Namenskonventionen, Namenskonflikte"
  - "Namespaces"
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Namespaces in Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Namespaces organisieren die in einer Assembly definierten Objekte. Assemblys können mehrere Namespaces enthalten, die wiederum andere Namespaces enthalten können. Namespaces vermeiden Mehrdeutigkeit und vereinfachen Verweise, wenn Sie große Gruppen von Objekten verwenden, zum Beispiel Klassenbibliotheken.  
  
 Zum Beispiel definiert [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] die <xref:System.Windows.Forms.ListBox>\-Klasse im <xref:System.Windows.Forms?displayProperty=fullName>\-Namespace. Das folgende Codefragment zeigt, wie eine Variable mit dem vollqualifizierten Namen für diese Klasse deklariert wird:  
  
 [!code-vb[VbVbalrApplication#6](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_1.vb)]  
  
## Vermeiden von Namenskonflikten  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Namespaces beheben ein Problem, das manchmal als *Namespacekonflikte* bezeichnet wird. Dabei wird die Entwicklung einer Klassenbibliothek durch die Verwendung ähnlicher Namen in einer anderen Bibliothek beeinträchtigt. Diese Konflikte mit vorhandenen Komponenten werden auch als *Namenskonflikte* bezeichnet.  
  
 Angenommen, Sie erstellen eine neue Klasse namens `ListBox`, können Sie sie innerhalb des Projekts ohne Qualifikation verwenden. Sollten Sie jedoch die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] <xref:System.Windows.Forms.ListBox>\-Klasse im gleichen Projekt verwenden, müssen Sie einen vollqualifizierten Verweis verwenden, um den Verweis eindeutig zu machen. Wenn der Verweis nicht eindeutig ist, meldet [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] einen Fehler, dass der Name mehrdeutig ist. Im folgenden Codebeispiel wird die Deklaration dieser Objekte veranschaulicht:  
  
 [!code-vb[VbVbalrApplication#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_2.vb)]  
  
 Die folgende Abbildung zeigt zwei Namespacehierarchien, beide mit einem Objekt mit dem Namen `ListBox`.  
  
 ![Namespacehierarchie](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.png "vaNamespaceHierarchy")  
  
 Standardmäßig enthält jede mit [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] erstellte ausführbare Datei einen Namespace mit demselben Namen wie für das Projekt. Wenn Sie zum Beispiel ein Objekt in einem Projekt mit dem Namen `ListBoxProject` definieren, enthält die ausführbare Datei ListBoxProject.exe einen Namespace mit dem Namen `ListBoxProject`.  
  
 Mehrere Assemblys können den gleichen Namen verwenden.[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] behandelt sie als einen einzigen Satz von Namen. Zum Beispiel können Sie Klassen für einen Namespace mit dem Namen `SomeNameSpace` in einer Assembly mit dem Namen `Assemb1` definieren, und zusätzliche Klassen für den gleichen Namespace in einer Assembly mit dem Namen `Assemb2`.  
  
## Vollqualifizierte Namen  
 Vollqualifizierte Namen sind Objektverweise, denen der Name des Namespace vorangestellt ist, in dem das Objekt definiert ist. Sie können in anderen Projekten definierte Objekte verwenden, wenn Sie einen Verweis auf die Klasse erstellen \(durch Auswahl von **Verweis hinzufügen** aus dem Menü **Projekt**\) und dann den vollqualifizierten Namen für das Objekt im Code verwenden. Das folgende Codefragment zeigt, wie Sie den vollqualifizierten Namen für ein Objekt aus dem Namespace eines anderen Projekts verwenden:  
  
 [!code-vb[VbVbalrApplication#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_3.vb)]  
  
 Durch vollqualifizierte Namen werden Namenskonflikte vermieden, da der Compiler feststellen kann, welches Objekt verwendet wird. Die Namen selbst können jedoch lang und umständlich sein. Um dies zu umgehen, können Sie die `Imports`\-Anweisung für die Definition eines *Alias* verwenden. Diesen abgekürzten Namen können Sie anstelle eines vollqualifizierten Namens verwenden. Das folgende Codebeispiel erstellt Aliase für zwei vollqualifizierte Namen und verwendet diese Aliase zur Definition zweier Objekte.  
  
 [!code-vb[VbVbalrApplication#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_4.vb)]  
  
 [!code-vb[VbVbalrApplication#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_5.vb)]  
  
 Wenn Sie die `Imports`\-Anweisung ohne Alias verwenden, können Sie alle Namen in diesem Namespace ohne Qualifikation verwenden – vorausgesetzt, sie sind in dem Projekt eindeutig. Wenn das Projekt `Imports`\-Anweisungen für Namespaces enthält, die Elemente mit gleichem Namen enthalten, müssen Sie Namen, die Sie verwenden, vollständig qualifizieren. Nehmen wir an, das Projekt enthält die folgenden beiden `Imports`\-Anweisungen:  
  
 [!code-vb[VbVbalrApplication#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_6.vb)]  
  
 Wenn Sie versuchen, `Class1` zu verwenden ohne diesen Namen voll zu qualifizieren, meldet [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] einen Fehler, dass der Name `Class1` mehrdeutig ist.  
  
## Namespaceebenen\-Anweisungen  
 Innerhalb eines Namespace können Sie Elemente wie Module, Schnittstellen, Klassen, Delegaten, Enumerationen, Strukturen und andere Namespaces definieren. Sie können keine Elemente wie Eigenschaften, Prozeduren, Variablen und Ereignisse auf Namespaceebene definieren. Diese Elemente müssen in Containern, beispielsweise in Modulen, Strukturen oder Klassen deklariert werden.  
  
## Das Schlüsselwort „global“ in vollqualifizierten Namen  
 Wenn Sie eine geschachtelte Hierarchie aus Namespaces definiert haben, kann der Zugriff auf den <xref:System?displayProperty=fullName>\-Namespace von .NET Framework für Code innerhalb dieser Hierarchie blockiert sein. Das folgende Beispiel veranschaulicht eine Hierarchie, in der der `SpecialSpace.System`\-Namespace den Zugriff auf <xref:System?displayProperty=fullName> blockiert.  
  
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
  
 Der Visual Basic\-Compiler kann daher den Verweis auf <xref:System.Int32?displayProperty=fullName> nicht auflösen, da `SpecialSpace.System` kein `Int32` definiert. Sie können das Schlüsselwort `Global` verwenden, um die Qualifikationskette in der äußersten Ebene der .NET Framework\-Klassenbibliothek zu beginnen. Dadurch können Sie den <xref:System?displayProperty=fullName>\-Namespace oder irgendeinen anderen Namespace in der Klassenbibliothek angeben. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
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
  
 Sie können `Global` verwenden, um auf andere Namespaces auf Stammebene zuzugreifen, beispielsweise auf <xref:Microsoft.VisualBasic?displayProperty=fullName>, und auf jeden anderen Namespace, der dem Projekt zugeordnet ist.  
  
## Global\-Schlüsselwort in Namespace\-Anweisungen  
 Sie können auch das Schlüsselwort `Global` in einem [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) verwenden. Dadurch können Sie einen Namespace aus dem Stammnamespace des Projekts definieren.  
  
 Alle Namespaces im Projekt basieren auf dem Stammnamespace des Projekts.  Visual Studio weist den Projektnamen als den Standard\-Stammnamespace für den gesamten Code des Projekts zu. Wenn Ihr Projekt beispielsweise den Namen `ConsoleApplication1` hat, gehören die Programmierelemente zum Namespace `ConsoleApplication1`. Wenn Sie `Namespace Magnetosphere` deklarieren, greifen Verweise auf `Magnetosphere` im Projekt auf `ConsoleApplication1.Magnetosphere` zu.  
  
 Die folgenden Beispiele verwenden das Schlüsselwort `Global`, um einen Namespace aus dem Stammnamespace für das Projekt zu deklarieren.  
  
 [!code-vb[VbVbalrApplication#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_7.vb)]  
  
 In einer Namespace\-Deklaration kann `Global` nicht in einem anderen Namespace geschachtelt sein.  
  
 Sie können [Seite "Anwendung", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic) zum Anzeigen und Ändern des **Stammnamespace** des Projekts verwenden.  Bei neuen Projekten erhält der **Stammnamespace** standardmäßig den Namen des Projekts. Damit `Global` der Namespace der obersten Ebene ist, können Sie den **Stammnamespace**\-Eintrag löschen, so dass das Feld leer ist. Löschen des **Stammnamespace** beseitigt die Notwendigkeit des Schlüsselworts `Global` in Namespacedeklarationen.  
  
 Wenn eine `Namespace`\-Anweisung einen Namen deklariert, der auch ein Namespace in .NET Framework ist, ist der .NET Framework\-Namespace nicht mehr verfügbar, wenn das Schlüsselwort `Global` nicht in einem vollständig qualifizierten Namen verwendet wird. Um den Zugriff auf diesen .NET Framework\-Namespace ohne die Verwendung des Schlüsselworts `Global` zu aktivieren, können Sie das Schlüsselwort `Global` in die `Namespace`\-Anweisung aufnehmen.  
  
 Das folgende Beispiel enthält in der Namespacedeklaration `System.Text` das Schlüsselwort `Global`.  
  
 Wenn das Schlüsselwort `Global` nicht in der Namespacedeklaration enthalten ist, kann auf <xref:System.Text.StringBuilder> nicht zugegriffen werden, ohne dass `Global.System.Text.StringBuilder` festgelegt wird. Für ein Projekt mit dem Namen `ConsoleApplication1` greifen Verweise auf `System.Text` auf `ConsoleApplication1.System.Text` zu, wenn das Schlüsselwort `Global` nicht verwendet wurde.  
  
 [!code-vb[VbVbalrApplication#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_8.vb)]  
  
## Siehe auch  
 <xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms?displayProperty=fullName>   
 [Assemblys und der globale Assemblycache](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md)   
 [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Schreiben von Code in Office\-Projektmappen](/office-dev/office-dev/writing-code-in-office-solutions)