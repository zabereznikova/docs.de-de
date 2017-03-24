---
title: 'Gewusst wie: Verwenden von Ausdrucksbaumstrukturen zum Erstellen dynamischer Abfragen (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8d69be78a9f3568535dffe54e21af80c6eb12f70
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-visual-basic"></a>Gewusst wie: Verwenden von Ausdrucksbaumstrukturen zum Erstellen dynamischer Abfragen (Visual Basic)
In LINQ sind Ausdrucksbaumstrukturen strukturierten Abfragen dieses Ziel Datenquellen dar, die implementieren <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> verwendet. Angenommen, der LINQ-Anbieter implementiert die <xref:System.Linq.IQueryable%601>-Schnittstelle für das Abfragen relationaler Datenspeicher.</xref:System.Linq.IQueryable%601> Visual Basic-Compiler kompiliert, Abfragen, die diese Datenquellen in Code zu verwenden, die zur Laufzeit eine Ausdrucksbaumstruktur erstellt wird. Der Abfrageanbieter kann die Datenstruktur des Ausdruck-Struktur durchlaufen und in eine Abfragesprache entsprechend für die Datenquelle zu übersetzen.  
  
 Ausdrucksbaumstrukturen werden auch in LINQ verwendet, Lambda-Ausdrücke dar, die Variablen des Typs <xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601> zugewiesen sind  
  
 Dieses Thema beschreibt, wie Sie Ausdrucksbaumstrukturen dynamische LINQ-Abfragen erstellen. Dynamische Abfragen sind nützlich, wenn die Einzelheiten einer Abfrage zur Kompilierzeit nicht bekannt sind. Beispielsweise kann eine Anwendung eine Benutzeroberfläche bereitstellen, mit der der Endbenutzer eines oder mehrere Prädikate zum Filtern der Daten festlegen können. LINQ für Abfragen verwenden möchten, muss dieser Anwendungstyp Ausdrucksbaumstrukturen verwenden, die LINQ-Abfrage zur Laufzeit erstellt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Ausdrucksbaumstrukturen verwenden, erstellen Sie eine Abfrage für ein `IQueryable` Datenquelle und dann ausgeführt wird. Der Code erstellt eine Ausdrucksbaumstruktur, um die Darstellung der folgenden Abfrage:  
  
 `companies.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16).OrderBy(Function(company) company)`  
  
 Die Methoden in der <xref:System.Linq.Expressions>Namespace werden zum Erstellen von Ausdrucksbaumstrukturen, die die Ausdrücke darstellen, aus denen die gesamte Abfrage zusammensetzt.</xref:System.Linq.Expressions> Die Ausdrücke, die Aufrufe an die Standardabfrageoperator-Methoden darstellen, finden Sie in der <xref:System.Linq.Queryable>Implementierungen dieser Methoden.</xref:System.Linq.Queryable> Die endgültige Ausdrucksbaumstruktur wird zum Übergeben der <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29>Implementierung des Anbieters von den `IQueryable` -Datenquelle, um eine ausführbare Abfrage vom Typ erstellen `IQueryable`.</xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> Die Ergebnisse werden abgerufen, indem diese Abfragevariable aufgelistet.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Dieser Code verwendet eine feste Anzahl von Ausdrücken in das Prädikat, das an die `Queryable.Where` Methode. Allerdings können Sie eine Anwendung schreiben, die eine Variable Anzahl von Prädikatausdrücken kombiniert, die von der Benutzereingabe abhängig ist. Sie können auch die Standardabfrageoperatoren variieren, die in der Abfrage abhängig von der Eingabe vom Benutzer aufgerufen werden.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Erstellen Sie ein neues **Konsolenanwendung** Projekt.  
  
-   Fügen Sie einen Verweis auf System.Core.dll hinzu, wenn es nicht bereits verwiesen wird.  
  
-   Schließen Sie den System.Linq.Expressions-Namespace.  
  
-   Kopieren Sie den Code aus dem Beispiel, und fügen Sie ihn in die `Main` `Sub` Verfahren.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)   
 [Gewusst wie: Ausführen von Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
