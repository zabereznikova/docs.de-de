---
title: 'Vorgehensweise: Verwenden von Ausdrucksbaumstrukturen zum Erstellen dynamischer Abfragen (C#) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 52cd44dd-a3ec-441e-b93a-4eca388119c7
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7de999848870de80996f308affde088088e32e52
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-c"></a>Vorgehensweise: Verwenden von Ausdrucksbaumstrukturen zum Erstellen dynamischer Abfragen (C#)
Ausdrucksbaumstrukturen werden in LINQ dazu verwendet, strukturierte Abfragen für Datenquellen zu repräsentieren, die <xref:System.Linq.IQueryable%601> implementieren. Der LINQ-Anbieter implementiert z.B. die <xref:System.Linq.IQueryable%601>-Schnittstelle, um relationale Datenspeicher abzufragen. Die Compiler für C# kompilieren Abfragen solcher Datenquellen in Code, der zur Laufzeit eine Ausdrucksbaumstruktur erzeugt. Anschließend kann der Abfrageanbieter die Datenstruktur der Ausdrucksbaumstruktur durchlaufen und in eine für die Datenquelle geeignete Abfragesprache übersetzen.  
  
 Ausdrucksbaumstrukturen werden in LINQ außerdem dazu verwendet, Lambdaausdrücke zu repräsentieren, die Variablen den Typs <xref:System.Linq.Expressions.Expression%601> zugewiesen sind.  
  
 In diesem Thema wird erläutert, wie Sie Ausdrucksbaumstrukturen verwenden können, um dynamische LINQ-Abfragen zu erstellen. Dynamische Abfragen sind nützlich, wenn die Eigenschaften einer Abfrage zur Kompilierzeit nicht bekannt sind. Beispielsweise kann eine Anwendung über eine Benutzeroberfläche verfügen, in der der Endbenutzer ein oder mehrere Prädikate zum Filtern der Daten angeben kann. Damit LINQ für Abfragen verwendet werden kann, muss solch eine Anwendung Ausdrucksbaumstrukturen benutzen, um die LINQ-Abfrage zur Laufzeit zu erstellen.  
  
## <a name="example"></a>Beispiel  
 In folgendem Beispiel erfahren Sie, wie Sie Ausdrucksbaumstrukturen zur Konstruktion einer Abfrage anhand einer `IQueryable`-Datenquelle verwenden und diese anschließend ausführen können. Im Code wird eine Ausdrucksbaumstruktur erstellt, welche die folgende Abfrage darstellt:  
  
 `companies.Where(company => (company.ToLower() == "coho winery" || company.Length > 16)).OrderBy(company => company)`  
  
 Die Factorymethoden im <xref:System.Linq.Expressions>-Namespace werden zum Erstellen von Ausdrucksbaumstrukturen verwendet, die Ausdrücke repräsentieren, aus denen die Abfrage besteht. Die Ausdrücke, die Aufrufe an die Methoden des Standardabfrageoperators repräsentieren, verweisen auf die <xref:System.Linq.Queryable>-Implementierung dieser Methoden. Die letzte Ausdrucksbaumstruktur wird an die <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29>-Implementierung des Anbieters der `IQueryable`-Datenquelle übergeben, um eine ausführbare Abfrage des Typs `IQueryable` zu erstellen. Sie erhalten die Ergebnisse via Zugriff auf die Auflistung der Abfrageergebnisse.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 In diesem Code wird in dem an die `Queryable.Where`-Methode übergebenen Prädikat eine feste Anzahl von Ausdrücken verwendet. Sie können allerdings eine Anwendung schreiben, die eine variable Zahl von Prädikatausdrücken miteinander vereint; diese Zahl ist von der Benutzereingabe abhängig. Sie können auch die Standardabfrageoperatoren variieren, die in der Abfrage aufgerufen werden; dies ist ebenfalls von der Benutzereingabe abhängig.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Erstellen Sie ein neues **Konsolenanwendungsprojekt**.  
  
-   Fügen Sie einen Verweis auf „System.Core.dll“ hinzu, wenn nicht bereits darauf verwiesen wird.  
  
-   Binden Sie den System.Linq.Expressions-Namespace ein.  
  
-   Kopieren Sie den Code aus dem ersten Beispiel, und fügen Sie ihn in die `Main`-Methode ein.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrucksbaumstrukturen (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)   
 [Vorgehensweise: Ausführen von Ausdrucksbaumstrukturen (C#)](../../../../csharp/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)   
 [Gewusst wie: Dynamisches Festlegen von Prädikatfiltern zur Laufzeit](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)
