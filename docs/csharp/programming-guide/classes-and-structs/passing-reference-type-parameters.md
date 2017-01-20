---
title: "&#220;bergeben von Verweistypparametern (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Methodenparameter [C#], Verweistypen"
  - "Parameter [C#], Referenz"
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &#220;bergeben von Verweistypparametern (C#-Programmierhandbuch)
In einer [Verweistypvariablen](../../../csharp/language-reference/keywords/reference-types.md) sind keine Daten, sondern ist lediglich ein Verweis auf die Daten enthalten.  Wenn Sie einen Verweistypparameter als Wert übergeben, können Sie die Daten ändern, auf die verwiesen wird, z. B. den Wert eines Klassenmembers.  Der Wert des Verweises selbst kann jedoch nicht geändert werden, d. h., es ist nicht möglich, mit ein und demselben Verweis Speicher für eine neue Klasse zu belegen und gleichzeitig den Wert zu ändern, sodass die Änderung außerhalb des Blocks Bestand hat.  Zu diesem Zweck muss der Parameter mit dem [ref](../../../csharp/language-reference/keywords/ref.md)\-Schlüsselwort oder dem [out](../../../csharp/language-reference/keywords/out.md)\-Schlüsselwort übergeben werden.  Der Einfachheit halber wird in den folgenden Beispielen `ref` verwendet.  
  
## Übergeben von Verweistypen als Wert  
 Im folgenden Beispiel wird der `arr`\-Verweistypparameter der `Change`\-Methode als Wert übergeben.  Da es sich bei dem Parameter um einen Verweis auf `arr` handelt, können die Werte der Arrayelemente geändert werden.  Der Versuch, den Parameter einer neuen Speicheradresse zuzuweisen, wirkt sich jedoch nur innerhalb der Methode aus und hat keinen Einfluss auf die ursprüngliche Variable `arr`.  
  
 [!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-para_1.cs)]  
  
 Im vorangegangenen Beispiel wird das Array `arr`, bei dem es sich um einen Verweistyp handelt, ohne den `ref`\-Parameter an die Methode übergeben.  In diesem Fall wird eine Kopie des Verweises, der auf `arr` zeigt, an die Methode übergeben.  Die Ausgabe zeigt, dass der Inhalt eines Arrayelements durch die Methode geändert werden kann, in diesem Fall von `1` bis `888`.  Da unter Verwendung des Operators [new](../../../csharp/language-reference/keywords/new.md) innerhalb der `Change`\-Methode ein neuer Speicherbereich belegt wird, verweist die Variable `pArray` jedoch auf ein neues Array.  Alle später vorgenommenen Änderungen haben daher keinen Einfluss auf das ursprüngliche Array `arr`, das innerhalb von `Main` erstellt wird.  Tatsächlich werden in diesem Beispiel zwei Arrays erstellt, das eine in `Main` und das andere in der `Change`\-Methode.  
  
## Übergeben von Verweistypen als Verweis  
 Das folgende Beispiel entspricht dem vorhergehenden Beispiel, mit der Ausnahme, dass das `ref`\-Schlüsselwort wird dem Header und der Aufruf Methoden hinzugefügt.  Alle Änderungen, die im Methoden affekt die ursprüngliche Variable im aufrufenden Programm stattfinden.  
  
 [!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-para_2.cs)]  
  
 Alle Änderungen, die innerhalb der Methode vorgenommen werden, haben Einfluss auf das ursprünglichen Array in `Main`.  Das ursprüngliche Array wird eigentlich mithilfe des Operators `new` neu zugeordnet.  Nach dem Aufrufen der `Change`\-Methode zeigt daher jeder Verweis auf `arr` auf das aus fünf Elementen bestehende Array, das in der `Change`\-Methode erstellt wird.  
  
## Vertauschen zweier Zeichenfolgen  
 Das Vertauschen von Zeichenfolgen ist ein gutes Beispiel dafür, wie Verweistypparameter als Verweis übergeben werden.  Im vorliegenden Beispiel werden zwei Zeichenfolgen, `str1` und `str2`, in `Main` initialisiert und als Parameter, die durch das `ref`\-Schlüsselwort geändert wurden, an die `SwapStrings`\-Methode übergeben.  Die beiden Zeichenfolgen werden sowohl innerhalb der Methode als auch innerhalb von `Main` vertauscht.  
  
 [!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-para_3.cs)]  
  
 In diesem Beispiel müssen die Parameter als Verweis übergeben werden, damit sich der Vorgang auf die Variablen im aufrufenden Programm auswirkt.  Wenn Sie das `ref`\-Schlüsselwort sowohl aus dem Header als auch aus dem Aufruf der Methode entfernen, werden im aufrufenden Programm keine Änderungen vorgenommen.  
  
 Weitere Informationen über Zeichenfolgen finden Sie unter [Zeichenfolgen](../../../csharp/language-reference/keywords/string.md).  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Übergeben von Parametern](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)   
 [Übergeben von Arrays mithilfe von "ref" und "out"](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
 [ref](../../../csharp/language-reference/keywords/ref.md)   
 [Verweistypen](../../../csharp/language-reference/keywords/reference-types.md)