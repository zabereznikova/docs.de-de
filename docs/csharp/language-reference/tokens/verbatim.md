---
description: '@ – C#-Referenz'
title: '@ – C#-Referenz'
ms.date: 02/09/2017
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
ms.openlocfilehash: 7d78b28479ed6128321207073dc94976710f10b6
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138903"
---
# <a name="-c-reference"></a>@ (C#-Referenz)

Das Sonderzeichen `@` dient als ausführlicher Bezeichner. Er wird wie folgt verwendet:

1. Zum Aktivieren von C#-Schlüsselwörtern, die als Bezeichner verwendet werden sollen. Das Zeichen `@` steht vor einem Codeelement, das der Compiler als Bezeichner und nicht als C#-Schlüsselwort interpretieren soll. Im folgenden Beispiel wird das Zeichen `@` zum Definieren eines Bezeichners mit dem Namen `for` verwendet, der in einer `for`-Schleife verwendet wird.

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. Zum Angeben, dass ein Zeichenfolgenliteral wörtlich interpretiert werden soll. Das Zeichen `@` in dieser Instanz definiert ein *ausführliches Zeichenfolgenliteral*. Einfache Escapesequenzen (z.B. `"\\"` für einen umgekehrten Schrägstrich), Escapesequenzen für Hexadezimalzahlen (z.B. `"\x0041"` für ein groß geschriebenes A) und Escapesequenzen für Unicodezeichen (wie z.B. `"\u0041"` für ein groß geschriebenes A) werden wörtlich interpretiert. Nur eine Escapesequenz für Anführungszeichen (`""`) wird nicht wörtlich interpretiert, sie erzeugt ein doppeltes Anführungszeichen. Bei einer ausführlichen [interpolierten Zeichenfolge](interpolated.md) werden darüber hinaus Klammern als Escapesequenzen (`{{` und `}}`) nicht wörtlich interpretiert. In diesem Fall werden einfache geschweifte Klammerzeichen erzeugt. Im folgenden Beispiel werden zwei identische Dateipfade definiert – einer durch Verwendung eines regulären Zeichenfolgenliterals und der andere durch ein ausführliches Zeichenfolgenliteral. Dies ist einer der häufigeren Verwendungsarten von ausführlichen Zeichenfolgenliteralen.

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   Im folgenden Beispiel werden die Auswirkungen des Definierens eines regulären Zeichenfolgenliterals und eines ausführlichen Zeichenfolgenliterals mit identischen Zeichensequenzen dargestellt.

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. Zum Zulassen, dass der Compiler im Fall eines Namenskonflikts zwischen Attributen unterscheiden kann. Ein Attribut ist eine von <xref:System.Attribute> abgeleitete Klasse. Der Name des Typs enthält normalerweise das Suffix **Attribute**, obwohl der Compiler diese Konvention nicht erzwingt. Auf das Attribut kann dann im Code entweder über den vollständigen Typnamen (z.B. `[InfoAttribute]`) oder über den gekürzten Namen (z.B. `[Info]`) verwiesen werden. Allerdings tritt ein Namenskonflikt auf, wenn zwei gekürzte Typnamen des Attributs identisch sind und ein Typname das Suffix **Attribute** enthält, der andere jedoch nicht. Der folgende Code kann z.B. nicht kompiliert werden, da der Compiler nicht bestimmen kann, ob das Attribut `Info` oder `InfoAttribute` auf die Klasse `Example` angewendet wird. Weitere Informationen finden Sie unter [CS1614](../compiler-messages/cs1614.md).

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim2.cs#1)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Sonderzeichen](./index.md)
