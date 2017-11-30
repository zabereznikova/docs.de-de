---
title: Auf NULL festlegbare Werttypen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8734114b9d657066a0ef0b2d648f0290c03b1cbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-value-types-visual-basic"></a>Auf NULL festlegbare Werttypen (Visual Basic)
In einigen Fällen arbeiten Sie mit einem Werttyp, der nicht über einen definierten Wert unter bestimmten Umständen verfügt. Z. B. ein Feld in einer Datenbank möglicherweise unterscheiden, dass einen Wert zugewiesen, der sinnvoll ist, ohne dass einen Wert zugewiesen. Werttypen können erweitert werden, um die normalen Werte oder einen null-Wert zu nutzen. Eine solche Erweiterung wird aufgerufen, eine *nullable-Typ*.  
  
 Jede nullable-Typ wird erstellt, von der generischen <xref:System.Nullable%601> Struktur. Erwägen Sie eine Datenbank, die Arbeitsaufgaben-bezogenen Aktivitäten verfolgt. Das folgende Beispiel erstellt einen `Boolean` geben und deklariert eine Variable dieses Typs. Sie können die Deklaration auf drei Arten schreiben:  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]  
  
 Die Variable `ridesBusToWork` können Aufnahme eines Werts von `True`, einen Wert von `False`, oder überhaupt kein Wert. Der anfängliche Standardwert ist kein Wert, der bedeuten in diesem Fall, dass die Informationen noch nicht für diese Person abgerufen wurde. Im Gegensatz dazu `False` bedeuten, dass die Informationen abgerufen wurden und die Person, die nicht mit den Bus zur Arbeit kommt.  
  
 Deklarieren von Variablen und Eigenschaften mit auf NULL festlegbare Typen, und Sie können ein Array mit Elementen des dem nullable-Typ deklarieren. Sie können Prozeduren mit auf NULL festlegbaren Typen als Parameter deklarieren, und Sie können aus den nullable-Typ zurückgeben einer `Function` Prozedur.  
  
 Sie können keinen nullable-Typ für einen Verweistyp wie z. B. ein Array erstellen eine `String`, oder eine Klasse. Der zugrunde liegende Typ muss ein Werttyp sein. Weitere Informationen finden Sie unter [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
## <a name="using-a-nullable-type-variable"></a>Mithilfe einer Variablen des Typs NULL-Werte zulässt  
 Die wichtigsten Elemente von dem nullable-Typ werden die <xref:System.Nullable%601.HasValue%2A> und <xref:System.Nullable%601.Value%2A> Eigenschaften. Für eine Variable mit dem nullable-Typ <xref:System.Nullable%601.HasValue%2A> gibt Aufschluss darüber, ob die Variable einen definierten Wert enthält. Wenn <xref:System.Nullable%601.HasValue%2A> ist `True`, erfahren Sie, den Wert von <xref:System.Nullable%601.Value%2A>. Beachten Sie, dass beide <xref:System.Nullable%601.HasValue%2A> und <xref:System.Nullable%601.Value%2A> sind `ReadOnly` Eigenschaften.  
  
### <a name="default-values"></a>Standardwerte  
 Beim Deklarieren einer Variablenverweis mit dem nullable-Typ, dessen <xref:System.Nullable%601.HasValue%2A> Eigenschaft hat den Standardwert `False`. Dies bedeutet, dass standardmäßig die Variable keinen definierten Wert, statt den Standardwert der zugrunde liegenden Werttyp verfügt. Im folgenden Beispiel wird die Variable `numberOfChildren` anfänglich kein definierten Wert vorliegt, obwohl den Wert von der `Integer` ist 0.  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]  
  
 Ein null-Wert ist hilfreich, einen nicht definierten oder unbekannten Wert anzugeben. Wenn `numberOfChildren` deklariert wurde als `Integer`, gib es kein Wert, der darauf hinweisen kann, dass die Informationen nicht verfügbar ist.  
  
### <a name="storing-values"></a>Speichern von Werten  
 Speichern Sie einen Wert in einer Variablen oder Eigenschaft eines Typs mit NULL-Werte zulässt, auf die gewohnte Weise. Im folgende Beispiel weist einen Wert der Variablen `numberOfChildren` im vorherigen Beispiel deklariert.  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]  
  
 Wenn eine Variable oder eine Eigenschaft eines NULL-Werte zulassen Typs einen definierten Wert enthält, können Sie es auf ihren ursprünglichen Zustand der ohne eines zugewiesenen Wert zurücksetzen auslösen. Sie dazu die Variable oder die Eigenschaft `Nothing`, wie im folgende Beispiel gezeigt.  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]  
  
> [!NOTE]
>  Sie können zwar zuweisen `Nothing` einer Variablen eines Typs mit NULL-Werte zulässt, kann nicht für test `Nothing` mit dem Gleichheitszeichen. Vergleich, die das Gleichheitszeichen verwendet `someVar = Nothing`, ergibt immer `Nothing`. Testen Sie der Variablentyps <xref:System.Nullable%601.HasValue%2A> -Eigenschaft für `False`, oder testen, indem die `Is` oder `IsNot` Operator.  
  
### <a name="retrieving-values"></a>Abrufen von Werten  
 Zum Abrufen des Werts einer Variablen eines NULL-Werte zulässt, überprüfen Sie zunächst die <xref:System.Nullable%601.HasValue%2A> Eigenschaft, um sicherzustellen, dass er einen Wert aufweist. Wenn Sie versuchen, lesen Sie den Wert beim <xref:System.Nullable%601.HasValue%2A> ist `False`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] löst eine <xref:System.InvalidOperationException> Ausnahme. Das folgende Beispiel zeigt die empfohlene Methode zum Lesen der Variablen `numberOfChildren` vorherigen Beispiele.  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]  
  
## <a name="comparing-nullable-types"></a>Vergleichen von Typen mit Nullwert  
 Wenn NULL-Werte zulassen `Boolean` Variablen in booleschen Ausdrücken verwendet werden, kann das Ergebnis `True`, `False`, oder `Nothing`. Im folgenden ist die Wahrheitstabelle für `And` und `Or`. Da `b1` und `b2` verfügen jetzt über drei mögliche Werte sind neun Kombinationen auszuwerten.  
  
|B1|B2|B1 und b2|B1 oder b2|  
|--------|--------|---------------|--------------|  
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|  
|`Nothing`|`True`|`Nothing`|`True`|  
|`Nothing`|`False`|`False`|`Nothing`|  
|`True`|`Nothing`|`Nothing`|`True`|  
|`True`|`True`|`True`|`True`|  
|`True`|`False`|`False`|`True`|  
|`False`|`Nothing`|`False`|`Nothing`|  
|`False`|`True`|`False`|`True`|  
|`False`|`False`|`False`|`False`|  
  
 Wenn der Wert einer booleschen Variable oder ein Ausdruck ist `Nothing`, es ist keines von beiden `true` noch `false`. Betrachten Sie das folgende Beispiel.  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]  
  
 In diesem Beispiel `b1 And b2` ergibt `Nothing`. Daher die `Else` -Klausel ausgeführt wird, in den einzelnen `If` -Anweisung und die Ausgabe lautet wie folgt:  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  `AndAlso`und `OrElse`, welche verwenden kurzschlussauswertung müssen ihrer zweiten Operanden ergeben, wenn das erste ergibt `Nothing`.  
  
## <a name="propagation"></a>Weitergabe  
 Wenn eine oder beide der Operanden ein Arithmetik, Vergleich, UMSCHALT oder einem Rollenporttyp-Vorgang ist NULL-Werte zulässt, ist das Ergebnis des Vorgangs auch NULL-Werte zulässt. Wenn beide Operanden Werte aufweisen, die nicht `Nothing`, auf die zugrunde liegenden Werte der Operanden an, wird der Vorgang ausgeführt, als wäre weder ein NULL-Werte zulässt. Im folgenden Beispiel werden die Variablen `compare1` und `sum1` implizit typisiert werden. Wenn Sie den Mauszeiger darüber bewegen, sehen Sie sich, dass leitet der Compiler die Typen mit Nullwert für beide Identitäten.  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]  
  
 Wenn einer oder beide der Operanden den Wert haben `Nothing`, das Ergebnis `Nothing`.  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]  
  
## <a name="using-nullable-types-with-data"></a>Verwenden von auf NULL festlegbaren Typen mit Daten  
 Eine Datenbank ist eine der wichtigsten Stellen auf NULL festlegbare Typen verwenden. Nicht alle Datenbankobjekte unterstützen gegenwärtig auf NULL festlegbare Typen, aber führen Sie die vom Designer generierten TableAdapter. Siehe "TableAdapter-Unterstützung für Typen mit Nullwert" in [Übersicht über TableAdapters](/visualstudio/data-tools/tableadapter-overview).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.InvalidOperationException>  
 <xref:System.Nullable%601.HasValue%2A>  
 [Verwenden von Typen mit Nullwert](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Übersicht über TableAdapters](/visualstudio/data-tools/tableadapter-overview)  
 [If-Operator](../../../../visual-basic/language-reference/operators/if-operator.md)  
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)
