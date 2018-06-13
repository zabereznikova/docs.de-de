---
title: Join-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: 2186954ab6536988271629c4feba0a40563bfc3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603911"
---
# <a name="join-clause-visual-basic"></a>Join-Klausel (Visual Basic)
Fasst zwei Auflistungen zu einer einzelnen Auflistung zusammen. Die Join-Operation wird basierend auf übereinstimmenden Schlüsseln und verwendet die `Equals` Operator.  
  
## <a name="syntax"></a>Syntax  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a>Teile  
 `element`  
 Erforderlich. Die Steuerelementvariable für die zu verknüpfende Auflistung.  
  
 `collection`  
 Erforderlich. Die Auflistung, die mit der Auflistung auf der linken Seite des kombiniert die `Join` Operator. Ein `Join` Klausel kann geschachtelt sein, in einer anderen `Join` -Klausel, oder in einem `Group Join` Klausel.  
  
 `joinClause`  
 Dies ist optional. Eine oder mehrere zusätzliche `Join` Klauseln weiter optimieren der Abfrage.  
  
 `groupJoinClause`  
 Dies ist optional. Eine oder mehrere zusätzliche `Group Join` Klauseln weiter optimieren der Abfrage.  
  
 `key1` `Equals` `key2`  
 Erforderlich. Identifiziert die Schlüssel für die zu verknüpfenden Auflistungen. Verwenden Sie die `Equals` Operator zum Vergleichen von Schlüsseln aus der zu verknüpfenden Auflistungen. Sie können die Join-Bedingungen kombinieren, mit der `And` Operator, um mehrere Schlüssel zu identifizieren. `key1` muss aus der Auflistung auf der linken Seite von der `Join` Operator. `key2` aus der Auflistung auf der rechten Seite des muss die `Join` Operator.  
  
 Die in der Joinbedingung verwendeten Schlüssel können Ausdrücke sein, die mehr als ein Element aus der Auflistung enthalten. Jeder Schlüsselausdruck kann jedoch nur die Elemente aus der entsprechenden Auflistung enthalten.  
  
## <a name="remarks"></a>Hinweise  
 Die `Join` Klausel Fasst zwei Auflistungen, die basierend auf übereinstimmenden Schlüsselwerten von zu verknüpfenden Auflistungen zusammen. Die resultierende Auflistung kann eine beliebige Kombination von Werten aus der Auflistung auf der linken Seite des enthalten die `Join` Operator und der Auflistung identifiziert, der `Join` Klausel. Die Abfrage gibt nur Ergebnisse für die die Bedingung angegeben werden, indem zurück die `Equals` Operator erfüllt ist. Dies ist gleichbedeutend mit einem `INNER JOIN` in SQL.  
  
 Sie können mehrere `Join` Klauseln in einer Abfrage mindestens zwei Auflistungen zu einer einzigen Auflistung zu verknüpfen.  
  
 Ausführen ein implizites Joins zum Kombinieren von Auflistungen, ohne die `Join` Klausel. Um dies zu erreichen, fügen Sie mehrere `In` Klauseln in Ihre `From` Klausel, und geben Sie einen `Where` -Klausel, die die Schlüssel identifiziert, die Sie für den Join verwenden möchten.  
  
 Sie können die `Group Join` -Klausel, um Auflistungen zu einer einzelnen hierarchischen Auflistung kombinieren. Dies ist z. B. eine `LEFT OUTER JOIN` in SQL.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel führt eine implizite Verknüpfung, um eine Liste von Kunden mit ihrer Bestellungen zu kombinieren.  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird verknüpft zwei Auflistungen mithilfe der `Join` Klausel.  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 In diesem Beispiel wird die Ausgabe ähnlich der folgenden aus:  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird verknüpft zwei Auflistungen mithilfe der `Join` -Klausel mit zwei Schlüsselspalten.  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 Im Beispiel wird die Ausgabe ähnlich der folgenden aus:  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/queries.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Group Join-Klausel](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
