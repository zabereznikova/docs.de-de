---
title: value (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: 1e120d68fc4a42f24feb225f652c14525fde3d71
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521145"
---
# <a name="value-c-reference"></a>value (C#-Referenz)
Das kontextabhängige Schlüsselwort `value` wird im Set-Accessor in normalen Eigenschaftendeklarationen verwendet. Es ähnelt einem Eingabeparameter einer Methode. Das Wort `value` verweist auf den Wert, den Clientcode der Eigenschaft zuweisen möchte. Im folgenden Beispiel verfügt `MyDerivedClass` über eine Eigenschaft mit dem Namen `Name`, die den Parameter `value` verwendet, um dem Unterstützungsfeld `name` eine neue Zeichenfolge zuzuweisen. Aus Sicht des Clientcodes ist der Vorgang als einfache Zuweisung geschrieben.  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]  
  
 Weitere Informationen zur Verwendung von `value` finden Sie unter [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md).  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)
