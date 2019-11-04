---
title: Kontextabhängiges value-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: 34b192d17bd96b6b893c9f14f0d4a77274a32f78
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771744"
---
# <a name="value-c-reference"></a>value (C#-Referenz)

Das kontextabhängige Schlüsselwort `value` wird im `set`-Accessor in den Deklarationen [property](../../programming-guide/classes-and-structs/properties.md) und [indexer](../../programming-guide/indexers/index.md) verwendet. Es ähnelt einem Eingabeparameter einer Methode. Das Wort `value` verweist auf den Wert, den Clientcode der Eigenschaft oder dem Indexer zuweisen möchte. Im folgenden Beispiel verfügt `MyDerivedClass` über eine Eigenschaft mit dem Namen `Name`, die den Parameter `value` verwendet, um dem Unterstützungsfeld `name` eine neue Zeichenfolge zuzuweisen. Aus Sicht des Clientcodes ist der Vorgang als einfache Zuweisung geschrieben.

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

Weitere Informationen finden Sie in den Artikeln zu [Eigenschaften](../../programming-guide/classes-and-structs/properties.md) und [Indexern](../../programming-guide/indexers/index.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
