---
title: Kontextabhängiges Schlüsselwort „global“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- global
- global_CSharpKeyword
helpviewer_keywords:
- global keyword [C#]
ms.assetid: 8932c16a-6959-42c2-86e7-2c4221ab788b
ms.openlocfilehash: 837245e31a9a795aa2f13cfc6c33fefb6402801d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44217451"
---
# <a name="global-c-reference"></a>global (C#-Referenz)

Wenn das Kontextschlüsselwort `global` dem [Operator „::“](../operators/namespace-alias-qualifer.md) vorangestellt ist, verweist es auf den globalen Namespace. Dabei handelt es sich um den Standardnamespace für alle C#-Programme, der ansonsten unbenannt ist. Weitere Informationen finden Sie unter [How to: Use the Global Namespace Alias (Vorgehensweise: Verwenden des globalen Namespacealias)](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie mit dem Kontextschlüsselwort `global` angegeben wird, dass die Klasse `TestApp` im globalen Namespace definiert ist:

[!code-csharp[csrefKeywordsContextual#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#13)]

## <a name="see-also"></a>Siehe auch

- [Namespaces](../../programming-guide/namespaces/index.md)