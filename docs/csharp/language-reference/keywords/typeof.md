---
title: "typeof (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "typeof"
  - "typeof_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "typeof-Schlüsselwort [C#]"
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# typeof (C#-Referenz)
Wird verwendet, um das `System.Type`\-Objekt für einen Typ zu erhalten.  Der `typeof`\-Ausdruck nimmt folgende Form an:  
  
```  
System.Type type = typeof(int);  
```  
  
## Hinweise  
 Um den Laufzeittyp eines Ausdrucks abzurufen, kann die <xref:System.Object.GetType%2A>\-Methode von .NET Framework verwendet werden, wie im folgenden Beispiel gezeigt:  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 Der Operator `typeof` kann nicht überladen werden.  
  
 Der Operator `typeof` kann auch bei offenen generischen Typen verwendet werden.  Typen mit mehr als einem Parameter müssen die entsprechende Anzahl Kommas in der Spezifikation aufweisen.  Im folgenden Beispiel wird gezeigt, wie ermittelt wird, ob der Rückgabetyp einer Methode ein generischer <xref:System.Collections.Generic.IEnumerable%601>\-Typ ist.  Angenommen, diese Methode ist eine Instanz eines MethodInfo\-Typs:  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## Beispiel  
 [!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## Beispiel  
 In diesem Beispiel wird die <xref:System.Object.GetType%2A>\-Methode verwendet, um den Typ zu ermitteln, der das Ergebnis der numerischen Berechnung enthält.  Dies hängt von den Speicheranforderungen der resultierenden Zahl ab.  
  
 [!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.Type?displayProperty=fullName>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)