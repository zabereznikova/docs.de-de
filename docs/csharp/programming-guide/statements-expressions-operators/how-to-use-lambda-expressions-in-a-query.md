---
title: 'Vorgehensweise: Verwenden von Lambdaausdrücken in einer Abfrage – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
ms.openlocfilehash: e7e7da211599b5ce0263377ecaf25b404399ce9c
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423168"
---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a>Vorgehensweise: Verwenden von Lambdaausdrücken in einer Abfrage (C#-Programmierhandbuch)
Sie können Lambdaausdrücke nicht direkt in der Abfragesyntax verwenden, sondern nur in Methodenaufrufen. Abfrageausdrücke können Methodenaufrufe enthalten. Einige Abfragevorgänge können nur in Methodensyntax ausgedrückt werden. Weitere Informationen zu den Unterschieden zwischen Abfragesyntax und Methodensyntax finden Sie unter [Abfragesyntax und Methodensyntax in LINQ](../concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie Lambdaausdrücke in methodenbasierten Abfragen mithilfe des Standardabfrageoperators <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> verwenden können. Bitte beachten Sie, dass die Methode <xref:System.Linq.Enumerable.Where%2A> in diesem Beispiel einen Eingabeparameter des Delegattyps <xref:System.Func%602> aufweist und dass dieser Delegat eine Ganzzahl als Eingabe akzeptiert und einen booleschen Wert zurückgibt. Der Lambdaausdruck kann in diesen Delegat konvertiert werden. Wenn dies eine [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]-Abfrage wäre, die die Methode <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType> verwendet, wäre der Parametertyp `Expression<Func<int,bool>>`, aber der Lambdaausdruck wäre der gleiche. Weitere Informationen zum Ausdruckstyp finden Sie unter <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideLINQ#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#1)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie Lambdaausdrücke in einem Methodenaufruf eines Abfrageausdrucks verwenden können. Der Lambdaausdruck ist erforderlich, da der Standardabfrageoperator <xref:System.Linq.Enumerable.Sum%2A> nicht durch Abfragesyntax aufgerufen werden kann.  
  
 Die Abfrage gruppiert die Studenten zunächst anhand ihres Jahrs wie in der `GradeLevel`-Enumeration definiert. Dann fügt sie die Gesamtergebnisse jedes Studenten in jeder Gruppe hinzu. Dazu sind zwei `Sum`-Operationen erforderlich. Mit der inneren `Sum`-Operation wird das Gesamtergebnis für jeden Studenten berechnet, und mit der äußeren `Sum`-Operation wird eine kombinierte laufende Summe für alle Studenten in der Gruppe berechnet.  
  
 [!code-csharp[csProgGuideLINQ#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#2)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um diesen Code auszuführen, kopieren Sie die Methode, fügen Sie sie in die `StudentClass` ein, die in [Vorgehensweise: Abfragen einer Auflistung von Objekten](../../linq/query-a-collection-of-objects.md) bereitgestellt wird, und rufen Sie sie von der `Main`-Methode auf.  
  
## <a name="see-also"></a>Siehe auch

- [Lambda-Ausdrücke](./lambda-expressions.md)
- [Ausdrucksbaumstrukturen (C#)](../concepts/expression-trees/index.md)
