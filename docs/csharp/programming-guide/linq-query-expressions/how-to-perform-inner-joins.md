---
title: "Gewusst wie: Ausf&#252;hren innerer Verkn&#252;pfungen (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Innere Verknüpfungen [LINQ in C#]"
  - "Verknüpfungen [C#], Intern"
  - "Abfragen [LINQ in C#], Joins"
  - "Abfrageausdrücke [LINQ in C#], Joins"
ms.assetid: d9edb404-8314-413e-ae51-83bb86c7a4b5
caps.latest.revision: 25
caps.handback.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Ausf&#252;hren innerer Verkn&#252;pfungen (C#-Programmierhandbuch)
Bei relationalen Datenbanken erstellt ein *innerer Join* einen Ergebnissatz, in dem jedes Element der ersten Auflistung einmal für jedes übereinstimmende Element in der zweiten Auflistung angezeigt wird.  Wenn ein Element in der ersten Auflistung keine übereinstimmenden Elemente hat, wird es nicht im Ergebnissatz angezeigt.  Die <xref:System.Linq.Enumerable.Join%2A>\-Methode, die von der `join`\-Klausel in C\# aufgerufen wird, implementiert einen inneren Join.  
  
 Dieses Thema zeigt vier Variationen, wie Sie einen inneren Join ausführen können:  
  
-   Ein einfacher innerer Join, der Elemente aus zwei Datenquellen anhand eines einfachen Schlüssels verknüpft.  
  
-   Ein innerer Join, der Elemente aus zwei Datenquellen anhand eines *zusammengesetzten*  Schlüssels verknüpft.  Ein zusammengesetzter Schlüssel besteht aus mehr als einem Wert und ermöglicht es Ihnen, Elemente anhand mehr als einer Eigenschaft zu verknüpfen.  
  
-   Ein *Mehrfachjoin*, in dem aufeinander folgende Joinoperationen aneinander angefügt werden.  
  
-   Ein innerer Join, der durch einen Group Join implementiert wird.  
  
## Beispiel  
  
## Beispiel für Join mit einfachem Schlüssel  
 Im folgenden Beispiel werden zwei Auflistungen erstellt, die Objekte von zwei benutzerdefinierten Typen, `Person` und `Pet`, enthalten.  Die Abfrage verwendet die `join`\-Klausel in C\#, um die `Person`\-Objekte mit `Pet`\-Objekten abzugleichen, deren `Owner` diese `Person` ist.  Die `select`\-Klausel in C\# definiert die Darstellung der resultierenden Objekte.  In diesem Beispiel handelt es sich bei den erstellten Objekten um anonyme Typen, die aus dem Vornamen des Besitzers und dem Namen des Tiers bestehen.  
  
 [!code-cs[CsLINQProgJoining#1](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/Joins/joins.cs#1)]  
  
 Beachten Sie, dass das `Person`\-Objekt, dessen `LastName` "Huff" ist, nicht im Ergebnissatz angezeigt wird, da es kein `Pet`\-Objekt gibt, bei dem `Pet.Owner` dieser `Person` entspricht.  
  
## Beispiel  
  
## Beispiel für Join mit zusammengesetztem Schlüssel  
 Anstatt Elemente anhand nur einer Eigenschaft zu verknüpfen, können Sie mit einem zusammengesetzten Schlüssel Elemente anhand mehrerer Eigenschaften vergleichen.  Geben Sie dazu die Schlüsselauswahlfunktion für jede Auflistung an, um einen anonymen Typ zurückzugeben, der aus den Eigenschaften besteht, die Sie vergleichen möchten.  Wenn Sie die Eigenschaften beschriften, müssen sie die gleiche Bezeichnung im anonymen Typ jedes Schlüssels haben.  Die Eigenschaften müssen auch in der gleichen Reihenfolge angezeigt werden.  
  
 Im folgenden Beispiel wird mit einer Liste von `Employee`\-Objekten und einer Liste von `Student`\-Objekten festgelegt, welche Angestellten ebenfalls Studenten sind.  Beide Typen verfügen über eine `FirstName`\-Eigenschaft und eine `LastName`\-Eigenschaft des Typs <xref:System.String>.  Die Funktionen, mit denen die Joinschlüssel aus den Elementen jeder Liste erstellt werden, geben einen anonymen Typ zurück, der aus der `FirstName`\-Eigenschaft und der `LastName`\-Eigenschaft jedes Elements besteht.  Die Joinoperation vergleicht diese zusammengesetzten Schlüssel auf Gleichheit und gibt Objektpaare aus jeder Liste zurück, wenn der Vor\- und Nachname übereinstimmen.  
  
 [!code-cs[CsLINQProgJoining#2](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/Joins/joins.cs#2)]  
  
## Beispiel  
  
## Beispiel für Mehrfachjoin  
 Jede beliebige Anzahl von Joinoperationen kann aneinander angefügt werden, um einen Mehrfachjoin durchzuführen.  Jede `join`\-Klausel in C\# verknüpft eine angegebene Datenquelle mit den Ergebnissen des vorherigen Joins.  
  
 Im folgenden Beispiel werden drei Auflistungen erstellt: eine Liste mit `Person`\-Objekten, eine Liste mit `Cat`\-Objekten und eine mit `Dog`\-Objekten.  
  
 Die erste `join`\-Klausel in C\# gleicht Personen und Katzen anhand eines `Person`\-Objekts, das `Cat.Owner` entspricht, miteinander ab.  Es wird eine Sequenz anonymer Typen zurückgegeben, die das `Person`\-Objekt und `Cat.Name` enthält.  
  
 Die zweite `join`\-Klausel in C\# verknüpft die anonymen Typen, die vom ersten Join mit `Dog`\-Objekten in der angegebenen Liste mit Hunden zurückgegeben wurden, anhand eines zusammengesetzten Schlüssels, der aus der `Owner`\-Eigenschaft des Typs `Person` und dem ersten Buchstaben des Tiernamens besteht.  Es wird eine Sequenz anonymer Typen zurückgegeben, die die `Cat.Name`\-Eigenschaft und die `Dog.Name`\-Eigenschaft jedes übereinstimmenden Paars enthält.  Da es sich hierbei um einen inneren Join handelt, werden nur die Objekte aus der ersten Datenquelle, für die es eine Übereinstimmung in der zweiten Datenquelle gibt, zurückgegeben.  
  
 [!code-cs[CsLINQProgJoining#3](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/Joins/joins.cs#3)]  
  
## Beispiel  
  
## Innerer Join mithilfe des Beispiels für Group Joins  
 Im folgenden Beispiel wird gezeigt, wie Sie einen inneren Join implementieren können, indem Sie einen Group Join verwenden.  
  
 In `query1` ist die Liste der `Person`\-Objekte über einen Group Join mit der Liste der `Pet`\-Objekte verknüpft, wobei die `Person` mit der `Pet.Owner`\-Eigenschaft übereinstimmt.  Der Group Join erstellt eine Auflistung von Zwischengruppen, wobei jede Gruppe aus einem `Person`\-Objekt und einer Sequenz übereinstimmender `Pet`\-Objekte besteht.  
  
 Durch das Hinzufügen einer zweiten `from`\-Klausel zur Abfrage wird diese Sequenz mit Sequenzen zu einer längeren Sequenz zusammengefasst \(vereinfacht\).  Der Typ der Elemente der endgültigen Sequenz wird mit der `select`\-Klausel angegeben.  In diesem Beispiel ist der Typ ein anonymer Typ, der aus der `Person.FirstName`\-Eigenschaft und der `Pet.Name`\-Eigenschaft für jedes übereinstimmende Paar besteht.  
  
 Das Ergebnis von `query1` entspricht dem Resultset, das zum Ausführen eines inneren Joins mit der `join`\-Klausel ohne die `into`\-Klausel zurückgegeben wird.  Die `query2`\-Variable veranschaulicht diese entsprechende Abfrage.  
  
 [!code-cs[CsLINQProgJoining#4](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/Joins/joins.cs#4)]  
  
## Kompilieren des Codes  
  
-   Erstellen Sie ein neues Konsolenanwendungsprojekt in [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)].  
  
-   Fügen Sie einen Verweis auf System.Core.dll hinzu, wenn er noch nicht vorhanden ist.  
  
-   Schließen Sie den <xref:System.Linq>\-Namespace ein.  
  
-   Kopieren Sie den Code aus dem Beispiel, und fügen Sie ihn in die program.cs\-Datei unter der `Main`\-Methode ein.  Fügen Sie der `Main`\-Methode eine Codezeile hinzu, um die eingefügte Methode aufzurufen.  
  
-   Führen Sie das Programm aus.  
  
## Siehe auch  
 <xref:System.Linq.Enumerable.Join%2A>   
 <xref:System.Linq.Enumerable.GroupJoin%2A>   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [Gewusst wie: Ausführen von Gruppenverknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)   
 [Gewusst wie: Ausführen linker äußerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)   
 [Vorgehensweise: Verknüpfen zweier Auflistungen](../Topic/How%20to:%20Join%20Two%20Collections%20\(C%23\)%20\(LINQ%20to%20XML\).md)   
 [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)