---
title: Abfrageausdruckssyntax für Standardabfrageoperatoren
ms.date: 07/20/2015
ms.assetid: eb978d86-d3b5-497b-95ce-a054bea8f510
ms.openlocfilehash: 57a08f6540cbf3e091ee1b2e202e0e181487e3be
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090247"
---
# <a name="query-expression-syntax-for-standard-query-operators-visual-basic"></a>Abfrage Ausdrucks Syntax für Standard Abfrage Operatoren (Visual Basic)

Einige der häufiger verwendeten Standard Abfrage Operatoren verfügen über eine dedizierte Schlüsselwort Syntax für Visual Basic Sprache, mit der Sie als Teil eines *Abfrage Ausdrucks*aufgerufen werden können. Mit einem Abfrageausdruck kann eine Abfrage besser lesbar ausgedrückt werden als mit dessen *methodenbasierter* Entsprechung. Die Abfrageausdrucksklauseln werden bei der Kompilierung in Aufrufe der Abfragemethoden übersetzt.  
  
## <a name="query-expression-syntax-table"></a>Tabelle: Abfrageausdruckssyntax  

 In der folgenden Tabelle finden Sie eine Liste von Standardabfrageoperatoren, die über äquivalente Abfrageausdrucksklauseln verfügen.  
  
|Methode|Syntax von Visual Basic-Abfrage Ausdrücken|  
|------------|------------------------------------------|  
|<xref:System.Linq.Enumerable.All%2A>|`Aggregate … In … Into All(…)`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Any%2A>|`Aggregate … In … Into Any()`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Average%2A>|`Aggregate … In … Into Average()`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Cast%2A>|`From … As …`<br /><br /> (Weitere Informationen finden Sie unter [from-Klausel](../../../language-reference/queries/from-clause.md).)|  
|<xref:System.Linq.Enumerable.Count%2A>|`Aggregate … In … Into Count()`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Distinct%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|`Distinct`<br /><br /> (Weitere Informationen finden Sie unter unter [schiedliche-Klausel](../../../language-reference/queries/distinct-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`Group … By … Into …`<br /><br /> (Weitere Informationen finden Sie unter [Group By-Klausel](../../../language-reference/queries/group-by-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`Group Join … In … On …`<br /><br /> (Weitere Informationen finden Sie unter [Group Join-Klausel](../../../language-reference/queries/group-join-clause.md).)|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`From x In …, y In … Where x.a = b.a`<br /><br /> - oder -<br /><br /> `Join … [As …]In … On …`<br /><br /> (Weitere Informationen finden Sie unter [Join-Klausel](../../../language-reference/queries/join-clause.md).)|  
|<xref:System.Linq.Enumerable.LongCount%2A>|`Aggregate … In … Into LongCount()`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Max%2A>|`Aggregate … In … Into Max()`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Min%2A>|`Aggregate … In … Into Min()`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By`<br /><br /> (Weitere Informationen finden Sie unter [Order By-Klausel](../../../language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By … Descending`<br /><br /> (Weitere Informationen finden Sie unter [Order By-Klausel](../../../language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.Select%2A>|`Select`<br /><br /> (Weitere Informationen finden Sie unter [SELECT-Klausel](../../../language-reference/queries/select-clause.md).)|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|Mehrere `From` Klauseln<br /><br /> (Weitere Informationen finden Sie unter [from-Klausel](../../../language-reference/queries/from-clause.md).)|  
|<xref:System.Linq.Enumerable.Skip%2A>|`Skip`<br /><br /> (Weitere Informationen finden Sie unter [Skip-Klausel](../../../language-reference/queries/skip-clause.md).)|  
|<xref:System.Linq.Enumerable.SkipWhile%2A>|`Skip While`<br /><br /> (Weitere Informationen finden Sie unter [Skip While-Klausel](../../../language-reference/queries/skip-while-clause.md).)|  
|<xref:System.Linq.Enumerable.Sum%2A>|`Aggregate … In … Into Sum()`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Take%2A>|`Take`<br /><br /> (Weitere Informationen finden Sie unter [Take-Klausel](../../../language-reference/queries/take-clause.md).)|  
|<xref:System.Linq.Enumerable.TakeWhile%2A>|`Take While`<br /><br /> (Weitere Informationen finden Sie unter [Take While-Klausel](../../../language-reference/queries/take-while-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By …, …`<br /><br /> (Weitere Informationen finden Sie unter [Order By-Klausel](../../../language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By …, … Descending`<br /><br /> (Weitere Informationen finden Sie unter [Order By-Klausel](../../../language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.Where%2A>|`Where`<br /><br /> (Weitere Informationen finden Sie unter [WHERE-Klausel](../../../language-reference/queries/where-clause.md).)|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](standard-query-operators-overview.md)
- [Klassifizierung von Standard Abfrage Operatoren nach Ausführungs Arten (Visual Basic)](classification-of-standard-query-operators-by-manner-of-execution.md)
