---
title: Namespaces in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.global
dev_langs:
- VB
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names, avoiding conflicts
- naming conflicts, namespaces
- namespaces, assemblies
- Visual Basic code, namespaces
- fully qualified names
- naming conventions, naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fe94e65ddbb4ebd2f7d26e8750a0a7ef5d3153af
ms.lasthandoff: 03/13/2017

---
# <a name="namespaces-in-visual-basic"></a>Namespaces in Visual Basic
Namespaces organisieren die in einer Assembly definierten Objekte. Assemblys können mehrere Namespaces enthalten, die wiederum andere Namespaces enthalten können. Namespaces vermeiden Mehrdeutigkeit und vereinfachen Verweise, wenn Sie große Gruppen von Objekten verwenden, zum Beispiel Klassenbibliotheken.  
  
 Zum Beispiel die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] definiert die <xref:System.Windows.Forms.ListBox>-Klasse in die <xref:System.Windows.Forms?displayProperty=fullName>Namespace.</xref:System.Windows.Forms?displayProperty=fullName> </xref:System.Windows.Forms.ListBox> Das folgende Codefragment zeigt, wie eine Variable mit dem vollqualifizierten Namen für diese Klasse deklariert wird:  
  
 [!code-vb[VbVbalrApplication&6;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_1.vb)]  
  
## <a name="avoiding-name-collisions"></a>Vermeiden von Namenskonflikten  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]Namespaces beheben ein Problems bezeichnet *Namespacekonflikte*, in denen der Entwickler einer Klassenbibliothek durch die Verwendung ähnlicher Namen in einer anderen Bibliothek gestört wird. Diese Konflikte mit vorhandenen Komponenten werden auch als *Namenskonflikte*bezeichnet.  
  
 Angenommen, Sie erstellen eine neue Klasse namens `ListBox`, können Sie sie innerhalb des Projekts ohne Qualifikation verwenden. Allerdings sollten Sie verwenden die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.Windows.Forms.ListBox>Klasse im gleichen Projekt müssen Sie einen vollqualifizierten Verweis verwenden, um den Verweis eindeutig zu machen.</xref:System.Windows.Forms.ListBox> Wenn der Verweis nicht eindeutig ist, meldet [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] einen Fehler, dass der Name mehrdeutig ist. Im folgenden Codebeispiel wird die Deklaration dieser Objekte veranschaulicht:  
  
 [!code-vb[VbVbalrApplication&#7;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_2.vb)]  
  
 Die folgende Abbildung zeigt zwei Namespacehierarchien, beide mit einem Objekt mit dem Namen `ListBox`.  
  
 ![Namespace-Hierarchie](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.gif "VaNamespaceHierarchy")  
  
 Standardmäßig enthält jede mit [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erstellte ausführbare Datei einen Namespace mit demselben Namen wie für das Projekt. Wenn Sie zum Beispiel ein Objekt in einem Projekt mit dem Namen `ListBoxProject`definieren, enthält die ausführbare Datei ListBoxProject.exe einen Namespace mit dem Namen `ListBoxProject`.  
  
 Mehrere Assemblys können den gleichen Namen verwenden. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] behandelt sie als einen einzigen Satz von Namen. Zum Beispiel können Sie Klassen für einen Namespace mit dem Namen `SomeNameSpace` in einer Assembly mit dem Namen `Assemb1` definieren, und zusätzliche Klassen für den gleichen Namespace in einer Assembly mit dem Namen `Assemb2`.  
  
## <a name="fully-qualified-names"></a>Vollqualifizierte Namen  
 Vollqualifizierte Namen sind Objektverweise, denen der Name des Namespace vorangestellt ist, in dem das Objekt definiert ist. Sie können in anderen Projekten definierte Objekte verwenden, wenn Sie einen Verweis auf die Klasse erstellen (durch Auswahl von **Verweis hinzufügen** aus dem Menü **Projekt** ) und dann den vollqualifizierten Namen für das Objekt im Code verwenden. Das folgende Codefragment zeigt, wie Sie den vollqualifizierten Namen für ein Objekt aus dem Namespace eines anderen Projekts verwenden:  
  
 [!code-vb[VbVbalrApplication&#8;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_3.vb)]  
  
 Durch vollqualifizierte Namen werden Namenskonflikte vermieden, da der Compiler feststellen kann, welches Objekt verwendet wird. Die Namen selbst können jedoch lang und umständlich sein. Um dies zu umgehen, können Sie die `Imports` -Anweisung für die Definition eines *Alias*verwenden. Diesen abgekürzten Namen können Sie anstelle eines vollqualifizierten Namens verwenden. Das folgende Codebeispiel erstellt Aliase für zwei vollqualifizierte Namen und verwendet diese Aliase zur Definition zweier Objekte.  
  
 [!code-vb[VbVbalrApplication&#9;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_4.vb)]  
  
 [!code-vb[VbVbalrApplication&#10;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_5.vb)]  
  
 Wenn Sie die `Imports` -Anweisung ohne Alias verwenden, können Sie alle Namen in diesem Namespace ohne Qualifikation verwenden – vorausgesetzt, sie sind in dem Projekt eindeutig. Wenn das Projekt `Imports` -Anweisungen für Namespaces enthält, die Elemente mit gleichem Namen enthalten, müssen Sie Namen, die Sie verwenden, vollständig qualifizieren. Nehmen wir an, das Projekt enthält die folgenden beiden `Imports` -Anweisungen:  
  
 [!code-vb[VbVbalrApplication&#11;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_6.vb)]  
  
 Wenn Sie versuchen, `Class1` zu verwenden ohne diesen Namen voll zu qualifizieren, meldet [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] einen Fehler, dass der Name `Class1` mehrdeutig ist.  
  
## <a name="namespace-level-statements"></a>Namespaceebenen-Anweisungen  
 Innerhalb eines Namespace können Sie Elemente wie Module, Schnittstellen, Klassen, Delegaten, Enumerationen, Strukturen und andere Namespaces definieren. Sie können keine Elemente wie Eigenschaften, Prozeduren, Variablen und Ereignisse auf Namespaceebene definieren. Diese Elemente müssen in Containern, beispielsweise in Modulen, Strukturen oder Klassen deklariert werden.  
  
## <a name="global-keyword-in-fully-qualified-names"></a>Das Schlüsselwort „global“ in vollqualifizierten Namen  
 Wenn Sie eine geschachtelte Hierarchie aus Namespaces definiert haben, Code innerhalb dieser Hierarchie möglicherweise blockiert den Zugriff auf die <xref:System?displayProperty=fullName>-Namespace von .NET Framework.</xref:System?displayProperty=fullName> Das folgende Beispiel veranschaulicht eine Hierarchie, in der die `SpecialSpace.System` Namespace blockiert den Zugriff auf <xref:System?displayProperty=fullName>.</xref:System?displayProperty=fullName>  
  
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
  
 Visual Basic-Compiler nicht daher auflösen den Verweis auf <xref:System.Int32?displayProperty=fullName>, da `SpecialSpace.System` definiert keine `Int32`.</xref:System.Int32?displayProperty=fullName> Sie können das Schlüsselwort `Global` verwenden, um die Qualifikationskette in der äußersten Ebene der .NET Framework-Klassenbibliothek zu beginnen. Dadurch können Sie angeben, die <xref:System?displayProperty=fullName>Namespace oder irgendeinen anderen Namespace in der Klassenbibliothek.</xref:System?displayProperty=fullName> Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
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
  
 Sie können `Global` andere Namespaces auf Stammebene, z. B. Zugriff auf <xref:Microsoft.VisualBasic?displayProperty=fullName>, und jeden Namespace, der dem Projekt zugeordnet.</xref:Microsoft.VisualBasic?displayProperty=fullName>  
  
## <a name="global-keyword-in-namespace-statements"></a>Global-Schlüsselwort in Namespace-Anweisungen  
 Sie können auch die `Global` -Schlüsselwort in einer [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md). Dadurch können Sie einen Namespace aus dem Stammnamespace des Projekts definieren.  
  
 Alle Namespaces im Projekt basieren auf dem Stammnamespace des Projekts.  Visual Studio weist den Projektnamen als den Standard-Stammnamespace für den gesamten Code des Projekts zu. Wenn Ihr Projekt beispielsweise den Namen `ConsoleApplication1`hat, gehören die Programmierelemente zum Namespace `ConsoleApplication1`. Wenn Sie `Namespace Magnetosphere`deklarieren, greifen Verweise auf `Magnetosphere` im Projekt auf `ConsoleApplication1.Magnetosphere`zu.  
  
 Die folgenden Beispiele verwenden das Schlüsselwort `Global` , um einen Namespace aus dem Stammnamespace für das Projekt zu deklarieren.  
  
 [!code-vb[VbVbalrApplication&#22;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_7.vb)]  
  
 In einer Namespace-Deklaration kann `Global` nicht in einem anderen Namespace geschachtelt sein.  
  
 Können Sie die [Anwendungsseite, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) anzeigen und Ändern der **Stamm-Namespace** des Projekts.  Bei neuen Projekten erhält der **Stammnamespace** standardmäßig den Namen des Projekts. Damit `Global` der Namespace der obersten Ebene ist, können Sie den **Stammnamespace** -Eintrag löschen, so dass das Feld leer ist. Löschen des **Stammnamespace** beseitigt die Notwendigkeit des Schlüsselworts `Global` in Namespacedeklarationen.  
  
 Wenn eine `Namespace` -Anweisung einen Namen deklariert, der auch ein Namespace in .NET Framework ist, ist der .NET Framework-Namespace nicht mehr verfügbar, wenn das Schlüsselwort `Global` nicht in einem vollständig qualifizierten Namen verwendet wird. Um den Zugriff auf diesen .NET Framework-Namespace ohne die Verwendung des Schlüsselworts `Global` zu aktivieren, können Sie das Schlüsselwort `Global` in die `Namespace` -Anweisung aufnehmen.  
  
 Das folgende Beispiel enthält in der Namespacedeklaration `Global` das Schlüsselwort `System.Text` .  
  
 Wenn die `Global` Schlüsselwort ist nicht vorhanden, in der Namespacedeklaration <xref:System.Text.StringBuilder>konnte nicht zugegriffen werden, ohne dass `Global.System.Text.StringBuilder`.</xref:System.Text.StringBuilder> Für ein Projekt mit dem Namen `ConsoleApplication1`greifen Verweise auf `System.Text` auf `ConsoleApplication1.System.Text` zu, wenn das Schlüsselwort `Global` nicht verwendet wurde.  
  
 [!code-vb[VbVbalrApplication&21;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_8.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ListBox></xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms?displayProperty=fullName></xref:System.Windows.Forms?displayProperty=fullName>   
 [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)   
 [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Schreiben von Code in Office-Projektmappen](https://msdn.microsoft.com/library/bb608596)
