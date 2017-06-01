---
title: typeof (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeof
- typeof_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0590aa8a339dc58b7215722a530a71f8973864d4
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="typeof-c-reference"></a>typeof (C#-Referenz)
Wird zum Abrufen des Objekts `System.Type` eines Typs verwendet. Der Ausdruck `typeof` weist folgende Form auf:  
  
```  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können die .NET Framework-Methode <xref:System.Object.GetType%2A> verwenden, um den Laufzeittyp eines Ausdrucks zu erhalten, so wie in folgendem Beispiel:  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 Der Operator `typeof` kann nicht überladen werden.  
  
 Der Operator `typeof` kann auch bei offenen generischen Typen verwendet werden. Typen mit mehr als einem Parameter müssen die entsprechende Anzahl von Kommas in der Spezifikation haben. Das folgende Beispiel zeigt, wie Sie bestimmen, ob der Rückgabetyp einer Methode ein generischer <xref:System.Collections.Generic.IEnumerable%601> ist. Nehmen Sie an, dass die Methode eine Instanz eines MethodInfo-Typs ist:  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die Methode <xref:System.Object.GetType%2A>, um den Typ zu bestimmen, der verwendet wird, um das Ergebnis einer numerischen Berechnung zu speichern. Dies hängt vom Speicherbedarf der resultierenden Zahl ab.  
  
 [!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Type?displayProperty=fullName>   
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)
