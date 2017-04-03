---
title: sizeof (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
dev_langs:
- CSharp
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: 20
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7a1944caceaba3ffb8d83a8f67e5ef2975bf9644
ms.lasthandoff: 03/13/2017

---
# <a name="sizeof-c-reference"></a>sizeof (C#-Referenz)
Wird verwendet, um die Größe eines nicht verwalteten Typs in Bytes abzurufen. Nicht verwaltete Typen umfassen die in der unteren Tabelle aufgelisteten integrierten Typen sowie folgende Typen:  
  
-   Enumerationstypen  
  
-   Zeigertypen  
  
-   Benutzerdefinierte Strukturen, die keine Felder oder Eigenschaften enthalten, die Verweistypen sind  
  
 Im folgenden Beispiel wird gezeigt, wie Sie die Größe von `int` abrufen:  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a>Hinweise  
 Ab C# Version 2.0 muss für das Anwenden von `sizeof` auf integrierte Typen nicht länger der Modus [unsafe](../../../csharp/language-reference/keywords/unsafe.md) (unsicher) verwendet werden.  
  
 Der Operator `sizeof` kann nicht überladen werden. Die Rückgabewerte des Operators `sizeof` sind vom Typ `int`. Die folgende Tabelle zeigt die konstanten Werte, die als Ersatz für `sizeof`-Ausdrücke dienen, die über bestimmte integrierte Typen als Operanden verfügen.  
  
|Ausdruck|Konstanter Wert|  
|----------------|--------------------|  
|`sizeof(sbyte)`|1|  
|`sizeof(byte)`|1|  
|`sizeof(short)`|2|  
|`sizeof(ushort)`|2|  
|`sizeof(int)`|4|  
|`sizeof(uint)`|4|  
|`sizeof(long)`|8|  
|`sizeof(ulong)`|8|  
|`sizeof(char)`|2 (Unicode)|  
|`sizeof(float)`|4|  
|`sizeof(double)`|8|  
|`sizeof(decimal)`|16|  
|`sizeof(bool)`|1|  
  
 Bei allen anderen Typen, darunter Strukturen, kann der Operator `sizeof` nur in unsicheren Codeblöcken zugelassen werden. Sie können die Methode <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> zwar verwenden, der von dieser Methode zurückgegebene Wert entspricht allerdings nicht immer dem von `sizeof` zurückgegeben Wert. <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> gibt die Größe nach dem Marshalling des Typs zurück, während `sizeof` die Größe inklusive Abständen zurückgibt, die von der Common Language Runtime zugeordnet wurde.  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Operator Keywords (Operatorschlüsselwörter)](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [enum](../../../csharp/language-reference/keywords/enum.md)   
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [Konstanten](../../../csharp/programming-guide/classes-and-structs/constants.md)
