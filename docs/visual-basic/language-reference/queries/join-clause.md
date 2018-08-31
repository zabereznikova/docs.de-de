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
ms.openlocfilehash: b1551583079c66d1bf5f6963a42d5d24e518fff3
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "43255296"
---
# <a name="join-clause-visual-basic"></a>Join-Klausel (Visual Basic)
Fasst zwei Auflistungen zu einer einzelnen Auflistung zusammen. Die Join-Operation wird auf Grundlage übereinstimmender Schlüssel und verwendet die `Equals` Operator.  
  
## <a name="syntax"></a>Syntax  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a>Teile  
 `element`  
 Erforderlich. Die Steuerelementvariable für die Sammlung verknüpft wird.  
  
 `collection`  
 Erforderlich. Die Auflistung, die mit der Auflistung auf der linken Seite des kombiniert die `Join` Operator. Ein `Join` -Klausel kann in einer anderen geschachtelt werden `Join` -Klausel oder in einem `Group Join` Klausel.  
  
 `joinClause`  
 Dies ist optional. Eine oder mehrere zusätzliche `Join` -Klauseln zum weiteren Optimieren der Abfrage.  
  
 `groupJoinClause`  
 Dies ist optional. Eine oder mehrere zusätzliche `Group Join` -Klauseln zum weiteren Optimieren der Abfrage.  
  
 `key1` `Equals` `key2`  
 Erforderlich. Bezeichnet die Schlüssel für die Auflistungen verknüpft wird. Verwenden Sie die `Equals` Operator zum Vergleichen von Schlüsseln aus den zu verknüpfenden Auflistungen. Sie können den Join-Bedingungen kombinieren, mit der `And` Operator, um mehrere Schlüssel zu identifizieren. `key1` aus der Auflistung auf der linken Seite des muss die `Join` Operator. `key2` aus der Auflistung auf der rechten Seite des muss die `Join` Operator.  
  
 Die Schlüssel für die Join-Bedingung können Ausdrücke sein, die mehr als ein Element aus der Auflistung enthalten. Jedes Schlüssel-Ausdrucks kann jedoch nur die Elemente aus der entsprechenden Auflistung enthalten.  
  
## <a name="remarks"></a>Hinweise  
 Die `Join` Klausel Fasst zwei Auflistungen, die basierend auf übereinstimmenden Werte aus den zu verknüpfenden Auflistungen zusammen. Die resultierende Auflistung kann eine beliebige Kombination von Werten aus der Auflistung auf der linken Seite des enthalten die `Join` Operator und der Auflistung identifiziert, die der `Join` Klausel. Die Abfrage gibt nur Ergebnisse für die die Bedingung, durch angegeben die `Equals` Operator erfüllt ist. Dies ist äquivalent zu einer `INNER JOIN` in SQL.  
  
 Sie können mehrere `Join` Klauseln in einer Abfrage mindestens zwei Auflistungen in einer einzelnen Auflistung zu verknüpfen.  
  
 Sie können eine implizite Verknüpfung zum Kombinieren von Sammlungen ohne Ausführen der `Join` Klausel. Zu diesem Zweck fügen Sie mehrere `In` Klauseln in Ihrem `From` Klausel, und geben Sie einen `Where` -Klausel, die die Schlüssel identifiziert, die Sie für den Join verwenden möchten.  
  
 Sie können die `Group Join` -Klausel, um Auflistungen in einer einzelnen hierarchischen Auflistung zu kombinieren. Dies ist z. B. eine `LEFT OUTER JOIN` in SQL.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel führt eine implizite Verknüpfung, um eine Liste von Kunden mit ihrer Bestellungen zu kombinieren.  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird joins von zwei Auflistungen mithilfe der `Join` Klausel.  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 In diesem Beispiel wird eine Ausgabe ähnlich der folgenden erzeugt:  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird joins von zwei Auflistungen mithilfe der `Join` -Klausel mit zwei Spalten.  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 Im Beispiel wird eine Ausgabe ähnlich der folgenden erzeugt:  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/index.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Group Join-Klausel](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
