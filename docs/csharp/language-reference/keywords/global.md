---
title: Kontextabhängiges global-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- global
- global_CSharpKeyword
helpviewer_keywords:
- global keyword [C#]
ms.assetid: 8932c16a-6959-42c2-86e7-2c4221ab788b
ms.openlocfilehash: 9a8c7b5134cc29668aae53e8a3f86ddae4c8263a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627682"
---
# <a name="global-c-reference"></a>global (C#-Referenz)

Wenn das Kontextschlüsselwort `global` dem [Operator „::“](../operators/namespace-alias-qualifier.md) vorangestellt ist, verweist es auf den globalen Namespace. Dabei handelt es sich um den Standardnamespace für alle C#-Programme, der ansonsten unbenannt ist. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des globalen Namespacealias](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie mit dem Kontextschlüsselwort `global` angegeben wird, dass die Klasse `TestApp` im globalen Namespace definiert ist:

[!code-csharp[csrefKeywordsContextual#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#13)]

## <a name="see-also"></a>Siehe auch

- [Namespaces](../../programming-guide/namespaces/index.md)
