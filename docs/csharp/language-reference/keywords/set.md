---
title: set (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- set
- set_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- set keyword [C#]
ms.assetid: 30d7e4e5-cc2e-4635-a597-14a724879619
caps.latest.revision: 14
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
ms.openlocfilehash: 7111483ac2c939830560e8aad61078da5190684a
ms.lasthandoff: 03/13/2017

---
# <a name="set-c-reference"></a>set (C#-Referenz)
Das Schlüsselwort `set` definiert eine *Accessor*-Methode in einer Eigenschaft oder einem Indexer, die der Eigenschaft oder dem Indexer-Element einen Wert zuweist. Weitere Informationen und Beispiele finden Sie unter [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md), [Automatisch implementierte Eigenschaften](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) und [Indexers](../../../csharp/programming-guide/indexers/index.md).  
  
Im folgenden Beispiel werden ein `get`- und ein `set`-Accessor für eine Eigenschaft namens `Seconds` definiert. Im Beispiel wird ein privates Feld mit dem Namen `_seconds` verwendet, um den Eigenschaftswert zu unterstützen.  
 
 [!code-cs[set#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  

Der `set`-Accessor besteht häufig aus einer einzelnen Anweisung, die einen Wert zurückgibt (wie im vorherigen Beispiel gezeigt). Ab C# 7 können sie den `set`-Accessor als Ausdruckskörpermember implementieren. Im folgenden Beispiel wird sowohl der `get`- als auch der `set`-Accessor als Ausdruckskörpermember implementiert.

 [!code-cs[set#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
    
In einfachen Fällen, in denen der `get`- und der `set`-Accessor einer Eigenschaft nichts anderes durchführen als das Festlegen oder Abrufen eines Wertes in einem privaten Unterstützungsfeld, können Sie die Vorteile der Unterstützung von automatisch implementierten Eigenschaften durch einen C#-Compiler nutzen. Im folgenden Beispiel wird `Hours` als automatisch implementierte Eigenschaft implementiert. 
  
 [!code-cs[set#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
    
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)
