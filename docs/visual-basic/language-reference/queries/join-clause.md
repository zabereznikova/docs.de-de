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
ms.openlocfilehash: b0baca9f897a00b3c6c67699629477ff385d6ef7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353266"
---
# <a name="join-clause-visual-basic"></a>Join-Klausel (Visual Basic)

Fasst zwei Auflistungen zu einer einzelnen Auflistung zusammen. Der Joinvorgang basiert auf übereinstimmenden Schlüsseln und verwendet den `Equals`-Operator.

## <a name="syntax"></a>Syntax

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a>-Komponenten

`element` ist erforderlich. Die Steuerelement Variable für die Auflistung, die verknüpft wird.

`collection`  
Erforderlich Die Auflistung, die mit der auf der linken Seite des `Join` Operators identifizierten Auflistung kombiniert werden soll. Eine `Join`-Klausel kann in einer anderen `Join`-Klausel oder in einer `Group Join`-Klausel eingefügt werden.

`joinClause`  
Optional. Mindestens eine zusätzliche `Join`-Klausel, um die Abfrage weiter zu verfeinern.

`groupJoinClause`  
Optional. Mindestens eine zusätzliche `Group Join`-Klausel, um die Abfrage weiter zu verfeinern.

`key1` `Equals` `key2`  
Erforderlich Identifiziert Schlüssel für die Auflistungen, die verknüpft werden. Sie müssen den `Equals`-Operator verwenden, um Schlüssel aus den Auflistungen zu vergleichen, die verknüpft werden. Joinbedingungen können mithilfe des `And`-Operators kombiniert werden, um mehrere Schlüssel zu identifizieren. `key1` muss von der Auflistung auf der linken Seite des `Join` Operators sein. `key2` muss von der Auflistung auf der rechten Seite des `Join` Operators sein.

Die in der Join-Bedingung verwendeten Schlüssel können Ausdrücke sein, die mehr als ein Element aus der Auflistung enthalten. Jeder Schlüssel Ausdruck kann jedoch nur Elemente aus der jeweiligen Auflistung enthalten.

## <a name="remarks"></a>Hinweise

Die `Join`-Klausel kombiniert zwei Auflistungen basierend auf übereinstimmenden Schlüsselwerten aus den verbundenen Sammlungen. Die resultierende Auflistung kann eine beliebige Kombination von Werten aus der Auflistung enthalten, die auf der linken Seite des `Join` Operators und der in der `Join`-Klausel identifizierten Auflistung identifiziert werden. Die Abfrage gibt nur Ergebnisse zurück, für die die vom `Equals` Operator angegebene Bedingung erfüllt wird. Dies entspricht einer `INNER JOIN` in SQL.

Sie können mehrere `Join` Klauseln in einer Abfrage verwenden, um zwei oder mehr Auflistungen in einer einzelnen Auflistung zu verknüpfen.

Sie können einen impliziten Join ausführen, um Auflistungen ohne die `Join`-Klausel zu kombinieren. Fügen Sie zu diesem Zweck mehrere `In`-Klauseln in Ihre `From`-Klausel ein, und geben Sie eine `Where`-Klausel an, die die Schlüssel angibt, die Sie für den Join verwenden möchten.

Sie können die `Group Join`-Klausel verwenden, um Auflistungen in einer einzelnen hierarchischen Auflistung zu kombinieren. Dies ist wie eine `LEFT OUTER JOIN` in SQL.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird ein impliziter Join durchführt, um eine Liste von Kunden mit Ihren Aufträgen zu kombinieren.

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel werden zwei Auflistungen mithilfe der `Join`-Klausel miteinander verbunden.

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

In diesem Beispiel wird eine Ausgabe ähnlich der folgenden erzeugt:

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel werden zwei Auflistungen mithilfe der `Join`-Klausel mit zwei Schlüssel Spalten verbunden.

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

Im Beispiel wird eine Ausgabe ähnlich der folgenden erzeugt:

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Group Join-Klausel](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
