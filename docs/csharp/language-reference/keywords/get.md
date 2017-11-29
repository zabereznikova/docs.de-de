---
title: get (C#-Referenz)
ms.date: 03/10/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- get_CSharpKeyword
- get
helpviewer_keywords: get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a2e8426e5c5be16be0114b5ccc66f30793ce7dda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="get-c-reference"></a>get (C#-Referenz)

Das Schlüsselwort `get` definiert eine *Accessor*methode in einer Eigenschaft oder einem Indexer, die den Eigenschaftswert oder das Indexer-Element zurückgibt. Weitere Informationen finden Sie unter [Properties (Eigenschaften)](../../../csharp/programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties (Automatisch implementierte Eigenschaften)](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) und [Indexers (Indexer)](../../../csharp/programming-guide/indexers/index.md).  
  
Im folgenden Beispiel werden ein `get`- und ein `set`-Accessor für eine Eigenschaft namens `Seconds` definiert. Im Beispiel wird ein privates Feld mit dem Namen `_seconds` verwendet, um den Eigenschaftswert zu unterstützen.  
 
 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
Der `get`-Accessor besteht häufig aus einer einzelnen Anweisung, die einen Wert zurückgibt (wie im vorherigen Beispiel gezeigt). Beginnend mit dem C# 7, können sie den `get`-Accessor als Ausdruckskörpermember implementieren. Im folgenden Beispiel wird sowohl der `get`- als auch der `set`-Accessor als Ausdruckskörpermember implementiert.

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
 
In einfachen Fällen, in denen der `get`- und der `set`-Accessor einer Eigenschaft nichts anderes durchführen als das Festlegen oder Abrufen eines Wertes in einem privaten Unterstützungsfeld, können Sie die Vorteile der Unterstützung von automatisch implementierten Eigenschaften durch einen C#-Compiler nutzen. Im folgenden Beispiel wird `Hours` als automatisch implementierte Eigenschaft implementiert. 
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C# Keywords (C#-Schlüsselwörter)](../../../csharp/language-reference/keywords/index.md) [Properties (Eigenschaften)](../../../csharp/programming-guide/classes-and-structs/properties.md)
