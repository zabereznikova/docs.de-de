---
title: "Ausführen von Gruppenverknüpfungen"
description: "So führen Sie Gruppenverknüpfungen aus."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0410c5f673e61f91c00a69cb1659e0d72852f128
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="perform-grouped-joins"></a>Ausführen von Gruppenverknüpfungen

Die Gruppenverknüpfung ist nützlich für das Erstellen hierarchischer Datenstrukturen. Sie verbindet jedes Element aus der ersten Auflistung mit einem Satz von entsprechenden Elementen aus der zweiten Auflistung.  
  
 Eine Klasse oder relationale Datenbanktabelle namens `Student` kann z.B. zwei Felder enthalten: `Id` und `Name`. Eine zweite Klasse oder relationale Datenbanktabelle namens `Course` kann zwei Felder enthalten: `StudentId` und `CourseTitle`. Eine Gruppenverknüpfung dieser beiden Datenquellen, die auf der übereinstimmenden `Student.Id` und `Course.StudentId` basiert, würde jeden `Student` mit einer Auflistung von `Course`-Objekten gruppieren (die vielleicht leer sind).  
  
> [!NOTE]
>  Jedes Element der ersten Auflistung erscheint im Ergebnissatz einer Gruppenverknüpfung, unabhängig davon, ob entsprechende Elemente in der zweiten Auflistung gefunden werden. Sollten keine entsprechenden Elemente gefunden werden, ist die Sequenz der entsprechenden Elemente für das Element leer. Die Ergebnisauswahl hat daher Zugriff auf jedes Element der ersten Auflistung. Dies unterscheidet sich von der Ergebnisauswahl in einer Verknüpfung, bei der keine Gruppen verknüpft werden. Diese kann nicht auf Elemente aus der ersten Auflistung zugreifen, die keine Übereinstimmung in der zweiten Auflistung haben.  
  
 Im ersten Beispiel in diesem Thema wird das Ausführen einer Gruppenverknüpfung gezeigt. Im zweiten Beispiel wird gezeigt, wie eine Gruppenverknüpfung zum Erstellen von XML-Elementen verwendet wird.  
  
## <a name="example"></a>Beispiel  
  
### <a name="group-join-example"></a>Beispiel für eine Gruppenverknüpfung  
 Das folgende Beispiel führt eine Gruppenverknüpfung von Objekten des Typs `Person` und `Pet` aus, die auf der `Person` basiert und mit der `Pet.Owner`-Eigenschaft übereinstimmt. Bei einer Verknüpfung, bei der keine Gruppen verknüpft werden, wird für jede Übereinstimmung ein Elementpaar erzeugt. Im Gegensatz dazu erzeugt eine Gruppenverknüpfung nur ein resultierendes Objekt für jedes Element der ersten Auflistung, was in diesem Beispiel ein `Person`-Objekt ist. Die entsprechenden Elemente aus der zweiten Auflistung, die in diesem Beispiel `Pet`-Objekte sind, werden in einer Auflistung gruppiert. Die Ergebnisauswahlfunktion erstellt schließlich einen anonymen Typ für jede Übereinstimmung, die aus `Person.FirstName` und einer Auflistung von `Pet`-Objekten besteht.  
  
 [!code-cs[CsLINQProgJoining#5](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]  
  
## <a name="example"></a>Beispiel  
  
### <a name="group-join-to-create-xml-example"></a>Gruppenverknüpfung zum Erstellen eines XML-Beispiels  
 Gruppenverknüpfungen lassen sich ideal für das Erstellen von XML mithilfe von LINQ to XML nutzen. Das folgende Beispiel ähnelt dem vorherigen, nur dass die Ergebnisauswahlfunktion anstatt eines anonymen Typs XML-Elemente erstellt, die die verknüpften Objekte darstellen.  
  
 [!code-cs[CsLINQProgJoining#6](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]  
 
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.Enumerable.Join%2A>   
 <xref:System.Linq.Enumerable.GroupJoin%2A>   
 [Ausführen innerer Verknüpfungen](perform-inner-joins.md)   
 [Perform left outer joins (Ausführen von Left Outer Joins)](perform-left-outer-joins.md)   
 [Anonyme Typen](../programming-guide/classes-and-structs/anonymous-types.md)   
 

