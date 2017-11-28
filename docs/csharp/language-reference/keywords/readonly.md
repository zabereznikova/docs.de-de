---
title: readonly (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords: readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b499f9fc5121afe6c2e92bcf8c5d2ac593b4c06c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="readonly-c-reference"></a>readonly (C#-Referenz)
Das Schlüsselwort `readonly` ist ein Modifizierer, den Sie für Felder verwenden können. Wenn eine Felddeklaration einen `readonly`-Modifizierer enthält, können Zuweisungen an die Felder, die von der Deklaration eingeführt wurden, nur als Teil der Deklaration oder in einem Konstruktor in derselben Klasse auftreten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel kann der Wert des Felds `year` nicht zur Methode `ChangeYear` geändert werden, obwohl ihm im Klassenkonstruktor ein Wert zugewiesen ist:  
  
 [!code-csharp[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 Sie können einem `readonly`-Feld nur in den folgenden Kontexten einen Wert zuweisen:  
  
-   Wenn die Variable in der Deklaration initialisiert ist, z.B.:  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   Für ein Instanzenfeld, in den Instanzkonstruktoren der Klasse, die die Felddeklaration enthält oder für ein statisches Feld im statischen Konstruktor der Klasse, die die Felddeklaration enthält. Hierbei handelt es sich auch um die einzigen Kontexte, in denen es gültig ist, ein `readonly`-Feld als [out](../../../csharp/language-reference/keywords/out.md) oder [ref](../../../csharp/language-reference/keywords/ref.md)-Parameter zu übergeben.  
  
> [!NOTE]
>  Das Schlüsselwort `readonly` unterscheidet sich vom Schlüsselwort [const](../../../csharp/language-reference/keywords/const.md). Ein `const`-Feld kann nur bei der Deklaration des Felds initialisiert werden. Ein `readonly`-Feld kann entweder bei der Deklaration oder in einem Konstruktor initialisiert werden. Daher können `readonly`-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen. Außerdem ist ein `const`-Feld eine Kompilierzeitkonstante, während ein `readonly`-Feld wie im folgenden Beispiel für Laufzeitkonstanten verwendet werden kann:  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 Im vorherigen Beispiel, wenn Sie eine Anweisung wie folgt verwenden:  
  
 `p2.y = 66;        // Error`  
  
 erhalten Sie die Compilerfehlermeldung:  
  
 `The left-hand side of an assignment must be an l-value`  
  
 Es handelt sich um den gleichen Fehler, den Sie erhalten, wenn Sie versuchen, einen Wert einer Konstanten zuzuweisen.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)  
 [const](../../../csharp/language-reference/keywords/const.md)  
 [Felder](../../../csharp/programming-guide/classes-and-structs/fields.md)
