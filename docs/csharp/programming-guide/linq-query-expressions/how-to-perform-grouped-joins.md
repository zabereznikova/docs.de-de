---
title: "Gewusst wie: Ausf&#252;hren von Gruppenverkn&#252;pfungen (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Gruppenverknüpfungen [LINQ in C#]"
  - "Verknüpfungen [C#], Gruppe"
  - "Abfragen [LINQ in C#], Joins"
  - "Abfrageausdrücke [LINQ in C#], Joins"
ms.assetid: 31b654c0-77ac-43fa-be11-aa38e14cae2d
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Ausf&#252;hren von Gruppenverkn&#252;pfungen (C#-Programmierhandbuch)
Der Group Join ist nützlich, um hierarchische Datenstrukturen zu erzeugen.  Sie weist jedem Element aus der ersten Auflistung einen Satz korrelierter Elemente aus der zweiten Auflistung zu.  
  
 Eine Klasse oder eine relationale Datenbanktabelle mit dem Namen Student könnte beispielsweise zwei Felder enthalten: Id und Name.  Eine zweite Klasse oder eine relationale Datenbanktabelle mit dem Namen Course könnte zwei Felder enthalten: StudentId und CourseTitle.  Bei einem Group Join dieser beiden Datenquellen anhand von übereinstimmender Student.Id und Course.StudentId würde jeder Student mit einer Auflistung von Course\-Objekten \(die leer sein können\) gruppiert werden.  
  
> [!NOTE]
>  Jedes Element der ersten Auflistung wird im Ergebnissatz eines Group Joins angezeigt, unabhängig davon, ob korrelierte Elemente in der zweiten Auflistung gefunden werden.  Wenn keine korrelierten Elemente gefunden werden, ist die Sequenz von korrelierten Elementen für dieses Element leer.  Die Ergebnisauswahl hat daher Zugriff auf jedes Element der ersten Auflistung.  Darin unterscheidet es sich von der Ergebnisauswahl in einem Nicht\-Group Join, der keinen Zugriff auf Elemente der ersten Auflistung hat, für die es keine Übereinstimmung in der zweiten Auflistung gibt.  
  
 Das erste Beispiel in diesem Thema zeigt, wie ein Group Join ausgeführt wird.  Im zweiten Beispiel wird Ihnen gezeigt, wie ein Group Join verwendet wird, um XML\-Elemente zu erstellen.  
  
## Beispiel  
  
### Beispiel für Group Join  
 Im folgenden Beispiel wird ein Group Join von Objekten des Typs `Person` und `Pet` basierend auf der `Person`, die mit der `Pet.Owner`\-Eigenschaft übereinstimmt, durchgeführt.  Anders als bei einem Nicht\-Group Join, bei dem ein Elementenpaar für jede Übereinstimmung erzeugt werden würde, erstellt der Group Join nur ein Objekt für jedes Element der ersten Auflistung, in diesem Beispiel ein `Person`\-Objekt.  Die entsprechenden Elemente aus der zweiten Auflistung, bei denen es sich in diesem Beispiel um `Pet`\-Objekte handelt, werden in einer Auflistung gruppiert.  Die Ergebnisauswahlfunktion erstellt dann einen anonymen Typ für jede Übereinstimmung, der aus `Person.FirstName` und einer Auflistung von `Pet`\-Objekten besteht.  
  
 [!code-cs[CsLINQProgJoining#5](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/Joins/joins.cs#5)]  
  
## Beispiel  
  
### Beispiel für einen Group Join zum Erstellen von XML  
 Group Joins sind ideal zum Erstellen von XML mit [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  Das folgende Beispiel ähnelt dem vorherigen Beispiel mit der Ausnahme, dass die Ergebnisauswahlfunktion XML\-Elemente anstelle eines anonymen Typs erstellt, die die verknüpften Objekte darstellen.  Weitere Informationen über [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] finden Sie unter [LINQ to XML](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).  
  
 [!code-cs[CsLINQProgJoining#6](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/Joins/joins.cs#6)]  
  
## Kompilieren des Codes  
  
-   Erstellen Sie ein neues **Konsolenanwendungsprojekt** in [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)].  
  
-   Fügen Sie einen Verweis auf System.Core.dll und System.Xml.Linq.dll hinzu, wenn nicht bereits auf sie verwiesen wird.  
  
-   Fügen Sie den <xref:System.Linq>\-Namespace und den <xref:System.Xml.Linq>\-Namespace hinzu.  
  
-   Kopieren Sie den Code aus dem Beispiel, und fügen Sie ihn in die program.cs\-Datei unter der `Main`\-Methode ein.  Fügen Sie der `Main`\-Methode eine Codezeile hinzu, um die eingefügte Methode aufzurufen.  
  
-   Führen Sie das Programm aus.  
  
## Siehe auch  
 <xref:System.Linq.Enumerable.Join%2A>   
 <xref:System.Linq.Enumerable.GroupJoin%2A>   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [Gewusst wie: Ausführen innerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [Gewusst wie: Ausführen linker äußerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)   
 [LINQ to XML](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)   
 [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)