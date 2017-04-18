---
title: Auf NULL festlegbare Werttypen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Nullable
dev_langs:
- VB
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9cdf1864fe955a082936596821ee84c831b86444
ms.lasthandoff: 03/13/2017

---
# <a name="nullable-value-types-visual-basic"></a>Auf NULL festlegbare Werttypen (Visual Basic)
Zuweilen arbeiten Sie mit einem Werttyp, der keinen definierten Wert unter bestimmten Umständen. Z. B. möglicherweise ein Feld in einer Datenbank unterscheiden, ob ihm ein Wert zugewiesen, der sinnvoll ist, ohne dass einen Wert zugewiesen. Werttypen können erweitert werden, um ihre normalen Werte oder einen null-Wert zu nutzen. Eine solche Erweiterung wird aufgerufen, ein *auf NULL festlegbaren Typ*.  
  
 Jeder auf NULL festlegbare Typ wird erstellt, von der generischen <xref:System.Nullable%601>Struktur.</xref:System.Nullable%601> Nehmen Sie eine Datenbank, die geschäftliche Aktivitäten nachverfolgt. Das folgende Beispiel erstellt ein auf NULL festlegbares `Boolean` geben und deklariert eine Variable dieses Typs. Sie können die Deklaration auf drei Arten schreiben:  
  
 [!code-vb[VbVbalrNullableValue&#1;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]  
  
 Die Variable `ridesBusToWork` können keinen Wert enthalten `True`, ein Wert von `False`, oder überhaupt kein Wert. Der anfängliche Standardwert ist kein Wert, der bedeuten in diesem Fall, dass sich die Informationen noch nicht für diese Person abgerufen wurde. Im Gegensatz dazu `False` bedeuten, dass die Informationen abgerufen wurden und die Person, die nicht mit den Bus zur Arbeit kommt.  
  
 Sie können Variablen und Eigenschaften mit auf NULL festlegbaren Typen deklarieren, und Sie können ein Array mit Elementen eines auf NULL festlegbaren Typs deklarieren. Sie können Prozeduren mit auf NULL festlegbaren Typen als Parameter deklarieren, und Sie können einen Typ von Zurückgeben einer `Function` Prozedur.  
  
 Sie können einen Typ für einen Verweistyp wie z. B. ein Array können nicht erstellt eine `String`, oder eine Klasse. Der zugrunde liegende Typ muss ein Werttyp sein. Weitere Informationen finden Sie unter [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
## <a name="using-a-nullable-type-variable"></a>Verwenden einer Variablen auf NULL festlegbaren Typ  
 Die wichtigsten Member eines auf NULL festlegbaren Typs sind seine <xref:System.Nullable%601.HasValue%2A>und <xref:System.Nullable%601.Value%2A>Eigenschaften.</xref:System.Nullable%601.Value%2A> </xref:System.Nullable%601.HasValue%2A> Für eine Variable eines Typs auf NULL festlegbare <xref:System.Nullable%601.HasValue%2A>erfahren Sie, ob die Variable einen definierten Wert enthält.</xref:System.Nullable%601.HasValue%2A> Wenn <xref:System.Nullable%601.HasValue%2A>ist `True`, Sie können den Wert von <xref:System.Nullable%601.Value%2A>.</xref:System.Nullable%601.Value%2A> lesen</xref:System.Nullable%601.HasValue%2A> Beachten Sie, dass beide <xref:System.Nullable%601.HasValue%2A>und <xref:System.Nullable%601.Value%2A>sind `ReadOnly` Eigenschaften.</xref:System.Nullable%601.Value%2A> </xref:System.Nullable%601.HasValue%2A>  
  
### <a name="default-values"></a>Standardwerte  
 Beim Deklarieren einer Variablenverweis mit einem NULL-Werte zulässt, dessen <xref:System.Nullable%601.HasValue%2A>Eigenschaft hat den Standardwert `False`.</xref:System.Nullable%601.HasValue%2A> Dies bedeutet, dass standardmäßig die Variable keinen definierten Wert, statt des Standardwerts des ihr zugrunde liegenden Werttyps enthält. Im folgenden Beispiel die Variable `numberOfChildren` Anfangs hat keinen definierten Wert, obwohl den Standardwert der `Integer` ist 0.  
  
 [!code-vb[VbVbalrNullableValue&#2;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]  
  
 Ein null-Wert ist sinnvoll, einen undefinierten oder unbekannten Wert anzugeben. Wenn `numberOfChildren` deklariert wurde als `Integer`, wäre kein Wert, die darauf hinweisen könnte, dass die Informationen derzeit nicht verfügbar ist.  
  
### <a name="storing-values"></a>Speichern von Werten  
 Sie speichern einen Wert in einer Variablen oder Eigenschaft eines auf NULL festlegbaren Typs auf die gewohnte Weise. Im folgende Beispiel weist einen Wert der Variablen `numberOfChildren` im vorherigen Beispiel deklariert.  
  
 [!code-vb[VbVbalrNullableValue&3;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]  
  
 Wenn eine Variable oder die Eigenschaft einen Typ einen definierten Wert enthält, können Sie es wieder in den Anfangszustand keinen zugewiesenen Wert auslösen. Sie dazu die Variable oder die Eigenschaft `Nothing`, wie im folgende Beispiel gezeigt.  
  
 [!code-vb[VbVbalrNullableValue&4;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]  
  
> [!NOTE]
>  Sie können zwar zuweisen `Nothing` einer Variablen eines Typs mit NULL-Werte zulässt, kann nicht für test `Nothing` mit dem Gleichheitszeichen. Vergleich des Gleichheitszeichens, `someVar = Nothing`, ergibt immer `Nothing`. Testen Sie der Variablentyps <xref:System.Nullable%601.HasValue%2A>-Eigenschaft für `False`, oder testen Sie mithilfe der `Is` oder `IsNot` Operator.</xref:System.Nullable%601.HasValue%2A>  
  
### <a name="retrieving-values"></a>Abrufen von Werten  
 Um den Wert einer Variablen mit einem auf NULL festlegbaren Typ abzurufen, überprüfen Sie zunächst die <xref:System.Nullable%601.HasValue%2A>Eigenschaft, um sicherzustellen, dass sie einen Wert hat.</xref:System.Nullable%601.HasValue%2A> Wenn Sie versuchen, den Wert zu lesen, wenn <xref:System.Nullable%601.HasValue%2A>ist `False`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] löst eine <xref:System.InvalidOperationException>Ausnahme.</xref:System.InvalidOperationException> </xref:System.Nullable%601.HasValue%2A> Im folgende Beispiel wird die empfohlene Vorgehensweise zum Lesen der Variablen `numberOfChildren` der vorherigen Beispiele.  
  
 [!code-vb[VbVbalrNullableValue&5;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]  
  
## <a name="comparing-nullable-types"></a>Vergleichen von auf NULL festlegbaren Typen  
 Wenn NULL-Werte zu `Boolean` Variablen in booleschen Ausdrücken verwendet werden, kann das Ergebnis `True`, `False`, oder `Nothing`. Im folgenden ist die Wahrheitstabelle für `And` und `Or`. Da `b1` und `b2` haben jetzt drei mögliche Werte sind neun Kombinationen auszuwerten.  
  
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
  
 Wenn der Wert von booleschen Variablen oder Ausdrücken ist `Nothing`, es ist weder `true` noch `false`. Betrachten Sie das folgende Beispiel.  
  
 [!code-vb[VbVbalrNullableValue&6;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]  
  
 In diesem Beispiel `b1 And b2` ergibt `Nothing`. Daher die `Else` -Klausel ausgeführt wird, in den einzelnen `If` -Anweisung und die Ausgabe lautet wie folgt:  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  `AndAlso`und `OrElse`, verwenden kurzschlussauswertung muss ihrer zweiten Operanden ausgewertet werden, wenn die erste ergibt `Nothing`.  
  
## <a name="propagation"></a>Weitergabe  
 Eine oder beide der Operanden eine Arithmetik, Vergleich, UMSCHALT oder Vorgang vom Typ ist NULL-Werte zulässt, das Ergebnis des Vorgangs auch NULL-Werte zulässt. Wenn beide Operanden Werte verfügen, die nicht `Nothing`, der Vorgang erfolgt auf die zugrunde liegenden Werte der Operanden, als wäre keine kein Werttyp ist. Im folgenden Beispiel werden die Variablen `compare1` und `sum1` sind implizit typisiert. Wenn Sie den Mauszeiger darüber bewegen, sehen Sie sich, dass der Compiler für beide Typen ableitet.  
  
 [!code-vb[VbVbalrNullableValue&#7;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]  
  
 Wenn einer oder beide Operanden den Wert haben `Nothing`, das Ergebnis `Nothing`.  
  
 [!code-vb[VbVbalrNullableValue&#8;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]  
  
## <a name="using-nullable-types-with-data"></a>Verwenden von auf NULL festlegbaren Typen mit Daten  
 Eine Datenbank ist eine der wichtigsten Anwendungsmöglichkeiten für auf NULL festlegbare Typen. Nicht alle Datenbankobjekte unterstützen gegenwärtig auf NULL festlegbare Typen, aber führen Sie den vom Designer generierten TableAdapter. Siehe "TableAdapter-Unterstützung für auf NULL festlegbare Typen" in [Übersicht über TableAdapters](https://docs.microsoft.com/visualstudio/data-tools/tableadapter-overview).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.InvalidOperationException></xref:System.InvalidOperationException>   
 <xref:System.Nullable%601.HasValue%2A></xref:System.Nullable%601.HasValue%2A>   
 [Verwenden von auf NULL festlegbaren Typen](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)   
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Übersicht über TableAdapters](https://docs.microsoft.com/visualstudio/data-tools/tableadapter-overview)   
 [Wenn Operator](../../../../visual-basic/language-reference/operators/if-operator.md)   
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)
