---
title: typeof (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: aff7462f0df938a8e96cca33155489bee4891da0
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "50744443"
---
# <a name="typeof-c-reference"></a>typeof (C#-Referenz)
Wird zum Abrufen des Objekts `System.Type` eines Typs verwendet. Der Ausdruck `typeof` weist folgende Form auf:  
  
```csharp  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a>Hinweise  
 Um den Runtime-Typ eines Ausdrucks zu erhalten, können Sie die .NET Framework-Methode <xref:System.Object.GetType%2A> wie in folgendem Beispiel verwenden:  
  
```csharp  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 Operator `typeof` kann nicht überladen werden.  
  
 Der Operator `typeof` kann auch bei offenen generischen Typen verwendet werden. Typen mit mehr als einem Parameter müssen die entsprechende Anzahl von Kommas in der Spezifikation haben. Das folgende Beispiel zeigt, wie Sie bestimmen, ob der Rückgabetyp einer Methode ein generischer <xref:System.Collections.Generic.IEnumerable%601> ist. <xref:System.Type.GetInterface%2A?displayProperty=nameWithType> gibt `null` zurück, wenn der Rückgabetyp kein generischer <xref:System.Collections.Generic.IEnumerable%601>-Typ ist.
  
 [!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]   
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Object.GetType%2A>-Methode um den Typ zu bestimmen, der verwendet wird, um das Ergebnis einer numerischen Berechnung zu speichern. Dies hängt vom Speicherbedarf der resultierenden Zahl ab.  
  
 [!code-csharp[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  

Weitere Informationen finden Sie unter [Der typeof-Operator](~/_csharplang/spec/expressions.md#the-typeof-operator) in der [C#-Sprachspezifikation](../language-specification/index.md). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.
 
## <a name="see-also"></a>Siehe auch

- <xref:System.Type?displayProperty=nameWithType>  
- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
- [is](../../../csharp/language-reference/keywords/is.md)  
- [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)
