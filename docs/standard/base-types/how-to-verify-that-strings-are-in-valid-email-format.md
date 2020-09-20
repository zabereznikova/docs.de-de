---
title: 'Gewusst wie: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen'
description: In diesem Artikel sehen Sie anhand eines Beispiels, wie ein regulärer Ausdruck in .NET überprüft, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen.
ms.date: 06/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- user input, examples
- Regex.IsMatch method
- regular expressions [.NET Framework], examples
- examples [Visual Basic], strings
- IsValidEmail
- validation, email strings
- input, checking
- strings [.NET Framework], examples [Visual Basic]
- email [.NET Framework], validating
- IsMatch method
ms.assetid: 7536af08-4e86-4953-98a1-a8298623df92
ms.openlocfilehash: 90e79af649727330c2afa1ccb8c64ffe34733f92
ms.sourcegitcommit: 6d4ee46871deb9ea1e45bb5f3784474e240bbc26
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2020
ms.locfileid: "90022947"
---
# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a>Gewusst wie: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen

Im folgenden Beispiel wird mit einem regulären Ausdruck geprüft, ob eine Zeichenfolge ein gültiges E-Mail-Format aufweist.

Im Vergleich dazu, was tatsächlich als E-Mail-Adresse verwendet werden kann, ist dieser reguläre Ausdruck einfach. Die Verwendung eines regulären Ausdrucks zum Überprüfen einer E-Mail-Adresse ist nützlich, um sicherzustellen, dass die Struktur einer E-Mail-Adresse korrekt ist. Sie ist allerdings kein Ersatz für die Überprüfung der tatsächlichen Existenz einer E-Mail-Adresse.

✔️ VERWENDEN SIE einen einfachen regulären Ausdruck, um die Struktur einer E-Mail-Adresse zu überprüfen.

✔️ SENDEN SIE eine Test-E-Mail an die von einem Benutzer Ihrer App angegebene Adresse.

❌ Verwenden Sie einen regulären Ausdruck NICHT als einzige Methode zum Überprüfen einer E-Mail-Adresse.

Wenn Sie versuchen, den _perfekten_ regulären Ausdruck zum Überprüfen der korrekten Struktur einer E-Mail-Adresse zu erstellen, wird dieser Ausdruck so komplex, dass es äußerst schwierig wird, ihn zu debuggen oder zu verbessern. Reguläre Ausdrücke können nicht überprüfen, ob eine E-Mail-Adresse existiert, auch wenn sie richtig strukturiert ist. Die beste Möglichkeit, eine E-Mail-Adresse zu überprüfen, ist das Senden einer Test-E-Mail an diese Adresse.

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a>Beispiel

Im Beispiel wird eine Methode `IsValidEmail` definiert, die `true` zurückgibt, wenn die Zeichenfolge eine gültige E-Mail-Adresse enthält, und `false`, wenn nicht. Sie führt jedoch keine weitere Aktion aus.

Um die Gültigkeit der E-Mail-Adresse zu überprüfen ruft die `IsValidEmail` -Methode die <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> -Methode mit dem regulären Ausdruck `(@)(.+)$` auf, um den Domänennamen von der E-Mail-Adresse zu trennen. Der dritte Parameter ist ein <xref:System.Text.RegularExpressions.MatchEvaluator> -Delegat, der die Methode darstellt, die den gefundenen Text verarbeitet und ersetzt. Das Muster des regulären Ausdrucks wird wie folgt interpretiert:

| Muster | Beschreibung                                                                         |
|---------|-------------------------------------------------------------------------------------|
| `(@)`   | Das @ Zeichen wird als Übereinstimmung verwendet. Dieser Teil stellt die erste Erfassungsgruppe dar.                           |
| `(.+)`  | Ein- oder mehrmalige Übereinstimmung mit beliebigem Zeichen. Dieser Teil stellt die zweite Erfassungsgruppe dar. |
| `$`     | Beendet die Suche am Ende der Zeichenfolge.                                             |

Der Domänenname wird zusammen mit dem @ Zeichen der `DomainMapper` -Methode übergeben, die die <xref:System.Globalization.IdnMapping> -Klasse verwendet, um Unicode-Zeichen in ihre Punycode-Entsprechungen zu übersetzen, die außerhalb des 7-Bit-ASCII-Zeichenbereichs liegen. Darüber hinaus wird die Methode auch das `invalid` -Flag auf `True` fest, wenn die <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> -Methode ein unzulässiges Zeichen im Domänennamen erkennt. Diese Methode gibt den Punycode-Domänennamen, der dem @ Zeichen vorangestellt ist, an die `IsValidEmail` -Methode zurück.

> [!TIP]
> Es wird empfohlen, dass Sie einen einfachen regulären Ausdruck mit dem Muster `(@)(.+)$` verwenden, um die Domäne zu normalisieren und dann einen Wert zurückzugeben, der angibt, ob die Adresse der Überprüfung standgehalten hat oder nicht. Im Beispiel in diesem Artikel werden jedoch weitere Möglichkeiten beschrieben, wie Sie einen regulären Ausdruck zur Überprüfung der E-Mail-Adresse verwenden können. Unabhängig davon, wie Sie eine E-Mail-Adresse überprüfen, sollten Sie immer eine Test-E-Mail an die Adresse senden, um sicherzustellen, dass diese existiert.

Die `IsValidEmail`-Methode ruft dann die <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType>-Methode auf, um zu überprüfen, ob die Adresse dem Muster eines regulären Ausdrucks entspricht.

Die Methode `IsValidEmail` überprüft lediglich, ob das Format der E-Mail-Adresse gültig ist. Sie überprüft nicht, ob die E-Mail-Adresse existiert. Außerdem überprüft die Methode `IsValidEmail` nicht, ob es sich bei dem Domänennamen der obersten Ebene um einen gültigen Domänennamen handelt, der in der [IANA Root Zone Database](https://www.iana.org/domains/root/db) aufgeführt ist, was einen Suchvorgang erfordern würde.

:::code language="csharp" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/csharp/RegexUtilities.cs":::

:::code language="vb" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/vb/RegexUtilities.vb":::

In diesem Beispiel kann das Muster des regulären Ausdrucks `^[^@\s]+@[^@\s]+\.[^@\s]+$` wie in der folgenden Tabelle dargestellt interpretiert werden. Der reguläre Ausdruck wird mit dem Flag <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> kompiliert.

| Muster   | BESCHREIBUNG                                                                              |
|-----------|------------------------------------------------------------------------------------------|
| `^`       | Starten Sie den Vergleich am Beginn der Zeichenfolge.                                              |
| `[^@\s]+` | Überprüfung der einmaligen oder mehrmaligen Verwendung eines beliebigen Zeichens bis auf das @-Zeichen und das Leerzeichen |
| `@`       | Das @ Zeichen wird als Übereinstimmung verwendet.                                                                   |
| `[^@\s]+` | Überprüfung der einmaligen oder mehrmaligen Verwendung eines beliebigen Zeichens bis auf das @-Zeichen und das Leerzeichen |
| `\.`      | Überprüfung der Verwendung eines einzelnen Punkts                                                         |
| `[^@\s]+` | Überprüfung der einmaligen oder mehrmaligen Verwendung eines beliebigen Zeichens bis auf das @-Zeichen und das Leerzeichen |
| `$`       | Beendet die Suche am Ende der Zeichenfolge.                                                  |

> [!IMPORTANT]
> Dieser reguläre Ausdruck soll nicht jeden Aspekt einer gültigen E-Mail-Adresse abdecken. Er wird vielmehr als Beispiel bereitgestellt, das Sie nach Bedarf erweitern können.

## <a name="see-also"></a>Siehe auch

- [Reguläre Ausdrücke von .NET Framework](regular-expressions.md)
- [How far should one take e-mail address validation? (Wie weit sollte man bei der Überprüfung von E-Mail-Adressen gehen?)](https://softwareengineering.stackexchange.com/questions/78353/how-far-should-one-take-e-mail-address-validation#78363)
