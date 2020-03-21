---
title: Namespaces
ms.date: 07/20/2015
f1_keywords:
- vb.global
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names [Visual Basic], avoiding conflicts
- naming conflicts [Visual Basic], namespaces
- namespaces [Visual Basic], assemblies
- Visual Basic code, namespaces
- fully qualified names [Visual Basic]
- naming conventions [Visual Basic], naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
ms.openlocfilehash: ec892167f30a7ded739dc188ab4096cb3a5d154c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401292"
---
# <a name="namespaces-in-visual-basic"></a>Namespaces in Visual Basic
Namespaces organisieren die in einer Assembly definierten Objekte. Assemblys können mehrere Namespaces enthalten, die wiederum andere Namespaces enthalten können. Namespaces vermeiden Mehrdeutigkeit und vereinfachen Verweise, wenn Sie große Gruppen von Objekten verwenden, zum Beispiel Klassenbibliotheken.  
  
 Beispielsweise definiert .NET Framework die <xref:System.Windows.Forms.ListBox> Klasse <xref:System.Windows.Forms?displayProperty=nameWithType> im Namespace. Das folgende Codefragment zeigt, wie eine Variable mit dem vollqualifizierten Namen für diese Klasse deklariert wird:  
  
 [!code-vb[VbVbalrApplication#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#6)]  
  
## <a name="avoiding-name-collisions"></a>Vermeiden von Namenskonflikten  
 .NET Framework-Namespaces beheben ein Problem, das manchmal als *Namespace-Verschmutzung*bezeichnet wird, bei dem der Entwickler einer Klassenbibliothek durch die Verwendung ähnlicher Namen in einer anderen Bibliothek behindert wird. Diese Konflikte mit vorhandenen Komponenten werden auch als *Namenskonflikte*bezeichnet.  
  
 Angenommen, Sie erstellen eine neue Klasse namens `ListBox`, können Sie sie innerhalb des Projekts ohne Qualifikation verwenden. Wenn Sie jedoch die .NET <xref:System.Windows.Forms.ListBox> Framework-Klasse im selben Projekt verwenden möchten, müssen Sie einen vollqualifizierten Verweis verwenden, um den Verweis eindeutig zu machen. Wenn der Verweis nicht eindeutig ist, erzeugt Visual Basic einen Fehler, der besagt, dass der Name mehrdeutig ist. Im folgenden Codebeispiel wird die Deklaration dieser Objekte veranschaulicht:  
  
 [!code-vb[VbVbalrApplication#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#7)]  
  
 Die folgende Abbildung zeigt zwei Namespacehierarchien, `ListBox`die beide ein Objekt mit dem Namen enthalten:  
  
 ![Screenshot, der zwei Namespacehierarchien zeigt.](./media/namespaces/visual-basic-namespace-hierarchy.gif)  
  
 Standardmäßig enthält jede ausführbare Datei, die Sie mit Visual Basic erstellen, einen Namespace mit demselben Namen wie Ihr Projekt. Wenn Sie zum Beispiel ein Objekt in einem Projekt mit dem Namen `ListBoxProject`definieren, enthält die ausführbare Datei ListBoxProject.exe einen Namespace mit dem Namen `ListBoxProject`.  
  
 Mehrere Assemblys können den gleichen Namen verwenden. Visual Basic behandelt sie als einen einzigen Satz von Namen. Zum Beispiel können Sie Klassen für einen Namespace mit dem Namen `SomeNameSpace` in einer Assembly mit dem Namen `Assemb1`definieren, und zusätzliche Klassen für den gleichen Namespace in einer Assembly mit dem Namen `Assemb2`.  
  
## <a name="fully-qualified-names"></a>Vollqualifizierte Namen  
 Vollqualifizierte Namen sind Objektverweise, denen der Name des Namespace vorangestellt ist, in dem das Objekt definiert ist. Sie können in anderen Projekten definierte Objekte verwenden, wenn Sie einen Verweis auf die Klasse erstellen (durch Auswahl von **Verweis hinzufügen** aus dem Menü **Projekt** ) und dann den vollqualifizierten Namen für das Objekt im Code verwenden. Das folgende Codefragment zeigt, wie Sie den vollqualifizierten Namen für ein Objekt aus dem Namespace eines anderen Projekts verwenden:  
  
 [!code-vb[VbVbalrApplication#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#8)]  
  
 Durch vollqualifizierte Namen werden Namenskonflikte vermieden, da der Compiler feststellen kann, welches Objekt verwendet wird. Die Namen selbst können jedoch lang und umständlich sein. Um dies zu umgehen, können Sie die `Imports` -Anweisung für die Definition eines *Alias*verwenden. Diesen abgekürzten Namen können Sie anstelle eines vollqualifizierten Namens verwenden. Das folgende Codebeispiel erstellt Aliase für zwei vollqualifizierte Namen und verwendet diese Aliase zur Definition zweier Objekte.  
  
 [!code-vb[VbVbalrApplication#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#9)]  
  
 [!code-vb[VbVbalrApplication#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#10)]  
  
 Wenn Sie die `Imports` -Anweisung ohne Alias verwenden, können Sie alle Namen in diesem Namespace ohne Qualifikation verwenden – vorausgesetzt, sie sind in dem Projekt eindeutig. Wenn das Projekt `Imports` -Anweisungen für Namespaces enthält, die Elemente mit gleichem Namen enthalten, müssen Sie Namen, die Sie verwenden, vollständig qualifizieren. Nehmen wir an, das Projekt enthält die folgenden beiden `Imports` -Anweisungen:  
  
 [!code-vb[VbVbalrApplication#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#11)]  
  
 Wenn Sie versuchen, sie zu verwenden, `Class1` ohne sie vollständig `Class1` zu qualifizieren, erzeugt Visual Basic einen Fehler, der besagt, dass der Name mehrdeutig ist.  
  
## <a name="namespace-level-statements"></a>Namespaceebenen-Anweisungen  
 Innerhalb eines Namespace können Sie Elemente wie Module, Schnittstellen, Klassen, Delegaten, Enumerationen, Strukturen und andere Namespaces definieren. Sie können keine Elemente wie Eigenschaften, Prozeduren, Variablen und Ereignisse auf Namespaceebene definieren. Diese Elemente müssen in Containern, beispielsweise in Modulen, Strukturen oder Klassen deklariert werden.  
  
## <a name="global-keyword-in-fully-qualified-names"></a>Das Schlüsselwort „global“ in vollqualifizierten Namen  
 Wenn Sie eine geschachtelte Hierarchie aus Namespaces definiert haben, kann der Zugriff auf den <xref:System?displayProperty=nameWithType> -Namespace von .NET Framework für Code innerhalb dieser Hierarchie blockiert sein. Das folgende Beispiel veranschaulicht eine Hierarchie, in der der `SpecialSpace.System` -Namespace den Zugriff auf <xref:System?displayProperty=nameWithType>blockiert.  
  
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
  
 Der Visual Basic-Compiler kann daher den Verweis auf <xref:System.Int32?displayProperty=nameWithType>nicht auflösen, da `SpecialSpace.System` kein `Int32`definiert. Sie können das Schlüsselwort `Global` verwenden, um die Qualifikationskette in der äußersten Ebene der .NET Framework-Klassenbibliothek zu beginnen. Dadurch können Sie den <xref:System?displayProperty=nameWithType> -Namespace oder irgendeinen anderen Namespace in der Klassenbibliothek angeben. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
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
  
 Sie können `Global` verwenden, um auf andere Namespaces auf Stammebene zuzugreifen, beispielsweise auf <xref:Microsoft.VisualBasic?displayProperty=nameWithType>, und auf jeden anderen Namespace, der dem Projekt zugeordnet ist.  
  
## <a name="global-keyword-in-namespace-statements"></a>Global-Schlüsselwort in Namespace-Anweisungen  
 Sie können auch das Schlüsselwort `Global` in einem [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md)bezeichnet. Dadurch können Sie einen Namespace aus dem Stammnamespace des Projekts definieren.  
  
 Alle Namespaces im Projekt basieren auf dem Stammnamespace des Projekts.  Visual Studio weist den Projektnamen als den Standard-Stammnamespace für den gesamten Code des Projekts zu. Wenn Ihr Projekt beispielsweise den Namen `ConsoleApplication1`hat, gehören die Programmierelemente zum Namespace `ConsoleApplication1`. Wenn Sie `Namespace Magnetosphere`deklarieren, greifen Verweise auf `Magnetosphere` im Projekt auf `ConsoleApplication1.Magnetosphere`zu.  
  
 Die folgenden Beispiele verwenden das Schlüsselwort `Global` , um einen Namespace aus dem Stammnamespace für das Projekt zu deklarieren.  
  
 [!code-vb[VbVbalrApplication#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/module1.vb#22)]  
  
 In einer Namespace-Deklaration kann `Global` nicht in einem anderen Namespace geschachtelt sein.  
  
 Sie können [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) zum Anzeigen und Ändern des **Stammnamespace** des Projekts verwenden.  Bei neuen Projekten erhält der **Stammnamespace** standardmäßig den Namen des Projekts. Damit `Global` der Namespace der obersten Ebene ist, können Sie den **Stammnamespace** -Eintrag löschen, so dass das Feld leer ist. Löschen des **Stammnamespace** beseitigt die Notwendigkeit des Schlüsselworts `Global` in Namespacedeklarationen.  
  
 Wenn eine `Namespace` -Anweisung einen Namen deklariert, der auch ein Namespace in .NET Framework ist, ist der .NET Framework-Namespace nicht mehr verfügbar, wenn das Schlüsselwort `Global` nicht in einem vollständig qualifizierten Namen verwendet wird. Um den Zugriff auf diesen .NET Framework-Namespace ohne die Verwendung des Schlüsselworts `Global` zu aktivieren, können Sie das Schlüsselwort `Global` in die `Namespace` -Anweisung aufnehmen.  
  
 Das folgende Beispiel enthält in der Namespacedeklaration `Global` das Schlüsselwort `System.Text` .  
  
 Wenn das Schlüsselwort `Global` nicht in der Namespacedeklaration enthalten ist, kann auf <xref:System.Text.StringBuilder> nicht zugegriffen werden, ohne dass `Global.System.Text.StringBuilder`festgelegt wird. Für ein Projekt mit dem Namen `ConsoleApplication1`greifen Verweise auf `System.Text` auf `ConsoleApplication1.System.Text` zu, wenn das Schlüsselwort `Global` nicht verwendet wurde.  
  
 [!code-vb[VbVbalrApplication#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/module1.vb#21)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms?displayProperty=nameWithType>
- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Verweise und die Imports-Anweisung](references-and-the-imports-statement.md)
- [Imports-Anweisung (.NET-Namespace und -Typ)](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Schreiben von Code in Office-Projektmappen](/visualstudio/vsto/writing-code-in-office-solutions)
