---
title: this-Schlüsselwort – C#-Referenz
description: Schlüsselwort „this“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
ms.openlocfilehash: 2a2c487ad93e6fc75ecf95c541e859b8b60bb5b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715110"
---
# <a name="this-c-reference"></a>this (C#-Referenz)

Das Schlüsselwort `this` verweist auf die aktuelle Instanz der Klasse und wird auch als Modifizierer des ersten Parameters einer Erweiterungsmethode verwendet.

> [!NOTE]
> Dieser Artikel behandelt die Verwendung von `this` mit Klasseninstanzen. Weitere Informationen zu seiner Verwendung in Erweiterungsmethoden finden Sie unter [Erweiterungsmethoden](../../programming-guide/classes-and-structs/extension-methods.md).

Häufige Verwendungen von `this` sind wie folgt:

- Zum Qualifizieren von Membern, die durch ähnliche Namen ausgeblendet werden, wie z.B.:

  [!code-csharp[csrefKeywordsAccess#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#4)]  

- Zum Übergeben eines Objekts als ein Parameter an eine andere Methode, wie z.B.:

  ```csharp
  CalcTax(this);
  ```

- Zum Deklarieren von Indexern, wie z.B.:

  [!code-csharp[csrefKeywordsAccess#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#5)]

Statische Memberfunktionen haben keinen `this`-Zeiger, da sie auf Klassenebene und nicht als Teil eines Objekts existieren. Es ist ein Fehler, in einer statischen Methode auf `this` zu verweisen.

## <a name="example"></a>Beispiel

In diesem Beispiel wird `this` verwendet, um die `Employee`-Klassenmember `name` und `alias` zu qualifizieren, die von ähnlichen Namen ausgeblendet werden. Er wird auch verwendet, um ein Objekt an die Methode `CalcTax` zu übergeben, die zu einer anderen Klasse gehört.

[!code-csharp[csrefKeywordsAccess#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#3)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [base](base.md)
- [Methoden](../../programming-guide/classes-and-structs/methods.md)
