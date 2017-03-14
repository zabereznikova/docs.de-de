---
title: "sizeof (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "sizeof_CSharpKeyword"
  - "sizeof"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "sizeof-Schlüsselwort [C#]"
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# sizeof (C#-Referenz)
Wird verwendet, um für einen nicht verwalteten Typ die Größe in Bytes zu erhalten.  Zu den nicht verwalteten Typen gehören die integrierten Datentypen in der nachfolgenden Tabelle sowie die folgenden:  
  
-   Enumerationstypen  
  
-   Zeigertypen  
  
-   Benutzerdefinierte Strukturen ohne Felder oder Eigenschaften, die Verweistypen darstellen.  
  
 Im folgenden Beispiel wird veranschaulicht, wie die Größe eines `int`\-Typs abgerufen wird:  
  
```c#  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## Hinweise  
 Ab Version 2.0 von C\# ist der [unsafe](../../../csharp/language-reference/keywords/unsafe.md)\-Modus für die Anwendung von `sizeof` auf integrierte Typen nicht mehr erforderlich.  
  
 Der Operator `sizeof` kann nicht überladen werden.  Die vom Operator `sizeof` zurückgegebenen Werte sind vom Typ `int`.  In der folgenden Tabelle werden die konstanten Werte angezeigt, die durch `sizeof`\-Ausdrücke mit bestimmten integrierten Datentypen als Operanden ersetzt werden.  
  
|Ausdruck|Konstantenwert|  
|--------------|--------------------|  
|`sizeof(sbyte)`|1|  
|`sizeof(byte)`|1|  
|`sizeof(short)`|2|  
|`sizeof(ushort)`|2|  
|`sizeof(int)`|4|  
|`sizeof(uint)`|4|  
|`sizeof(long)`|8|  
|`sizeof(ulong)`|8|  
|`sizeof(char)`|2 \(Unicode\)|  
|`sizeof(float)`|4|  
|`sizeof(double)`|8|  
|`sizeof(decimal)`|16|  
|`sizeof(bool)`|1|  
  
 Für alle Typen einschließlich Strukturen kann der Operator `sizeof` nur in nicht sicheren Codeblocks verwendet werden.  Sie können zwar die <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName>\-Methode verwenden, jedoch stimmt der von dieser Methode zurückgegebene Wert nicht immer mit dem Wert überein, der von `sizeof` zurückgegeben wird.  <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> gibt die Größe des Typs nach dem Marshalling zurück. `sizeof` hingegen gibt die Größe des Typs nach Zuweisung durch die Common Language Runtime einschließlich Leerspeicher zurück.  
  
## Beispiel  
 [!code-cs[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [enum](../../../csharp/language-reference/keywords/enum.md)   
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [Konstanten](../../../csharp/programming-guide/classes-and-structs/constants.md)