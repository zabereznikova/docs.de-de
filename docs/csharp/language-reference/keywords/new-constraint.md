---
title: new-Einschränkung (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 9948fc65030a4636c5d23db4ef8c3a584018d2f5
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087010"
---
# <a name="new-constraint-c-reference"></a>new-Einschränkung (C#-Referenz)

Die `new`-Einschränkung gibt an, dass jedes Typargument in einer generischen Klassendeklaration über einen öffentlichen parameterlosen Konstruktor verfügen muss. Der Typ kann nicht abstrakt sein, um die neue Einschränkung zu verwenden.

## <a name="example"></a>Beispiel

Wenden Sie die `new`-Einschränkung auf einen Typparameter an, wenn Ihre generische Klasse neue Instanzen desselben Typs erstellt, wie im folgenden Beispiel gezeigt wird:

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

## <a name="example"></a>Beispiel

Beim Verwenden der `new()`-Einschränkung mit anderen Einschränkungen muss sie zuletzt angegeben werden:

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../../programming-guide/generics/constraints-on-type-parameters.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic>
- [C#-Referenz](../../language-reference/index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Operatorschlüsselwörter](operator-keywords.md)
- [Generika](../../programming-guide/generics/index.md)