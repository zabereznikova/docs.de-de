---
title: Join-Klausel
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
ms.openlocfilehash: f73dc31bbbb9014a8a1a315de406c53fa58d1c65
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359773"
---
# <a name="join-clause-visual-basic"></a>Join-Klausel (Visual Basic)

Fasst zwei Auflistungen zu einer einzelnen Auflistung zusammen. Der Joinvorgang basiert auf übereinstimmenden Schlüsseln und verwendet den- `Equals` Operator.

## <a name="syntax"></a>Syntax

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a>Bestandteile

`element` ist erforderlich. Die Steuerelement Variable für die Auflistung, die verknüpft wird.

`collection`  
Erforderlich. Die Auflistung, die mit der auf der linken Seite des Operators identifizierten Auflistung kombiniert werden soll `Join` . Eine- `Join` Klausel kann in einer anderen- `Join` Klausel oder in einer- `Group Join` Klausel eingefügt werden.

`joinClause`  
Optional. Eine oder mehrere zusätzliche `Join` Klauseln, um die Abfrage weiter zu verfeinern.

`groupJoinClause`  
Optional. Eine oder mehrere zusätzliche `Group Join` Klauseln, um die Abfrage weiter zu verfeinern.

`key1` `Equals` `key2`  
Erforderlich. Identifiziert Schlüssel für die Auflistungen, die verknüpft werden. Sie müssen den- `Equals` Operator verwenden, um Schlüssel aus den verbundenen Sammlungen zu vergleichen. Joinbedingungen können mithilfe des-Operators kombiniert werden `And` , um mehrere Schlüssel zu identifizieren. `key1`muss sich auf der linken Seite des Operators aus der Auflistung befinden `Join` . `key2`muss von der Auflistung auf der rechten Seite des Operators sein `Join` .

Die in der Join-Bedingung verwendeten Schlüssel können Ausdrücke sein, die mehr als ein Element aus der Auflistung enthalten. Jeder Schlüssel Ausdruck kann jedoch nur Elemente aus der jeweiligen Auflistung enthalten.

## <a name="remarks"></a>Bemerkungen

Die- `Join` Klausel kombiniert zwei Auflistungen basierend auf übereinstimmenden Schlüsselwerten aus den verbundenen Sammlungen. Die resultierende Auflistung kann eine beliebige Kombination von Werten aus der Auflistung enthalten, die auf der linken Seite des Operators identifiziert wird, `Join` und die in der-Klausel identifizierte Auflistung `Join` . Die Abfrage gibt nur Ergebnisse zurück, für die die vom Operator angegebene Bedingung `Equals` erfüllt ist. Dies entspricht einem `INNER JOIN` in SQL.

Sie können mehrere `Join` Klauseln in einer Abfrage verwenden, um zwei oder mehr Auflistungen in einer einzelnen Auflistung zu verknüpfen.

Sie können einen impliziten Join ausführen, um Auflistungen ohne die-Klausel zu kombinieren `Join` . Fügen Sie zu diesem Zweck mehrere `In` -Klauseln in die `From` -Klausel ein, und geben Sie eine- `Where` Klausel an, die die Schlüssel identifiziert, die Sie für den Join verwenden möchten.

Sie können die- `Group Join` Klausel verwenden, um Sammlungen in einer einzelnen hierarchischen Auflistung zu kombinieren. Dies ist wie ein `LEFT OUTER JOIN` in SQL.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird ein impliziter Join durchführt, um eine Liste von Kunden mit Ihren Aufträgen zu kombinieren.

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel werden zwei Auflistungen mithilfe der-Klausel miteinander verbunden `Join` .

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

In diesem Beispiel wird eine Ausgabe ähnlich der folgenden erzeugt:

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel werden zwei Auflistungen mithilfe der- `Join` Klausel mit zwei Schlüssel Spalten verbunden.

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

Im Beispiel wird eine Ausgabe ähnlich der folgenden erzeugt:

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a>Weitere Informationen

- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](index.md)
- [SELECT-Klausel](select-clause.md)
- [From-Klausel](from-clause.md)
- [Group Join-Klausel](group-join-clause.md)
- [WHERE-Klausel](where-clause.md)
