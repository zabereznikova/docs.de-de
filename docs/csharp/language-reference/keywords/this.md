---
title: this (C#-Referenz)
description: Schlüsselwort „this“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
ms.openlocfilehash: d26ad1565dc6faf8aba6c971b3a0023bac886775
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="this-c-reference"></a>this (C#-Referenz)
Das Schlüsselwort `this` verweist auf die aktuelle Instanz der Klasse und wird auch als Modifizierer des ersten Parameters einer Erweiterungsmethode verwendet.  
  
> [!NOTE]
>  Dieser Artikel behandelt die Verwendung von `this` mit Klasseninstanzen. Weitere Informationen zu seiner Verwendung in Erweiterungsmethoden finden Sie unter [Erweiterungsmethoden](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
 Häufige Verwendungen von `this` sind wie folgt:  
  
-   Zum Qualifizieren von Membern, die durch ähnliche Namen ausgeblendet werden, wie z.B.:  
  
 [!code-csharp[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]  
  
-   Zum Übergeben eines Objekts als ein Parameter an eine andere Methode, wie z.B.:  
  
    ```  
    CalcTax(this);  
    ```  
  
-   Zum Deklarieren von Indexern, wie z.B.:  
  
 [!code-csharp[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]  
  
 Statische Memberfunktionen haben keinen `this`-Zeiger, da sie auf Klassenebene und nicht als Teil eines Objekts existieren. Es ist ein Fehler, in einer statischen Methode auf `this` zu verweisen.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird `this` verwendet, um die `Employee`-Klassenmember `name` und `alias` zu qualifizieren, die von ähnlichen Namen ausgeblendet werden. Er wird auch verwendet, um ein Objekt an die Methode `CalcTax` zu übergeben, die zu einer anderen Klasse gehört.  
  
 [!code-csharp[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [base](../../../csharp/language-reference/keywords/base.md)  
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)
