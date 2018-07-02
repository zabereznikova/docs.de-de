---
title: Nullable-Typen (C#-Programmierhandbuch)
ms.date: 05/15/2017
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: 64b326b82cd022ed6590a232546690e2ec2a5c78
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105487"
---
# <a name="nullable-types-c-programming-guide"></a>Nullable-Typen (C#-Programmierhandbuch)
Auf NULL festlegbare Typen sind Instanzen der <xref:System.Nullable%601?displayProperty=nameWithType>-Struktur. Ein Nullable-Typ kann den richtigen Bereich an Werten für den zugrunde liegenden Werttyp plus einen zusätzlichen `null`-Wert darstellen. Einem `Nullable<Int32>` (ausgesprochen „Nullable von Int32“) kann jeder Wert im Bereich von -2147483648 bis 2147483647 oder ein `null`-Wert zugewiesen werden. Einem `Nullable<bool>` können die Werte [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) oder [null](../../../csharp/language-reference/keywords/null.md) zugewiesen werden. Die Möglichkeit, `null` zu numerischen und booleschen Typen zuzuweisen, ist besonders nützlich, wenn Sie mit Datenbanken und anderen Datentypen mit Elementen arbeiten, denen möglicherweise kein Wert zugewiesen wurde. Ein boolesches Feld in einer Datenbank kann beispielsweise die Werte `true` oder `false` speichern oder nicht definiert sein. 
  
[!code-csharp[nullable-types](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]  
  
Weitere Beispiele finden Sie unter [Verwenden von Nullable-Typen](../../../csharp/programming-guide/nullable-types/using-nullable-types.md).  
  
## <a name="nullable-types-overview"></a>Übersicht über Nullable-Typen  
 Nullable-Typen weisen die folgenden Eigenschaften auf:  
  
-   Nullable-Typen stellen Werttypvariablen dar, denen der Wert `null` zugewiesen werden kann. Sie können keinen Nullable-Typ basierend auf einem Verweistyp erstellen. (Verweistypen unterstützen immer den `null`-Wert.)  
  
-   Die Syntax `T?` ist die Kurzform für <xref:System.Nullable%601>, wobei `T` ein Werttyp ist. Die beiden Formen sind austauschbar.  
  
-   Sie weisen einem Nullable-Typ einen Wert genauso zu, wie Sie es für einen regulären Werttyp tun würden, z.B. `int? x = 10;` oder `double? d = 4.108;`. Einem Nullable-Typ kann auch der Wert `null`: `int? x = null;` zugewiesen werden.  
  
-   Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType>-Methode, um entweder den zugewiesenen Wert oder den Standardwert für den zugrunde liegenden Typ zurückzugeben, wenn der Wert `null` ist, z.B. `int j = x.GetValueOrDefault();`  
  
-   Verwenden Sie die schreibgeschützten Eigenschaften <xref:System.Nullable%601.HasValue%2A> und <xref:System.Nullable%601.Value%2A>, um auf NULL zu prüfen und den Wert abzurufen, wie im folgenden Beispiel gezeigt: `if(x.HasValue) j = x.Value;`  
  
    -   Die Eigenschaft `HasValue` gibt `true` zurück, wenn die Variable einen Wert enthält, oder sie gibt `false` zurück, wenn die Variable `null` ist.  
  
    -   Die Eigenschaft `Value` gibt einen Wert zurück, sofern einer zugewiesen ist. Andernfalls wird eine <xref:System.InvalidOperationException?displayProperty=nameWithType> ausgelöst.  
  
    -   Der Standardwert für `HasValue` lautet `false`. Die Eigenschaft `Value` hat keinen Standardwert.  
  
    -   Sie können auch die Operatoren `==` und `!=` mit einem Nullable-Typ verwenden, wie im folgenden Beispiel gezeigt: `if (x != null) y = x;`  
  
-   Verwenden Sie den Operator `??`, um einen Standardwert zuzuweisen, der angewendet wird, wenn ein Nullable-Typ, dessen aktueller Wert`null` lautet, einem Nicht-Nullable-Typ zugewiesen wird, z.B.: `int? x = null; int y = x ?? -1;`  
  
-   Geschachtelte Nullable-Typen sind nicht zulässig. Die folgende Zeile wird nicht kompiliert: `Nullable<Nullable<int>> n;`  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Weitere Informationen finden Sie unter:   
  
-   [Verwenden von Typen mit Nullwert](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [Boxing von Typen mit Nullwerten](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [?? Operator](../../../csharp/language-reference/operators/null-coalescing-operator.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Nullable>  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#](../../../csharp/index.md)  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/) (Was bedeutet „Lifted“ genau?)
