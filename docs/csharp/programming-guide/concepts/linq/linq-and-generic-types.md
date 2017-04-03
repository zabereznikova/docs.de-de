---
title: LINQ und generische Typen (C#) | Microsoft-Dokumentation
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
helpviewer_keywords:
- LINQ [C#], generic types
- generic types [LINQ]
- generics [LINQ]
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1951d53b069104f3439aa2fe3ee3975bae0e1659
ms.lasthandoff: 03/13/2017

---
# <a name="linq-and-generic-types-c"></a>LINQ und generische Typen (C#)
[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen basieren auf generischen Typen, die mit Version 2.0 von [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] eingeführt wurden. Sie benötigen kein ausführliches Wissen über Generika, um Abfragen schreiben zu können. Dennoch sollten Sie zwei grundlegende Konzepte verstehen:  
  
1.  Wenn Sie eine Instanz einer generischen Auflistungsklasse wie etwa <xref:System.Collections.Generic.List%601> erstellen, ersetzen Sie das „T“ durch den Objekttyp, den die Liste enthalten wird. Eine Liste von Zeichenfolgen wird z.B. als `List<string>` und eine Liste von `Customer`-Objekten als `List<Customer>` ausgedrückt. Eine generische Liste ist stark typisiert und hat gegenüber Auflistungen, die ihre Elemente als <xref:System.Object> speichern, viele Vorzüge. Wenn Sie versuchen einen `Customer` in eine `List<string>` einzufügen, erhalten Sie zur Laufzeit eine Fehlermeldung. Es ist sehr leicht, generische Auflistungen zu verwenden, da Sie keine Laufzeitumwandlung von Typen durchführen müssen.  
  
2.  <xref:System.Collections.Generic.IEnumerable%601> ist die Schnittstelle, die es ermöglicht, dass generische Auflistungsklassen mithilfe der Anweisung `foreach` aufzählt. Generische Auflistungsklassen unterstützen <xref:System.Collections.Generic.IEnumerable%601> so wie nicht generische Auflistungsklassen – wie etwa <xref:System.Collections.ArrayList> – <xref:System.Collections.IEnumerable> unterstützen.  
  
 Weitere Informationen zu Generika finden Sie unter [Generika](../../../../csharp/programming-guide/generics/index.md).  
  
## <a name="ienumerablet-variables-in-linq-queries"></a>IEnumerable<T\>-Variablen in LINQ-Abfragen  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragevariablen sind vom Typ <xref:System.Collections.Generic.IEnumerable%601>, oder sie sind abgeleitete Typen wie etwa <xref:System.Linq.IQueryable%601>. Wenn Sie eine Abfragevariable des Typs `IEnumerable<Customer>` sehen, bedeutet dies nur, dass die Abfrage bei der Ausführung eine Folge von null oder mehr `Customer`-Objekten produziert.  
  
 [!code-cs[csLINQGettingStarted#34](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_1.cs)]  
  
 Weitere Informationen finden Sie unter [Typbeziehungen in LINQ-Abfragevorgängen](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
## <a name="letting-the-compiler-handle-generic-type-declarations"></a>Verarbeiten von generischen Typdeklaration durch den Compiler  
 Falls Sie dies möchten, können Sie generische Syntax umgehen, indem Sie das Schlüsselwort [var](../../../../csharp/language-reference/keywords/var.md) verwenden. Das Schlüsselwort `var` weist den Compiler an, den Typ der Abfragevariablen abzuleiten, indem er sich an der in der `from`-Klausel angegebenen Datenquelle orientiert. Das folgende Beispiel erstellt den gleichen kompilierten Code wie das vorherige Beispiel:  
  
 [!code-cs[csLINQGettingStarted#35](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_2.cs)]  
  
 Das Schlüsselwort `var` ist nützlich, wenn der Typ der Variablen offensichtlich ist, oder wenn es nicht so wichtig ist, die geschachtelten generischen Typen explizit festzulegen, wie z.B. diejenigen, die in Gruppenabfragen erstellt werden. Allgemein wird darauf hingewiesen, dass das Verwenden von `var` das Lesen Ihres Codes durch andere erschwert. Weitere Informationen zu finden Sie unter [Implizit typisierte lokale Variablen](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte mit LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Generika](../../../../csharp/programming-guide/generics/index.md)
