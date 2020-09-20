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
# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a><span data-ttu-id="2beb2-103">Gewusst wie: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen</span><span class="sxs-lookup"><span data-stu-id="2beb2-103">How to verify that strings are in valid email format</span></span>

<span data-ttu-id="2beb2-104">Im folgenden Beispiel wird mit einem regulären Ausdruck geprüft, ob eine Zeichenfolge ein gültiges E-Mail-Format aufweist.</span><span class="sxs-lookup"><span data-stu-id="2beb2-104">The following example uses a regular expression to verify that a string is in valid email format.</span></span>

<span data-ttu-id="2beb2-105">Im Vergleich dazu, was tatsächlich als E-Mail-Adresse verwendet werden kann, ist dieser reguläre Ausdruck einfach.</span><span class="sxs-lookup"><span data-stu-id="2beb2-105">This regular expression is comparatively simple to what can actually be used as an email.</span></span> <span data-ttu-id="2beb2-106">Die Verwendung eines regulären Ausdrucks zum Überprüfen einer E-Mail-Adresse ist nützlich, um sicherzustellen, dass die Struktur einer E-Mail-Adresse korrekt ist. Sie ist allerdings kein Ersatz für die Überprüfung der tatsächlichen Existenz einer E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="2beb2-106">Using a regular expression to validate an email is useful to make sure the structure of an email is correct, but it isn't a substitution for verifying the email actually exists.</span></span>

<span data-ttu-id="2beb2-107">✔️ VERWENDEN SIE einen einfachen regulären Ausdruck, um die Struktur einer E-Mail-Adresse zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2beb2-107">✔️ DO use a small regular expression to check for the valid structure of an email.</span></span>

<span data-ttu-id="2beb2-108">✔️ SENDEN SIE eine Test-E-Mail an die von einem Benutzer Ihrer App angegebene Adresse.</span><span class="sxs-lookup"><span data-stu-id="2beb2-108">✔️ DO send a test email to the address provided by a user of your app.</span></span>

<span data-ttu-id="2beb2-109">❌ Verwenden Sie einen regulären Ausdruck NICHT als einzige Methode zum Überprüfen einer E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="2beb2-109">❌ DON'T use a regular expression as the only way you validate an email.</span></span>

<span data-ttu-id="2beb2-110">Wenn Sie versuchen, den _perfekten_ regulären Ausdruck zum Überprüfen der korrekten Struktur einer E-Mail-Adresse zu erstellen, wird dieser Ausdruck so komplex, dass es äußerst schwierig wird, ihn zu debuggen oder zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="2beb2-110">If you try to create the _perfect_ regular expression to validate that the structure of an email is correct, the expression becomes so complex that it's incredibly difficult to debug or improve.</span></span> <span data-ttu-id="2beb2-111">Reguläre Ausdrücke können nicht überprüfen, ob eine E-Mail-Adresse existiert, auch wenn sie richtig strukturiert ist.</span><span class="sxs-lookup"><span data-stu-id="2beb2-111">Regular expressions can't validate an email exists, even if it's structured correctly.</span></span> <span data-ttu-id="2beb2-112">Die beste Möglichkeit, eine E-Mail-Adresse zu überprüfen, ist das Senden einer Test-E-Mail an diese Adresse.</span><span class="sxs-lookup"><span data-stu-id="2beb2-112">The best way to validate an email is to send a test email to the address.</span></span>

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="2beb2-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2beb2-113">Example</span></span>

<span data-ttu-id="2beb2-114">Im Beispiel wird eine Methode `IsValidEmail` definiert, die `true` zurückgibt, wenn die Zeichenfolge eine gültige E-Mail-Adresse enthält, und `false`, wenn nicht. Sie führt jedoch keine weitere Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="2beb2-114">The example defines an `IsValidEmail` method, which returns `true` if the string contains a valid email address and `false` if it doesn't, but takes no other action.</span></span>

<span data-ttu-id="2beb2-115">Um die Gültigkeit der E-Mail-Adresse zu überprüfen ruft die `IsValidEmail` -Methode die <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> -Methode mit dem regulären Ausdruck `(@)(.+)$` auf, um den Domänennamen von der E-Mail-Adresse zu trennen.</span><span class="sxs-lookup"><span data-stu-id="2beb2-115">To verify that the email address is valid, the `IsValidEmail` method calls the <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> method with the `(@)(.+)$` regular expression pattern to separate the domain name from the email address.</span></span> <span data-ttu-id="2beb2-116">Der dritte Parameter ist ein <xref:System.Text.RegularExpressions.MatchEvaluator> -Delegat, der die Methode darstellt, die den gefundenen Text verarbeitet und ersetzt.</span><span class="sxs-lookup"><span data-stu-id="2beb2-116">The third parameter is a <xref:System.Text.RegularExpressions.MatchEvaluator> delegate that represents the method that processes and replaces the matched text.</span></span> <span data-ttu-id="2beb2-117">Das Muster des regulären Ausdrucks wird wie folgt interpretiert:</span><span class="sxs-lookup"><span data-stu-id="2beb2-117">The regular expression pattern is interpreted as follows.</span></span>

| <span data-ttu-id="2beb2-118">Muster</span><span class="sxs-lookup"><span data-stu-id="2beb2-118">Pattern</span></span> | <span data-ttu-id="2beb2-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2beb2-119">Description</span></span>                                                                         |
|---------|-------------------------------------------------------------------------------------|
| `(@)`   | <span data-ttu-id="2beb2-120">Das @ Zeichen wird als Übereinstimmung verwendet.</span><span class="sxs-lookup"><span data-stu-id="2beb2-120">Match the @ character.</span></span> <span data-ttu-id="2beb2-121">Dieser Teil stellt die erste Erfassungsgruppe dar.</span><span class="sxs-lookup"><span data-stu-id="2beb2-121">This part is the first capturing group.</span></span>                           |
| `(.+)`  | <span data-ttu-id="2beb2-122">Ein- oder mehrmalige Übereinstimmung mit beliebigem Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2beb2-122">Match one or more occurrences of any character.</span></span> <span data-ttu-id="2beb2-123">Dieser Teil stellt die zweite Erfassungsgruppe dar.</span><span class="sxs-lookup"><span data-stu-id="2beb2-123">This part is the second capturing group.</span></span> |
| `$`     | <span data-ttu-id="2beb2-124">Beendet die Suche am Ende der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2beb2-124">End the match at the end of the string.</span></span>                                             |

<span data-ttu-id="2beb2-125">Der Domänenname wird zusammen mit dem @ Zeichen der `DomainMapper` -Methode übergeben, die die <xref:System.Globalization.IdnMapping> -Klasse verwendet, um Unicode-Zeichen in ihre Punycode-Entsprechungen zu übersetzen, die außerhalb des 7-Bit-ASCII-Zeichenbereichs liegen.</span><span class="sxs-lookup"><span data-stu-id="2beb2-125">The domain name along with the @ character is passed to the `DomainMapper` method, which uses the <xref:System.Globalization.IdnMapping> class to translate Unicode characters that are outside the US-ASCII character range to Punycode.</span></span> <span data-ttu-id="2beb2-126">Darüber hinaus wird die Methode auch das `invalid` -Flag auf `True` fest, wenn die <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> -Methode ein unzulässiges Zeichen im Domänennamen erkennt.</span><span class="sxs-lookup"><span data-stu-id="2beb2-126">The method also sets the `invalid` flag to `True` if the <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> method detects any invalid characters in the domain name.</span></span> <span data-ttu-id="2beb2-127">Diese Methode gibt den Punycode-Domänennamen, der dem @ Zeichen vorangestellt ist, an die `IsValidEmail` -Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="2beb2-127">The method returns the Punycode domain name preceded by the @ symbol to the `IsValidEmail` method.</span></span>

> [!TIP]
> <span data-ttu-id="2beb2-128">Es wird empfohlen, dass Sie einen einfachen regulären Ausdruck mit dem Muster `(@)(.+)$` verwenden, um die Domäne zu normalisieren und dann einen Wert zurückzugeben, der angibt, ob die Adresse der Überprüfung standgehalten hat oder nicht.</span><span class="sxs-lookup"><span data-stu-id="2beb2-128">It's recommended that you use use the simple `(@)(.+)$` regular expression pattern to normalize the domain and then return a value indicating that it passed or failed.</span></span> <span data-ttu-id="2beb2-129">Im Beispiel in diesem Artikel werden jedoch weitere Möglichkeiten beschrieben, wie Sie einen regulären Ausdruck zur Überprüfung der E-Mail-Adresse verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2beb2-129">However, the example in this article describes how to further use a regular expression to validate the email.</span></span> <span data-ttu-id="2beb2-130">Unabhängig davon, wie Sie eine E-Mail-Adresse überprüfen, sollten Sie immer eine Test-E-Mail an die Adresse senden, um sicherzustellen, dass diese existiert.</span><span class="sxs-lookup"><span data-stu-id="2beb2-130">Regardless of how you validate an email, you should always send a test email to the address to make sure it exists.</span></span>

<span data-ttu-id="2beb2-131">Die `IsValidEmail`-Methode ruft dann die <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType>-Methode auf, um zu überprüfen, ob die Adresse dem Muster eines regulären Ausdrucks entspricht.</span><span class="sxs-lookup"><span data-stu-id="2beb2-131">The `IsValidEmail` method then calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> method to verify that the address conforms to a regular expression pattern.</span></span>

<span data-ttu-id="2beb2-132">Die Methode `IsValidEmail` überprüft lediglich, ob das Format der E-Mail-Adresse gültig ist. Sie überprüft nicht, ob die E-Mail-Adresse existiert.</span><span class="sxs-lookup"><span data-stu-id="2beb2-132">The `IsValidEmail` method merely determines whether the email format is valid for an email address, it doesn't validate that the email exists.</span></span> <span data-ttu-id="2beb2-133">Außerdem überprüft die Methode `IsValidEmail` nicht, ob es sich bei dem Domänennamen der obersten Ebene um einen gültigen Domänennamen handelt, der in der [IANA Root Zone Database](https://www.iana.org/domains/root/db) aufgeführt ist, was einen Suchvorgang erfordern würde.</span><span class="sxs-lookup"><span data-stu-id="2beb2-133">Also, the `IsValidEmail` method doesn't verify that the top-level domain name is a valid domain name listed at the [IANA Root Zone Database](https://www.iana.org/domains/root/db), which would require a look-up operation.</span></span>

:::code language="csharp" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/csharp/RegexUtilities.cs":::

:::code language="vb" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/vb/RegexUtilities.vb":::

<span data-ttu-id="2beb2-134">In diesem Beispiel kann das Muster des regulären Ausdrucks `^[^@\s]+@[^@\s]+\.[^@\s]+$` wie in der folgenden Tabelle dargestellt interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="2beb2-134">In this example, the regular expression pattern `^[^@\s]+@[^@\s]+\.[^@\s]+$` is interpreted as shown in the following table.</span></span> <span data-ttu-id="2beb2-135">Der reguläre Ausdruck wird mit dem Flag <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> kompiliert.</span><span class="sxs-lookup"><span data-stu-id="2beb2-135">The regular expression is compiled using the <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> flag.</span></span>

| <span data-ttu-id="2beb2-136">Muster</span><span class="sxs-lookup"><span data-stu-id="2beb2-136">Pattern</span></span>   | <span data-ttu-id="2beb2-137">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2beb2-137">Description</span></span>                                                                              |
|-----------|------------------------------------------------------------------------------------------|
| `^`       | <span data-ttu-id="2beb2-138">Starten Sie den Vergleich am Beginn der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2beb2-138">Begin the match at the start of the string.</span></span>                                              |
| `[^@\s]+` | <span data-ttu-id="2beb2-139">Überprüfung der einmaligen oder mehrmaligen Verwendung eines beliebigen Zeichens bis auf das @-Zeichen und das Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2beb2-139">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `@`       | <span data-ttu-id="2beb2-140">Das @ Zeichen wird als Übereinstimmung verwendet.</span><span class="sxs-lookup"><span data-stu-id="2beb2-140">Match the @ character.</span></span>                                                                   |
| `[^@\s]+` | <span data-ttu-id="2beb2-141">Überprüfung der einmaligen oder mehrmaligen Verwendung eines beliebigen Zeichens bis auf das @-Zeichen und das Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2beb2-141">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `\.`      | <span data-ttu-id="2beb2-142">Überprüfung der Verwendung eines einzelnen Punkts</span><span class="sxs-lookup"><span data-stu-id="2beb2-142">Match a single period character.</span></span>                                                         |
| `[^@\s]+` | <span data-ttu-id="2beb2-143">Überprüfung der einmaligen oder mehrmaligen Verwendung eines beliebigen Zeichens bis auf das @-Zeichen und das Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2beb2-143">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `$`       | <span data-ttu-id="2beb2-144">Beendet die Suche am Ende der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2beb2-144">End the match at the end of the string.</span></span>                                                  |

> [!IMPORTANT]
> <span data-ttu-id="2beb2-145">Dieser reguläre Ausdruck soll nicht jeden Aspekt einer gültigen E-Mail-Adresse abdecken.</span><span class="sxs-lookup"><span data-stu-id="2beb2-145">This regular expression is not intended to cover every aspect of a valid email address.</span></span> <span data-ttu-id="2beb2-146">Er wird vielmehr als Beispiel bereitgestellt, das Sie nach Bedarf erweitern können.</span><span class="sxs-lookup"><span data-stu-id="2beb2-146">It's provided as an example for you to extend as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="2beb2-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2beb2-147">See also</span></span>

- [<span data-ttu-id="2beb2-148">Reguläre Ausdrücke von .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2beb2-148">.NET Framework Regular Expressions</span></span>](regular-expressions.md)
- [<span data-ttu-id="2beb2-149">How far should one take e-mail address validation? (Wie weit sollte man bei der Überprüfung von E-Mail-Adressen gehen?)</span><span class="sxs-lookup"><span data-stu-id="2beb2-149">How far should one take e-mail address validation?</span></span>](https://softwareengineering.stackexchange.com/questions/78353/how-far-should-one-take-e-mail-address-validation#78363)
