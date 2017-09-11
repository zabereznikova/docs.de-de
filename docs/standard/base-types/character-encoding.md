---
title: Zeichencodierung in .NET
description: Zeichencodierung in .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bce54e41-e9dc-493a-8988-1cbadc340fe8
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: a8f42fa6a37f8de6f13186ea2ac17b2b2ced1601
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="character-encoding-in-net"></a><span data-ttu-id="245bb-104">Zeichencodierung in .NET</span><span class="sxs-lookup"><span data-stu-id="245bb-104">Character encoding in .NET</span></span>

<span data-ttu-id="245bb-105">Zeichen sind abstrakte Entitäten, die auf viele verschiedene Arten dargestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="245bb-105">Characters are abstract entities that can be represented in many different ways.</span></span> <span data-ttu-id="245bb-106">Eine Zeichencodierung ist ein System, in dem jedes Zeichen in einem unterstützten Zeichensatz mit einem Wert verknüpft wird, der dieses Zeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="245bb-106">A character encoding is a system that pairs each character in a supported character set with some value that represents that character.</span></span> <span data-ttu-id="245bb-107">Beispielsweise handelt es sich beim Morsealphabet um eine Zeichencodierung, die alle Zeichen im römischen Alphabet mit einem Muster aus Punkten und Bindestrichen verknüpft, das für die Übertragung über Telegrafenleitungen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="245bb-107">For example, Morse code is a character encoding that pairs each character in the Roman alphabet with a pattern of dots and dashes that are suitable for transmission over telegraph lines.</span></span> <span data-ttu-id="245bb-108">Bei einer Zeichencodierung für Computer wird jedes Zeichen in einem unterstützten Zeichensatz mit einem numerischen Wert verknüpft, der das jeweilige Zeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="245bb-108">A character encoding for computers pairs each character in a supported character set with a numeric value that represents that character.</span></span> <span data-ttu-id="245bb-109">Eine Zeichencodierung verfügt über zwei verschiedene Komponenten:</span><span class="sxs-lookup"><span data-stu-id="245bb-109">A character encoding has two distinct components:</span></span>

* <span data-ttu-id="245bb-110">Ein Encoder, der eine Folge von Zeichen in eine Folge von numerischen Werten (Bytes) übersetzt</span><span class="sxs-lookup"><span data-stu-id="245bb-110">An encoder, which translates a sequence of characters into a sequence of numeric values (bytes).</span></span>

* <span data-ttu-id="245bb-111">Ein Decoder, der eine Bytefolge in eine Folge von Zeichen übersetzt</span><span class="sxs-lookup"><span data-stu-id="245bb-111">A decoder, which translates a sequence of bytes into a sequence of characters.</span></span>

<span data-ttu-id="245bb-112">Die Zeichencodierung gibt die Regeln für die Funktionsweise von Encoder und Decoder an.</span><span class="sxs-lookup"><span data-stu-id="245bb-112">Character encoding describes the rules by which an encoder and a decoder operate.</span></span> <span data-ttu-id="245bb-113">Zum Beispiel beschreibt die [UTF8Encoding](xref:System.Text.UTF8Encoding)-Klasse die Regeln zum Codieren und Decodieren von UTF-8 (8-Bit-Unicode Transformation Format). In diesem Format werden für die Darstellung eines einzelnen Unicodezeichens ein bis vier Bytes verwendet.</span><span class="sxs-lookup"><span data-stu-id="245bb-113">For example, the [UTF8Encoding](xref:System.Text.UTF8Encoding) class describes the rules for encoding to, and decoding from, 8-bit Unicode Transformation Format (UTF-8), which uses one to four bytes to represent a single Unicode character.</span></span> <span data-ttu-id="245bb-114">Die Codierung und Decodierung können auch eine Validierung beinhalten.</span><span class="sxs-lookup"><span data-stu-id="245bb-114">Encoding and decoding can also include validation.</span></span> <span data-ttu-id="245bb-115">Die [UnicodeEncoding](xref:System.Text.UnicodeEncoding)-Klasse prüft z.B. alle Ersatzzeichen, um sicherzustellen, dass sie gültige Ersatzzeichenpaare bilden.</span><span class="sxs-lookup"><span data-stu-id="245bb-115">For example, the [UnicodeEncoding](xref:System.Text.UnicodeEncoding) class checks all surrogates to make sure they constitute valid surrogate pairs.</span></span> <span data-ttu-id="245bb-116">(Ein Ersatzzeichenpaar besteht aus einem Zeichen mit einem Codepunkt zwischen U+D800 und U+DBFF gefolgt von einem Zeichen mit einem Codepunkt zwischen U+DC00 und U+DFFF.) Eine Fallbackstrategie legt fest, wie ein Encoder ungültige Zeichen behandelt oder wie ein Decoder ungültige Bytes behandelt.</span><span class="sxs-lookup"><span data-stu-id="245bb-116">(A surrogate pair consists of a character with a code point that ranges from U+D800 to U+DBFF followed by a character with a code point that ranges from U+DC00 to U+DFFF.) A fallback strategy determines how an encoder handles invalid characters or how a decoder handles invalid bytes.</span></span> 

> [!WARNING]
> <span data-ttu-id="245bb-117">Die .NET-Codierungsklassen bieten eine Möglichkeit, Zeichendaten zu speichern und zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="245bb-117">The .NET encoding classes provide a way to store and convert character data.</span></span> <span data-ttu-id="245bb-118">Sie sollten nicht verwendet werden, um Binärdaten im Zeichenfolgenformat zu speichern.</span><span class="sxs-lookup"><span data-stu-id="245bb-118">They should not be used to store binary data in string form.</span></span> <span data-ttu-id="245bb-119">Abhängig von der verwendeten Codierung kann das Konvertieren von Binärdaten in das Zeichenfolgenformat mithilfe der Codierungsklassen zu unerwartetem Verhalten und ungenauen oder beschädigten Daten führen.</span><span class="sxs-lookup"><span data-stu-id="245bb-119">Depending on the encoding used, converting binary data to string format with the encoding classes can introduce unexpected behavior and produce inaccurate or corrupted data.</span></span> <span data-ttu-id="245bb-120">Um Binärdaten in ein Zeichenfolgenformat zu konvertieren, verwenden Sie die [Convert.ToBase64String](xref:System.Convert.ToBase64String(System.Byte[]))-Methode.</span><span class="sxs-lookup"><span data-stu-id="245bb-120">To convert binary data to a string form, use the [Convert.ToBase64String](xref:System.Convert.ToBase64String(System.Byte[])) method.</span></span> 
 
<span data-ttu-id="245bb-121">.NET verwendet die UTF-16-Codierung (angegeben durch die [UnicodeEncoding](xref:System.Text.UnicodeEncoding)-Klasse), um Zeichen und Zeichenfolgen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="245bb-121">.NET uses the UTF-16 encoding (represented by the [UnicodeEncoding](xref:System.Text.UnicodeEncoding) class) to represent characters and strings.</span></span> <span data-ttu-id="245bb-122">Anwendungen, die auf die Common Language Runtime abzielen, verwenden Encoder, um von der Common Language Runtime unterstützte Unicode-Zeichendarstellungen anderen Codierungsschemen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="245bb-122">Applications that target the common language runtime use encoders to map Unicode character representations supported by the common language runtime to other encoding schemes.</span></span> <span data-ttu-id="245bb-123">Decoder werden verwendet, um Zeichen aus Nicht-Unicode-Codierungen Unicode zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="245bb-123">They use decoders to map characters from non-Unicode encodings to Unicode.</span></span>

<span data-ttu-id="245bb-124">Dieses Thema enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="245bb-124">This topic consists of the following sections:</span></span>

* [<span data-ttu-id="245bb-125">Codierungen in .NET</span><span class="sxs-lookup"><span data-stu-id="245bb-125">Encodings in .NET</span></span>](#encodings-in-net)

* [<span data-ttu-id="245bb-126">Auswählen einer Encoding-Klasse</span><span class="sxs-lookup"><span data-stu-id="245bb-126">Selecting an encoding class</span></span>](#selecting-an-encoding-class)

* [<span data-ttu-id="245bb-127">Verwenden eines Codierungsobjekts</span><span class="sxs-lookup"><span data-stu-id="245bb-127">Using an encoding object</span></span>](#using-an-encoding-object)

* [<span data-ttu-id="245bb-128">Auswählen einer Fallbackstrategie</span><span class="sxs-lookup"><span data-stu-id="245bb-128">Choosing a fallback strategy</span></span>](#choosing-a-fallback-strategy)

* [<span data-ttu-id="245bb-129">Implementieren einer benutzerdefinierten Fallbackstrategie</span><span class="sxs-lookup"><span data-stu-id="245bb-129">Implementing a custom fallback strategy</span></span>](#implementing-a-custom-fallback-strategy)

## <a name="encodings-in-net"></a><span data-ttu-id="245bb-130">Codierungen in .NET</span><span class="sxs-lookup"><span data-stu-id="245bb-130">Encodings in .NET</span></span>

<span data-ttu-id="245bb-131">Alle Zeichencodierungsklassen in .NET erben von der abstrakten [System.Text.Encoding](xref:System.Text.Encoding)-Klasse, die die Funktionen definiert, die allen Zeichencodierungen gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="245bb-131">All character encoding classes in .NET inherit from the [System.Text.Encoding](xref:System.Text.Encoding) class, which is an abstract class that defines the functionality common to all character encodings.</span></span> <span data-ttu-id="245bb-132">Um auf die einzelnen in .NET implementierten Codierungsobjekte zuzugreifen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="245bb-132">To access the individual encoding objects implemented in .NET, do the following:</span></span>

* <span data-ttu-id="245bb-133">Verwenden Sie die statischen Eigenschaften der [Encoding](xref:System.Text.Encoding)-Klasse, die Objekte zurückgibt, die die in .NET verfügbaren Standardzeichencodierungen darstellen (ASCII, UTF-7, UTF-8, UTF-16 und UTF-32).</span><span class="sxs-lookup"><span data-stu-id="245bb-133">Use the static properties of the [Encoding](xref:System.Text.Encoding) class, which return objects that represent the standard character encodings available in .NET (ASCII, UTF-7, UTF-8, UTF-16, and UTF-32).</span></span> <span data-ttu-id="245bb-134">Die [Encoding.Unicode](xref:System.Text.Encoding.Unicode)-Eigenschaft gibt z.B. ein [UnicodeEncoding](xref:System.Text.UnicodeEncoding)-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="245bb-134">For example, the [Encoding.Unicode](xref:System.Text.Encoding.Unicode) property returns a [UnicodeEncoding](xref:System.Text.UnicodeEncoding) object.</span></span> <span data-ttu-id="245bb-135">Jedes Objekt verwendet einen Ersatzfallback für die Behandlung von Zeichenfolgen, die nicht codiert werden können, und von Bytes, die nicht decodiert werden können.</span><span class="sxs-lookup"><span data-stu-id="245bb-135">Each object uses replacement fallback to handle strings that it cannot encode and bytes that it cannot decode.</span></span> <span data-ttu-id="245bb-136">(Weitere Informationen finden Sie im Abschnitt [Ersatzfallback](#replacement-fallback).)</span><span class="sxs-lookup"><span data-stu-id="245bb-136">(For more information, see the [Replacement fallback](#replacement-fallback) section.)</span></span>

* <span data-ttu-id="245bb-137">Rufen Sie den Klassenkonstruktor der Codierung auf.</span><span class="sxs-lookup"><span data-stu-id="245bb-137">Call the encoding's class constructor.</span></span> <span data-ttu-id="245bb-138">Objekte für ASCII-, UTF-7-, UTF-8-, UTF-16- und UTF-32-Codierungen können auf diese Weise instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="245bb-138">Objects for the ASCII, UTF-7, UTF-8, UTF-16, and UTF-32 encodings can be instantiated in this way.</span></span> <span data-ttu-id="245bb-139">Standardmäßig verwendet jedes Objekt den Ersatzfallback zur Behandlung von Zeichenfolgen, die nicht codiert werden können, und von Bytes, die nicht decodiert werden können. Sie können aber angeben, dass stattdessen eine Ausnahme ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="245bb-139">By default, each object uses replacement fallback to handle strings that it cannot encode and bytes that it cannot decode, but you can specify that an exception should be thrown instead.</span></span> <span data-ttu-id="245bb-140">(Weitere Informationen finden Sie in den Abschnitten [Ersatzfallback](#replacement-fallback) und [Ausnahmefallback](#exception-fallback).)</span><span class="sxs-lookup"><span data-stu-id="245bb-140">(For more information, see the [Replacement fallback](#replacement-fallback) and [Exception fallback](#exception-fallback) sections.)</span></span>

* <span data-ttu-id="245bb-141">Rufen Sie den [Encoding.Encoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32))-Konstruktor auf, und übergeben Sie eine ganze Zahl, die die Codierung darstellt.</span><span class="sxs-lookup"><span data-stu-id="245bb-141">Call the [Encoding.Encoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32)) constructor and pass it an integer that represents the encoding.</span></span> <span data-ttu-id="245bb-142">Standardcodierungsobjekte verwenden den Ersatzfallback, und Codepage- und DBCS (Doppelbyte-Zeichensatz)-Codierungsobjekte verwenden den Fallback mit ähnlichen Zeichen zur Behandlung von Zeichenfolgen, die nicht codiert werden können, und von Bytes, die nicht decodiert werden können.</span><span class="sxs-lookup"><span data-stu-id="245bb-142">Standard encoding objects use replacement fallback, and code page and double-byte character set (DBCS) encoding objects use best-fit fallback to handle strings that they cannot encode and bytes that they cannot decode.</span></span> <span data-ttu-id="245bb-143">(Weitere Informationen finden Sie im Abschnitt [Fallback mit ähnlichen Zeichen](#best-fit-fallback).)</span><span class="sxs-lookup"><span data-stu-id="245bb-143">(For more information, see the [Best-Fit fallback](#best-fit-fallback) section.)</span></span>

* <span data-ttu-id="245bb-144">Rufen Sie die [Encoding.GetEncoding](xref:System.Text.Encoding.GetEncoding(System.Int32))-Methode auf, die jede in .NET verfügbare Standard-, Codepage- oder DBCS-Codierung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="245bb-144">Call the [Encoding.GetEncoding](xref:System.Text.Encoding.GetEncoding(System.Int32)) method, which returns any standard, code page, or DBCS encoding available in .NET.</span></span> <span data-ttu-id="245bb-145">Mithilfe von Überladungen können Sie sowohl für den Encoder als auch den Decoder ein Fallbackobjekt angeben.</span><span class="sxs-lookup"><span data-stu-id="245bb-145">Overloads let you specify a fallback object for both the encoder and the decoder.</span></span>

> [!NOTE]
> <span data-ttu-id="245bb-146">Gemäß Unicode-Standard werden jedem Zeichen aller unterstützten Skripts ein Codepunkt (eine Zahl) und ein Name zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="245bb-146">The Unicode Standard assigns a code point (a number) and a name to each character in every supported script.</span></span> <span data-ttu-id="245bb-147">Das Zeichen "A" wird beispielsweise durch den Codepunkt U+0041 und den Namen "LATIN CAPITAL LETTER A" dargestellt.</span><span class="sxs-lookup"><span data-stu-id="245bb-147">For example, the character "A" is represented by the code point U+0041 and the name "LATIN CAPITAL LETTER A".</span></span> <span data-ttu-id="245bb-148">Die UTF (Unicode-Transformation Format)-Codierungen definieren Möglichkeiten, diesen Codepunkt in eine Abfolge aus einem oder mehreren Bytes zu codieren.</span><span class="sxs-lookup"><span data-stu-id="245bb-148">The Unicode Transformation Format (UTF) encodings define ways to encode that code point into a sequence of one or more bytes.</span></span> <span data-ttu-id="245bb-149">Ein Unicode-Datencodierungsschema vereinfacht die Entwicklung weltweit einsetzbarer Anwendungen, da es die Darstellung von Zeichen aus beliebigen Zeichensätzen in einer Codierung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="245bb-149">A Unicode encoding scheme simplifies world-ready application development because it allows characters from any character set to be represented in a single encoding.</span></span> <span data-ttu-id="245bb-150">Anwendungsentwickler müssen nicht mehr das Codierungsschema verfolgen, das für die Erstellung von Zeichen für eine bestimmte Sprache oder ein Schreibsystem verwendet wurde, und die Daten können länderübergreifend auf allen Systemen verwendet werden, ohne beschädigt zu werden.</span><span class="sxs-lookup"><span data-stu-id="245bb-150">Application developers no longer have to keep track of the encoding scheme that was used to produce characters for a specific language or writing system, and data can be shared among systems internationally without being corrupted.</span></span>
>
>  <span data-ttu-id="245bb-151">.NET unterstützt drei Codierungen, die durch den Unicode-Standard definiert sind: UTF-8, UTF-16 und UTF-32.</span><span class="sxs-lookup"><span data-stu-id="245bb-151">.NET supports three encodings defined by the Unicode standard: UTF-8, UTF-16, and UTF-32.</span></span> <span data-ttu-id="245bb-152">Weitere Informationen finden Sie im Unicode-Standard auf der [Unicode](http://www.unicode.org/)-Homepage.</span><span class="sxs-lookup"><span data-stu-id="245bb-152">For more information, see The Unicode Standard at the [Unicode](http://www.unicode.org/) home page.</span></span>
 
<span data-ttu-id="245bb-153">.NET unterstützt die in der folgenden Tabelle aufgelisteten Zeichencodierungssysteme.</span><span class="sxs-lookup"><span data-stu-id="245bb-153">.NET supports the character encoding systems listed in the following table.</span></span>

<span data-ttu-id="245bb-154">Codierung</span><span class="sxs-lookup"><span data-stu-id="245bb-154">Encoding</span></span> | <span data-ttu-id="245bb-155">Klasse</span><span class="sxs-lookup"><span data-stu-id="245bb-155">Class</span></span> | <span data-ttu-id="245bb-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="245bb-156">Description</span></span> | <span data-ttu-id="245bb-157">Vorteile/Nachteile</span><span class="sxs-lookup"><span data-stu-id="245bb-157">Advantages/disadvantages</span></span>
-------- | ----- | ----------- | ------------------------ 
<span data-ttu-id="245bb-158">ASCII</span><span class="sxs-lookup"><span data-stu-id="245bb-158">ASCII</span></span> | [<span data-ttu-id="245bb-159">ASCIIEncoding</span><span class="sxs-lookup"><span data-stu-id="245bb-159">ASCIIEncoding</span></span>](xref:System.Text.ASCIIEncoding) | <span data-ttu-id="245bb-160">Codiert einen begrenzten Bereich von Zeichen mithilfe der unteren sieben Bits eines Bytes.</span><span class="sxs-lookup"><span data-stu-id="245bb-160">Encodes a limited range of characters by using the lower seven bits of a byte.</span></span> | <span data-ttu-id="245bb-161">Da diese Codierung nur Zeichenwerte von U+0000 bis U+007F unterstützt, ist sie in den meisten Fällen für weltweit einsetzbare Anwendungen nicht geeignet.</span><span class="sxs-lookup"><span data-stu-id="245bb-161">Because this encoding only supports character values from U+0000 through U+007F, in most cases it is inadequate for internationalized applications.</span></span>
<span data-ttu-id="245bb-162">UTF-7</span><span class="sxs-lookup"><span data-stu-id="245bb-162">UTF-7</span></span> | [<span data-ttu-id="245bb-163">UTF7Encoding</span><span class="sxs-lookup"><span data-stu-id="245bb-163">UTF7Encoding</span></span>](xref:System.Text.UTF7Encoding) | <span data-ttu-id="245bb-164">Stellt Zeichen als Sequenzen von 7-Bit-ASCII-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="245bb-164">Represents characters as sequences of 7-bit ASCII characters.</span></span> <span data-ttu-id="245bb-165">Nicht-ASCII-Unicode-Zeichen werden durch eine Escapesequenz von ASCII-Zeichen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="245bb-165">Non-ASCII Unicode characters are represented by an escape sequence of ASCII characters.</span></span> | <span data-ttu-id="245bb-166">UTF-7 unterstützt Protokolle wie E-Mail- und Newsgroupprotokolle.</span><span class="sxs-lookup"><span data-stu-id="245bb-166">UTF-7 supports protocols such as e-mail and newsgroup protocols.</span></span> <span data-ttu-id="245bb-167">UTF-7 ist jedoch nicht besonders sicher oder robust.</span><span class="sxs-lookup"><span data-stu-id="245bb-167">However, UTF-7 is not particularly secure or robust.</span></span> <span data-ttu-id="245bb-168">In einigen Fällen kann die Änderung eines Bits die Interpretation einer gesamten UTF-7-Zeichenfolge radikal ändern.</span><span class="sxs-lookup"><span data-stu-id="245bb-168">In some cases, changing one bit can radically alter the interpretation of an entire UTF-7 string.</span></span> <span data-ttu-id="245bb-169">In anderen Fällen können verschiedene UTF-7-Zeichenfolgen denselben Text codieren.</span><span class="sxs-lookup"><span data-stu-id="245bb-169">In other cases, different UTF-7 strings can encode the same text.</span></span> <span data-ttu-id="245bb-170">Bei Sequenzen, die Nicht-ASCII-Zeichen enthalten, benötigt UTF-7 mehr Speicherplatz als UTF-8, und auch die Codierung/Decodierung erfolgt langsamer.</span><span class="sxs-lookup"><span data-stu-id="245bb-170">For sequences that include non-ASCII characters, UTF-7 requires more space than UTF-8, and encoding/decoding is slower.</span></span> <span data-ttu-id="245bb-171">Daher sollten Sie nach Möglichkeit UTF-8 anstelle von UTF-7 verwenden.</span><span class="sxs-lookup"><span data-stu-id="245bb-171">Consequently, you should use UTF-8 instead of UTF-7 if possible.</span></span>
<span data-ttu-id="245bb-172">UTF-8</span><span class="sxs-lookup"><span data-stu-id="245bb-172">UTF-8</span></span> | [<span data-ttu-id="245bb-173">UTF8Encoding</span><span class="sxs-lookup"><span data-stu-id="245bb-173">UTF8Encoding</span></span>](xref:System.Text.UTF8Encoding) | <span data-ttu-id="245bb-174">Stellt jeden Unicode-Codepunkt als eine Folge von einem bis vier Bytes dar.</span><span class="sxs-lookup"><span data-stu-id="245bb-174">Represents each Unicode code point as a sequence of one to four bytes.</span></span> | <span data-ttu-id="245bb-175">UTF-8 unterstützt 8-Bit-Datengrößen und funktioniert mit vielen vorhandenen Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="245bb-175">UTF-8 supports 8-bit data sizes and works well with many existing operating systems.</span></span> <span data-ttu-id="245bb-176">Im ASCII-Zeichenbereich ist UTF-8 mit der ASCII-Codierung identisch und ermöglicht einen umfangreicheren Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="245bb-176">For the ASCII range of characters, UTF-8 is identical to ASCII encoding and allows a broader set of characters.</span></span> <span data-ttu-id="245bb-177">Für CJK-Skripts (Chinesisch, Japanisch, Koreanisch) können bei UTF-8 jedoch drei Bytes für jedes Zeichen erforderlich sein, und es können größere Datengrößen als bei UTF-16 entstehen.</span><span class="sxs-lookup"><span data-stu-id="245bb-177">However, for Chinese-Japanese-Korean (CJK) scripts, UTF-8 can require three bytes for each character, and can potentially cause larger data sizes than UTF-16.</span></span> <span data-ttu-id="245bb-178">Manchmal wird die größere Datengröße für den CJK-Bereich jedoch durch die Menge an ASCII-Daten, z. B. HTML-Tags, gerechtfertigt.</span><span class="sxs-lookup"><span data-stu-id="245bb-178">Note that sometimes the amount of ASCII data, such as HTML tags, justifies the increased size for the CJK range.</span></span>
<span data-ttu-id="245bb-179">UTF-16</span><span class="sxs-lookup"><span data-stu-id="245bb-179">UTF-16</span></span> | [<span data-ttu-id="245bb-180">UnicodeEncoding</span><span class="sxs-lookup"><span data-stu-id="245bb-180">UnicodeEncoding</span></span>](xref:System.Text.UnicodeEncoding) | <span data-ttu-id="245bb-181">Stellt jeden Unicode-Codepunkt als Folge von einer oder zwei 16-Bit-Ganzzahlen dar.</span><span class="sxs-lookup"><span data-stu-id="245bb-181">Represents each Unicode code point as a sequence of one or two 16-bit integers.</span></span> <span data-ttu-id="245bb-182">Die meisten allgemeinen Unicode-Zeichen erfordern nur einen UTF-16-Codepunkt. Ergänzende Unicode-Zeichen (U+10000 und höher) erfordern allerdings zwei UTF-16-Ersatzzeichen-Codepunkte.</span><span class="sxs-lookup"><span data-stu-id="245bb-182">Most common Unicode characters require only one UTF-16 code point, although Unicode supplementary characters (U+10000 and greater) require two UTF-16 surrogate code points.</span></span> <span data-ttu-id="245bb-183">Sowohl Little-Endian- als auch Big-Endian-Bytereihenfolgen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="245bb-183">Both little-endian and big-endian byte orders are supported.</span></span> | <span data-ttu-id="245bb-184">Die UTF-16-Codierung wird von der Common Language Runtime zur Darstellung von Char-Werten und String-Werten und vom Windows-Betriebssystem zur Darstellung von WCHAR-Werten verwendet.</span><span class="sxs-lookup"><span data-stu-id="245bb-184">UTF-16 encoding is used by the common language runtime to represent Char and String values, and it is used by the Windows operating system to represent WCHAR values.</span></span>
<span data-ttu-id="245bb-185">UTF-32</span><span class="sxs-lookup"><span data-stu-id="245bb-185">UTF-32</span></span> | [<span data-ttu-id="245bb-186">UTF32Encoding</span><span class="sxs-lookup"><span data-stu-id="245bb-186">UTF32Encoding</span></span>](xref:System.Text.UTF32Encoding) | <span data-ttu-id="245bb-187">Stellt jeden Unicode-Codepunkt als 32-Bit-Ganzzahl dar.</span><span class="sxs-lookup"><span data-stu-id="245bb-187">Represents each Unicode code point as a 32-bit integer.</span></span> <span data-ttu-id="245bb-188">Sowohl Little-Endian- als auch Big-Endian-Bytereihenfolgen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="245bb-188">Both little-endian and big-endian byte orders are supported.</span></span> | <span data-ttu-id="245bb-189">Die UTF-32-Codierung wird verwendet, wenn Anwendungen das Verhalten mit Ersatzzeichen-Codepunkten der UTF-16-Codierung unter Betriebssystemen vermeiden möchten, bei denen codierter Speicherplatz von zu großer Bedeutung ist.</span><span class="sxs-lookup"><span data-stu-id="245bb-189">UTF-32 encoding is used when applications want to avoid the surrogate code point behavior of UTF-16 encoding on operating systems for which encoded space is too important.</span></span> <span data-ttu-id="245bb-190">Einzelne Symbole, die in einer Anzeige gerendert werden, können dennoch mit mehr als einem UTF-32-Zeichen codiert werden.</span><span class="sxs-lookup"><span data-stu-id="245bb-190">Single glyphs rendered on a display can still be encoded with more than one UTF-32 character.</span></span>

<span data-ttu-id="245bb-191">Diese Codierungen ermöglichen Ihnen die Verwendung von Unicode-Zeichen und von Codierungen, die in älteren Anwendungen am häufigsten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="245bb-191">These encodings enable you to work with Unicode characters as well as with encodings that are most commonly used in legacy applications.</span></span> <span data-ttu-id="245bb-192">Außerdem können Sie eine benutzerdefinierte Codierung erstellen, indem Sie eine von [Encoding](xref:System.Text.Encoding) erbende Klasse definieren und deren Member überschreiben.</span><span class="sxs-lookup"><span data-stu-id="245bb-192">In addition, you can create a custom encoding by defining a class that derives from [Encoding](xref:System.Text.Encoding) and overriding its members.</span></span>

> [!NOTE]
> <span data-ttu-id="245bb-193">Standardmäßig stellt .NET Core keine anderen Codepagecodierungen als Codepage 28591 und Unicode-Codierungen (z.B. UTF-8 und UTF-16) bereit.</span><span class="sxs-lookup"><span data-stu-id="245bb-193">By default, .NET Core does not make available any code page encodings other than code page 28591 and the Unicode encodings, such as UTF-8 and UTF-16.</span></span> <span data-ttu-id="245bb-194">Allerdings können Sie Ihrer App die Codepagecodierungen hinzufügen, die in Standard-Windows-Apps verwendet werden, die .NET Framework als Ziel nutzen.</span><span class="sxs-lookup"><span data-stu-id="245bb-194">However, you can add the code page encodings found in standard Windows apps that target the .NET Framework to your app.</span></span> <span data-ttu-id="245bb-195">Vollständige Informationen finden Sie im Thema [EncodingProvider](xref:System.Text.EncodingProvider).</span><span class="sxs-lookup"><span data-stu-id="245bb-195">For complete information, see the [EncodingProvider](xref:System.Text.EncodingProvider) topic.</span></span> 

## <a name="selecting-an-encoding-class"></a><span data-ttu-id="245bb-196">Auswählen einer Encoding-Klasse</span><span class="sxs-lookup"><span data-stu-id="245bb-196">Selecting an Encoding class</span></span>

<span data-ttu-id="245bb-197">Wenn Sie die Möglichkeit haben, die von der Anwendung verwendete Codierung auszuwählen, sollten Sie eine Unicode-Codierung verwenden, vorzugsweise [UTF8Encoding](xref:System.Text.UTF8Encoding) oder [UnicodeEncoding](xref:System.Text.UnicodeEncoding).</span><span class="sxs-lookup"><span data-stu-id="245bb-197">If you have the opportunity to choose the encoding to be used by your application, you should use a Unicode encoding, preferably either [UTF8Encoding](xref:System.Text.UTF8Encoding) or [UnicodeEncoding](xref:System.Text.UnicodeEncoding).</span></span> <span data-ttu-id="245bb-198">(.NET unterstützt auch eine dritte Unicode-Codierung, [UTF32Encoding](xref:System.Text.UTF32Encoding).)</span><span class="sxs-lookup"><span data-stu-id="245bb-198">(.NET also supports a third Unicode encoding, [UTF32Encoding](xref:System.Text.UTF32Encoding).)</span></span> 

<span data-ttu-id="245bb-199">Wenn Sie eine ASCII-Codierung ([ASCIIEncoding](xref:System.Text.ASCIIEncoding)) verwenden möchten, wählen Sie stattdessen [UTF8Encoding](xref:System.Text.UTF8Encoding).</span><span class="sxs-lookup"><span data-stu-id="245bb-199">If you are planning to use an ASCII encoding ([ASCIIEncoding](xref:System.Text.ASCIIEncoding)), choose [UTF8Encoding](xref:System.Text.UTF8Encoding) instead.</span></span> <span data-ttu-id="245bb-200">Die beiden Codierungen sind für den ASCII-Zeichensatz identisch. [UTF8Encoding](xref:System.Text.UTF8Encoding) bietet allerdings die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="245bb-200">The two encodings are identical for the ASCII character set, but [UTF8Encoding](xref:System.Text.UTF8Encoding) has the following advantages:</span></span> 

* <span data-ttu-id="245bb-201">Alle Unicode-Zeichen können dargestellt werden, während [ASCIIEncoding](xref:System.Text.ASCIIEncoding) nur die Unicode-Zeichenwerte zwischen U+0000 und U+007F unterstützt.</span><span class="sxs-lookup"><span data-stu-id="245bb-201">It can represent every Unicode character, whereas [ASCIIEncoding](xref:System.Text.ASCIIEncoding) supports only the Unicode character values between U+0000 and U+007F.</span></span>

* <span data-ttu-id="245bb-202">Weitere Vorteile sind die Fehlererkennung und die verbesserte Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="245bb-202">It provides error detection and better security.</span></span>

* <span data-ttu-id="245bb-203">Die Geschwindigkeit wurde optimiert und sollte schneller sein als jede andere Codierung.</span><span class="sxs-lookup"><span data-stu-id="245bb-203">It has been tuned to be as fast as possible and should be faster than any other encoding.</span></span> <span data-ttu-id="245bb-204">Selbst bei Inhalten, bei denen es sich um reine ASCII-Daten handelt, erfolgen mit [UTF8Encoding](xref:System.Text.UTF8Encoding) durchgeführte Operationen schneller als mit [ASCIIEncoding](xref:System.Text.ASCIIEncoding) durchgeführte Operationen.</span><span class="sxs-lookup"><span data-stu-id="245bb-204">Even for content that is entirely ASCII, operations performed with [UTF8Encoding](xref:System.Text.UTF8Encoding) are faster than operations performed with [ASCIIEncoding](xref:System.Text.ASCIIEncoding).</span></span>

<span data-ttu-id="245bb-205">Sie sollten daher in Erwägung ziehen, [ASCIIEncoding](xref:System.Text.ASCIIEncoding) nur für ältere Anwendungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="245bb-205">You should consider using [ASCIIEncoding](xref:System.Text.ASCIIEncoding) only for legacy applications.</span></span> <span data-ttu-id="245bb-206">Allerdings kann [UTF8Encoding](xref:System.Text.UTF8Encoding) auch für ältere Anwendungen aus folgenden Gründen die bessere Wahl sein (ausgehend von den Standardeinstellungen):</span><span class="sxs-lookup"><span data-stu-id="245bb-206">However, even for legacy applications, [UTF8Encoding](xref:System.Text.UTF8Encoding) might be a better choice for the following reasons (assuming default settings):</span></span>

* <span data-ttu-id="245bb-207">Wenn die Anwendung Inhalte, die keine reinen ASCII-Daten sind, mit [ASCIIEncoding](xref:System.Text.ASCIIEncoding) codiert, wird jedes Nicht-ASCII-Zeichen als Fragezeichen (?) codiert.</span><span class="sxs-lookup"><span data-stu-id="245bb-207">If your application has content that is not strictly ASCII and encodes it with [ASCIIEncoding](xref:System.Text.ASCIIEncoding), each non-ASCII character encodes as a question mark (?).</span></span> <span data-ttu-id="245bb-208">Wenn die Anwendung diese Daten anschließend decodiert, gehen die Informationen verloren.</span><span class="sxs-lookup"><span data-stu-id="245bb-208">If the application then decodes this data, the information is lost.</span></span>


* <span data-ttu-id="245bb-209">Wenn die Anwendung Inhalte, die keine reinen ASCII-Daten sind, mit [UTF8Encoding](xref:System.Text.UTF8Encoding) codiert und als ASCII-Daten interpretiert, erscheint das Ergebnis unverständlich.</span><span class="sxs-lookup"><span data-stu-id="245bb-209">If your application has content that is not strictly ASCII and encodes it with [UTF8Encoding](xref:System.Text.UTF8Encoding), the result seems unintelligible if interpreted as ASCII.</span></span> <span data-ttu-id="245bb-210">Wenn die Anwendung dann jedoch einen UTF-8-Decoder verwendet, um diese Daten zu decodieren, durchlaufen sie einen erfolgreichen Roundtrip.</span><span class="sxs-lookup"><span data-stu-id="245bb-210">However, if the application then uses a UTF-8 decoder to decode this data, the data performs a round trip successfully.</span></span>

<span data-ttu-id="245bb-211">In einer Webanwendung sollten die Zeichen, die als Antwort auf eine Webanforderung an den Client gesendet werden, die auf dem Client verwendete Codierung widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="245bb-211">In a web application, characters sent to the client in response to a web request should reflect the encoding used on the client.</span></span> <span data-ttu-id="245bb-212">In den meisten Fällen sollten Sie die [HttpResponse.ContentEncoding](xref:System.Net.HttpResponseHeader.ContentEncoding)-Eigenschaft auf den Wert festlegen, der von der [HttpRequestHeader.ContentEncoding](xref:System.Net.HttpRequestHeader.ContentEncoding)-Eigenschaft zurückgegeben wird, um Text in der vom Benutzer erwarteten Codierung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="245bb-212">In most cases, you should set the [HttpResponse.ContentEncoding](xref:System.Net.HttpResponseHeader.ContentEncoding) property to the value returned by the [HttpRequestHeader.ContentEncoding](xref:System.Net.HttpRequestHeader.ContentEncoding) property to display text in the encoding that the user expects.</span></span>

## <a name="using-an-encoding-object"></a><span data-ttu-id="245bb-213">Verwenden eines Codierungsobjekts</span><span class="sxs-lookup"><span data-stu-id="245bb-213">Using an encoding object</span></span>

<span data-ttu-id="245bb-214">Ein Codierer konvertiert eine Zeichenfolge (meistens Unicode-Zeichen) in die numerische Entsprechung (Byte).</span><span class="sxs-lookup"><span data-stu-id="245bb-214">An encoder converts a string of characters (most commonly, Unicode characters) to its numeric (byte) equivalent.</span></span> <span data-ttu-id="245bb-215">Beispielsweise können Sie einen ASCII-Encoder verwenden, um Unicode-Zeichen in ASCII zu konvertieren, damit sie in der Konsole angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="245bb-215">For example, you might use an ASCII encoder to convert Unicode characters to ASCII so that they can be displayed at the console.</span></span> <span data-ttu-id="245bb-216">Um die Konvertierung auszuführen, rufen Sie die [Encoding.GetBytes](xref:System.Text.Encoding.GetBytes(System.Char[]))-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="245bb-216">To perform the conversion, you call the [Encoding.GetBytes](xref:System.Text.Encoding.GetBytes(System.Char[])) method.</span></span> <span data-ttu-id="245bb-217">Wenn Sie vor Ausführung der Codierung ermitteln möchten, wie viele Bytes zum Speichern der codierten Zeichen benötigt werden, können Sie die [GetByteCount](xref:System.Text.Encoding.GetByteCount(System.Char[]))-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="245bb-217">If you want to determine how many bytes are needed to store the encoded characters before performing the encoding, you can call the [GetByteCount](xref:System.Text.Encoding.GetByteCount(System.Char[])) method.</span></span>

<span data-ttu-id="245bb-218">Im folgenden Beispiel wird ein einzelnes Bytearray verwendet, um Zeichenfolgen in zwei separaten Vorgängen zu codieren.</span><span class="sxs-lookup"><span data-stu-id="245bb-218">The following example uses a single byte array to encode strings in two separate operations.</span></span> <span data-ttu-id="245bb-219">Ein verwalteter Index gibt die Anfangsposition im Bytearray für die nächste Gruppe von ASCII-codierten Bytes an.</span><span class="sxs-lookup"><span data-stu-id="245bb-219">It maintains an index that indicates the starting position in the byte array for the next set of ASCII-encoded bytes.</span></span> <span data-ttu-id="245bb-220">Die [ASCIIEncoding.GetByteCount(String)](xref:System.Text.ASCIIEncoding.GetByteCount(System.String))-Methode wird aufgerufen, um sicherzustellen, dass das Bytearray groß genug für die codierte Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="245bb-220">It calls the [ASCIIEncoding.GetByteCount(String)](xref:System.Text.ASCIIEncoding.GetByteCount(System.String)) method to ensure that the byte array is large enough to accommodate the encoded string.</span></span> <span data-ttu-id="245bb-221">Die [ASCIIEncoding.GetBytes(String, Int32, Int32, Byte[], Int32)](xref:System.Text.ASCIIEncoding.GetBytes(System.Char[],System.Int32,System.Int32,System.Byte[],System.Int32))-Methode wird dann zum Codieren der Zeichen in der Zeichenfolge aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="245bb-221">It then calls the [ASCIIEncoding.GetBytes(String, Int32, Int32, Byte[], Int32)](xref:System.Text.ASCIIEncoding.GetBytes(System.Char[],System.Int32,System.Int32,System.Byte[],System.Int32)) method to encode the characters in the string.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      string[] strings= { "This is the first sentence. ", 
                          "This is the second sentence. " };
      Encoding asciiEncoding = Encoding.ASCII;

      // Create array of adequate size.
      byte[] bytes = new byte[49];
      // Create index for current position of array.
      int index = 0;

      Console.WriteLine("Strings to encode:");
      foreach (var stringValue in strings) {
         Console.WriteLine("   {0}", stringValue);

         int count = asciiEncoding.GetByteCount(stringValue);
         if (count + index >=  bytes.Length)
            Array.Resize(ref bytes, bytes.Length + 50);

         int written = asciiEncoding.GetBytes(stringValue, 0, 
                                              stringValue.Length, 
                                              bytes, index);    

         index = index + written; 
      } 
      Console.WriteLine("\nEncoded bytes:");
      Console.WriteLine("{0}", ShowByteValues(bytes, index));
      Console.WriteLine();

      // Decode Unicode byte array to a string.
      string newString = asciiEncoding.GetString(bytes, 0, index);
      Console.WriteLine("Decoded: {0}", newString);
   }

   private static string ShowByteValues(byte[] bytes, int last ) 
   {
      string returnString = "   ";
      for (int ctr = 0; ctr <= last - 1; ctr++) {
         if (ctr % 20 == 0)
            returnString += "\n   ";
         returnString += String.Format("{0:X2} ", bytes[ctr]);
      }
      return returnString;
   }
}
// The example displays the following output:
//       Strings to encode:
//          This is the first sentence.
//          This is the second sentence.
//       
//       Encoded bytes:
//       
//          54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
//          6E 74 65 6E 63 65 2E 20 54 68 69 73 20 69 73 20 74 68 65 20
//          73 65 63 6F 6E 64 20 73 65 6E 74 65 6E 63 65 2E 20
//       
//       Decoded: This is the first sentence. This is the second sentence.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim strings() As String = { "This is the first sentence. ", 
                                  "This is the second sentence. " }
      Dim asciiEncoding As Encoding = Encoding.ASCII

      ' Create array of adequate size.
      Dim bytes(50) As Byte
      ' Create index for current position of array.
      Dim index As Integer = 0

      Console.WriteLine("Strings to encode:")
      For Each stringValue In strings
         Console.WriteLine("   {0}", stringValue)

         Dim count As Integer = asciiEncoding.GetByteCount(stringValue)
         If count + index >=  bytes.Length Then
            Array.Resize(bytes, bytes.Length + 50)
         End If
         Dim written As Integer = asciiEncoding.GetBytes(stringValue, 0, 
                                                         stringValue.Length, 
                                                         bytes, index)    

         index = index + written 
      Next 
      Console.WriteLine()
      Console.WriteLine("Encoded bytes:")
      Console.WriteLine("{0}", ShowByteValues(bytes, index))
      Console.WriteLine()

      ' Decode Unicode byte array to a string.
      Dim newString As String = asciiEncoding.GetString(bytes, 0, index)
      Console.WriteLine("Decoded: {0}", newString)
   End Sub

   Private Function ShowByteValues(bytes As Byte(), last As Integer) As String
      Dim returnString As String = "   "
      For ctr As Integer = 0 To last - 1
         If ctr Mod 20 = 0 Then returnString += vbCrLf + "   "
         returnString += String.Format("{0:X2} ", bytes(ctr))
      Next
      Return returnString
   End Function
End Module
' The example displays the following output:
'       Strings to encode:
'          This is the first sentence.
'          This is the second sentence.
'       
'       Encoded bytes:
'       
'          54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
'          6E 74 65 6E 63 65 2E 20 54 68 69 73 20 69 73 20 74 68 65 20
'          73 65 63 6F 6E 64 20 73 65 6E 74 65 6E 63 65 2E 20
'       
'       Decoded: This is the first sentence. This is the second sentence.
```

<span data-ttu-id="245bb-222">Ein Decoder konvertiert ein Bytearray, das eine spezifische Zeichencodierung darstellt, in einen Satz von Zeichen, d. h. entweder in ein Zeichenarray oder in eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="245bb-222">A decoder converts a byte array that reflects a particular character encoding into a set of characters, either in a character array or in a string.</span></span> <span data-ttu-id="245bb-223">Um ein Bytearray in ein Zeichenarray zu decodieren, rufen Sie die [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[]))-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="245bb-223">To decode a byte array into a character array, you call the [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])) method.</span></span> <span data-ttu-id="245bb-224">Um ein Bytearray in eine Zeichenfolge zu decodieren, rufen Sie die [GetString](xref:System.Text.Encoding.GetString(System.Byte[]))-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="245bb-224">To decode a byte array into a string, you call the [GetString](xref:System.Text.Encoding.GetString(System.Byte[])) method.</span></span> <span data-ttu-id="245bb-225">Wenn Sie vor Ausführung der Decodierung ermitteln möchten, wie viele Zeichen zum Speichern der decodierten Bytes benötigt werden, können Sie die [GetCharCount](xref:System.Text.Encoding.GetCharCount(System.Byte[]))-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="245bb-225">If you want to determine how many characters are needed to store the decoded bytes before performing the decoding, you can call the [GetCharCount](xref:System.Text.Encoding.GetCharCount(System.Byte[])) method.</span></span>

<span data-ttu-id="245bb-226">Im folgenden Beispiel werden drei Zeichenfolgen codiert und dann in einzelnes Array von Zeichen decodiert.</span><span class="sxs-lookup"><span data-stu-id="245bb-226">The following example encodes three strings and then decodes them into a single array of characters.</span></span> <span data-ttu-id="245bb-227">Ein verwalteter Index gibt die Anfangsposition im Zeichenarray für die nächste Gruppe von decodierten Zeichen an.</span><span class="sxs-lookup"><span data-stu-id="245bb-227">It maintains an index that indicates the starting position in the character array for the next set of decoded characters.</span></span> <span data-ttu-id="245bb-228">Die [GetCharCount](xref:System.Text.Encoding.GetCharCount(System.Byte[]))-Methode wird aufgerufen, um sicherzustellen, dass das Zeichenarray groß genug für alle decodierten Zeichen ist.</span><span class="sxs-lookup"><span data-stu-id="245bb-228">It calls the [GetCharCount](xref:System.Text.Encoding.GetCharCount(System.Byte[])) method to ensure that the character array is large enough to accommodate all the decoded characters.</span></span> <span data-ttu-id="245bb-229">Die [ASCIIEncoding.GetChars(Byte[], Int32, Int32, Char[], Int32)](xref:System.Text.ASCIIEncoding.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32))-Methode wird dann zum Decodieren des Bytearrays aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="245bb-229">It then calls the [ASCIIEncoding.GetChars(Byte[], Int32, Int32, Char[], Int32)](xref:System.Text.ASCIIEncoding.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) method to decode the byte array.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      string[] strings = { "This is the first sentence. ", 
                           "This is the second sentence. ",
                           "This is the third sentence. " };
      Encoding asciiEncoding = Encoding.ASCII;
      // Array to hold encoded bytes.
      byte[] bytes;
      // Array to hold decoded characters.
      char[] chars = new char[50];
      // Create index for current position of character array.
      int index = 0;     

      foreach (var stringValue in strings) {
         Console.WriteLine("String to Encode: {0}", stringValue);
         // Encode the string to a byte array.
         bytes = asciiEncoding.GetBytes(stringValue);
         // Display the encoded bytes.
         Console.Write("Encoded bytes: ");
         for (int ctr = 0; ctr < bytes.Length; ctr++)
            Console.Write(" {0}{1:X2}", 
                          ctr % 20 == 0 ? Environment.NewLine : "", 
                          bytes[ctr]);
         Console.WriteLine();

         // Decode the bytes to a single character array.
         int count = asciiEncoding.GetCharCount(bytes);
         if (count + index >=  chars.Length)
            Array.Resize(ref chars, chars.Length + 50);

         int written = asciiEncoding.GetChars(bytes, 0, 
                                              bytes.Length, 
                                              chars, index);              
         index = index + written;
         Console.WriteLine();       
      }

      // Instantiate a single string containing the characters.
      string decodedString = new string(chars, 0, index - 1);
      Console.WriteLine("Decoded string: ");
      Console.WriteLine(decodedString);
   }
}
// The example displays the following output:
//    String to Encode: This is the first sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
//    6E 74 65 6E 63 65 2E 20
//    
//    String to Encode: This is the second sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 73 65 63 6F 6E 64 20 73
//    65 6E 74 65 6E 63 65 2E 20
//    
//    String to Encode: This is the third sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 74 68 69 72 64 20 73 65
//    6E 74 65 6E 63 65 2E 20
//    
//    Decoded string:
//    This is the first sentence. This is the second sentence. This is the third sentence.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim strings() As String = { "This is the first sentence. ", 
                                  "This is the second sentence. ",
                                  "This is the third sentence. " }
      Dim asciiEncoding As Encoding = Encoding.ASCII
      ' Array to hold encoded bytes.
      Dim bytes() As Byte
      ' Array to hold decoded characters.
      Dim chars(50) As Char
      ' Create index for current position of character array.
      Dim index As Integer     

      For Each stringValue In strings
         Console.WriteLine("String to Encode: {0}", stringValue)
         ' Encode the string to a byte array.
         bytes = asciiEncoding.GetBytes(stringValue)
         ' Display the encoded bytes.
         Console.Write("Encoded bytes: ")
         For ctr As Integer = 0 To bytes.Length - 1
            Console.Write(" {0}{1:X2}", If(ctr Mod 20 = 0, vbCrLf, ""), 
                                        bytes(ctr))
         Next         
         Console.WriteLine()

         ' Decode the bytes to a single character array.
         Dim count As Integer = asciiEncoding.GetCharCount(bytes)
         If count + index >=  chars.Length Then
            Array.Resize(chars, chars.Length + 50)
         End If
         Dim written As Integer = asciiEncoding.GetChars(bytes, 0, 
                                                         bytes.Length, 
                                                         chars, index)              
         index = index + written
         Console.WriteLine()       
      Next

      ' Instantiate a single string containing the characters.
      Dim decodedString As New String(chars, 0, index - 1)
      Console.WriteLine("Decoded string: ")
      Console.WriteLine(decodedString)
   End Sub
End Module
' The example displays the following output:
'    String to Encode: This is the first sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
'    6E 74 65 6E 63 65 2E 20
'    
'    String to Encode: This is the second sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 73 65 63 6F 6E 64 20 73
'    65 6E 74 65 6E 63 65 2E 20
'    
'    String to Encode: This is the third sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 74 68 69 72 64 20 73 65
'    6E 74 65 6E 63 65 2E 20
'    
'    Decoded string:
'    This is the first sentence. This is the second sentence. This is the third sentence.
```

<span data-ttu-id="245bb-230">Die Codierungs- und Decodierungsmethoden einer von [Encoding](xref:System.Text.Encoding) abgeleiteten Klasse sind für die Behandlung eines vollständigen Satzes von Daten vorgesehen, d.h., alle zu codierenden oder decodierenden Daten werden in einem einzelnen Methodenaufruf angegeben.</span><span class="sxs-lookup"><span data-stu-id="245bb-230">The encoding and decoding methods of a class derived from [Encoding](xref:System.Text.Encoding) are designed to work on a complete set of data; that is, all the data to be encoded or decoded is supplied in a single method call.</span></span> <span data-ttu-id="245bb-231">In einigen Fällen sind Daten jedoch in einem Stream verfügbar, und die zu codierenden und decodierenden Daten sind möglicherweise nur über separate Lesevorgänge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="245bb-231">However, in some cases, data is available in a stream, and the data to be encoded or decoded may be available only from separate read operations.</span></span> <span data-ttu-id="245bb-232">Der Codierungs- oder Decodierungsvorgang muss hierbei jeden gespeicherten Zustand aus dem vorherigen Aufruf speichern.</span><span class="sxs-lookup"><span data-stu-id="245bb-232">This requires the encoding or decoding operation to remember any saved state from its previous invocation.</span></span> <span data-ttu-id="245bb-233">Methoden von Klassen, die von [Encoder](xref:System.Text.Encoder) und [Decoder](xref:System.Text.Decoder) abgeleitet sind, können Codierungs- und Decodierungsvorgänge behandeln, die mehrere Methodenaufrufe umfassen.</span><span class="sxs-lookup"><span data-stu-id="245bb-233">Methods of classes derived from [Encoder](xref:System.Text.Encoder) and [Decoder](xref:System.Text.Decoder) are able to handle encoding and decoding operations that span multiple method calls.</span></span>

<span data-ttu-id="245bb-234">Ein [Encoder](xref:System.Text.Encoder)-Objekt für eine bestimmte Codierung ist über die [Encoding.GetEncoder](xref:System.Text.Encoding.GetEncoder)-Eigenschaft dieser Codierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="245bb-234">An [Encoder](xref:System.Text.Encoder) object for a particular encoding is available from that encoding's [Encoding.GetEncoder](xref:System.Text.Encoding.GetEncoder) property.</span></span> <span data-ttu-id="245bb-235">Ein [Decoder](xref:System.Text.Decoder)-Objekt für eine bestimmte Codierung ist über die [Encoding.GetDecoder](xref:System.Text.Encoding.GetDecoder)-Eigenschaft dieser Codierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="245bb-235">A [Decoder](xref:System.Text.Decoder) object for a particular encoding is available from that encoding's [Encoding.GetDecoder](xref:System.Text.Encoding.GetDecoder) property.</span></span> <span data-ttu-id="245bb-236">Bei Decodierungsvorgängen beinhalten die von [Decoder](xref:System.Text.Decoder) abgeleiteten Klassen eine [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32))-Methode, jedoch keine Methode, die [Encoding.GetString](xref:System.Text.Encoding.GetString(System.Byte[])) entspricht.</span><span class="sxs-lookup"><span data-stu-id="245bb-236">For decoding operations, note that classes derived from [Decoder](xref:System.Text.Decoder) include a [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) method, but they do not have a method that corresponds to [Encoding.GetString](xref:System.Text.Encoding.GetString(System.Byte[])).</span></span>

<span data-ttu-id="245bb-237">Das folgende Beispiel veranschaulicht den Unterschied zwischen der Verwendung der [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[]))-Methode und der [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32))-Methode zum Decodieren eines Unicode-Bytearrays.</span><span class="sxs-lookup"><span data-stu-id="245bb-237">The following example illustrates the difference between using the [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])) and [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) methods for decoding a Unicode byte array.</span></span> <span data-ttu-id="245bb-238">Im Beispiel wird eine Zeichenfolge, die einige Unicode-Zeichen enthält, in eine Datei codiert. Anschließend werden die Zeichen mithilfe der zwei Decodierungsmethoden immer um je zehn Bytes decodiert.</span><span class="sxs-lookup"><span data-stu-id="245bb-238">The example encodes a string that contains some Unicode characters to a file, and then uses the two decoding methods to decode them ten bytes at a time.</span></span> <span data-ttu-id="245bb-239">Da im zehnten und elften Byte ein Ersatzzeichenpaar auftritt, erfolgt die Decodierung mit separaten Methodenaufrufen.</span><span class="sxs-lookup"><span data-stu-id="245bb-239">Because a surrogate pair occurs in the tenth and eleventh bytes, it is decoded in separate method calls.</span></span> <span data-ttu-id="245bb-240">Die Ausgabe zeigt, dass die [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[]))-Methode die Bytes nicht ordnungsgemäß decodieren kann und sie stattdessen durch U+FFFD (REPLACEMENT CHARACTER) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="245bb-240">As the output shows, the [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])) method is not able to correctly decode the bytes and instead replaces them with U+FFFD (REPLACEMENT CHARACTER).</span></span> <span data-ttu-id="245bb-241">Die [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32))-Methode kann das Bytearray hingegen erfolgreich decodieren, um die ursprüngliche Zeichenfolge abzurufen.</span><span class="sxs-lookup"><span data-stu-id="245bb-241">On the other hand, the [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) method is able to successfully decode the byte array to get the original string.</span></span>

```csharp
using System;
using System.IO;
using System.Text;

public class Example
{
   public static void Main()
   {
      // Use default replacement fallback for invalid encoding.
      UnicodeEncoding enc = new UnicodeEncoding(true, false, false);

      // Define a string with various Unicode characters.
      string str1 = "AB YZ 19 \uD800\udc05 \u00e4"; 
      str1 += "Unicode characters. \u00a9 \u010C s \u0062\u0308"; 
      Console.WriteLine("Created original string...\n");

      // Convert string to byte array.                     
      byte[] bytes = enc.GetBytes(str1);

      FileStream fs = File.Create(@".\characters.bin");
      BinaryWriter bw = new BinaryWriter(fs);
      bw.Write(bytes);
      bw.Close();

      // Read bytes from file.
      FileStream fsIn = File.OpenRead(@".\characters.bin");
      BinaryReader br = new BinaryReader(fsIn);

      const int count = 10;            // Number of bytes to read at a time. 
      byte[] bytesRead = new byte[10]; // Buffer (byte array).
      int read;                        // Number of bytes actually read. 
      string str2 = String.Empty;      // Decoded string.

      // Try using Encoding object for all operations.
      do { 
         read = br.Read(bytesRead, 0, count);
         str2 += enc.GetString(bytesRead, 0, read); 
      } while (read == count);
      br.Close();
      Console.WriteLine("Decoded string using UnicodeEncoding.GetString()...");
      CompareForEquality(str1, str2);
      Console.WriteLine();

      // Use Decoder for all operations.
      fsIn = File.OpenRead(@".\characters.bin");
      br = new BinaryReader(fsIn);
      Decoder decoder = enc.GetDecoder();
      char[] chars = new char[50];
      int index = 0;                   // Next character to write in array.
      int written = 0;                 // Number of chars written to array.
      do { 
         read = br.Read(bytesRead, 0, count);
         if (index + decoder.GetCharCount(bytesRead, 0, read) - 1 >= chars.Length) 
            Array.Resize(ref chars, chars.Length + 50);

         written = decoder.GetChars(bytesRead, 0, read, chars, index);
         index += written;                          
      } while (read == count);
      br.Close();            
      // Instantiate a string with the decoded characters.
      string str3 = new String(chars, 0, index); 
      Console.WriteLine("Decoded string using UnicodeEncoding.Decoder.GetString()...");
      CompareForEquality(str1, str3); 
   }

   private static void CompareForEquality(string original, string decoded)
   {
      bool result = original.Equals(decoded);
      Console.WriteLine("original = decoded: {0}", 
                        original.Equals(decoded, StringComparison.Ordinal));
      if (! result) {
         Console.WriteLine("Code points in original string:");
         foreach (var ch in original)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
         Console.WriteLine();

         Console.WriteLine("Code points in decoded string:");
         foreach (var ch in decoded)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
         Console.WriteLine();
      }
   }
}
// The example displays the following output:
//    Created original string...
//    
//    Decoded string using UnicodeEncoding.GetString()...
//    original = decoded: False
//    Code points in original string:
//    0041 0042 0020 0059 005A 0020 0031 0039 0020 D800 DC05 0020 00E4 0055 006E 0069 0063 006F
//    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
//    0020 0073 0020 0062 0308
//    Code points in decoded string:
//    0041 0042 0020 0059 005A 0020 0031 0039 0020 FFFD FFFD 0020 00E4 0055 006E 0069 0063 006F
//    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
//    0020 0073 0020 0062 0308
//    
//    Decoded string using UnicodeEncoding.Decoder.GetString()...
//    original = decoded: True
```

```vb
Imports System.IO
Imports System.Text

Module Example
   Public Sub Main()
      ' Use default replacement fallback for invalid encoding.
      Dim enc As New UnicodeEncoding(True, False, False)

      ' Define a string with various Unicode characters.
      Dim str1 As String = String.Format("AB YZ 19 {0}{1} {2}", 
                                         ChrW(&hD800), ChrW(&hDC05), ChrW(&h00e4))
      str1 += String.Format("Unicode characters. {0} {1} s {2}{3}", 
                            ChrW(&h00a9), ChrW(&h010C), ChrW(&h0062), ChrW(&h0308))
      Console.WriteLine("Created original string...")
      Console.WriteLine()

      ' Convert string to byte array.                     
      Dim bytes() As Byte = enc.GetBytes(str1)

      Dim fs As FileStream = File.Create(".\characters.bin")
      Dim bw As New BinaryWriter(fs)
      bw.Write(bytes)
      bw.Close()

      ' Read bytes from file.
      Dim fsIn As FileStream = File.OpenRead(".\characters.bin")
      Dim br As New BinaryReader(fsIn)

      Const count As Integer = 10      ' Number of bytes to read at a time. 
      Dim bytesRead(9) As Byte         ' Buffer (byte array).
      Dim read As Integer              ' Number of bytes actually read. 
      Dim str2 As String = ""          ' Decoded string.

      ' Try using Encoding object for all operations.
      Do 
         read = br.Read(bytesRead, 0, count)
         str2 += enc.GetString(bytesRead, 0, read) 
      Loop While read = count
      br.Close()
      Console.WriteLine("Decoded string using UnicodeEncoding.GetString()...")
      CompareForEquality(str1, str2)
      Console.WriteLine()

      ' Use Decoder for all operations.
      fsIn = File.OpenRead(".\characters.bin")
      br = New BinaryReader(fsIn)
      Dim decoder As Decoder = enc.GetDecoder()
      Dim chars(50) As Char
      Dim index As Integer = 0         ' Next character to write in array.
      Dim written As Integer = 0       ' Number of chars written to array.
      Do 
         read = br.Read(bytesRead, 0, count)
         If index + decoder.GetCharCount(bytesRead, 0, read) - 1 >= chars.Length Then 
            Array.Resize(chars, chars.Length + 50)
         End If   
         written = decoder.GetChars(bytesRead, 0, read, chars, index)
         index += written                          
      Loop While read = count
      br.Close()            
      ' Instantiate a string with the decoded characters.
      Dim str3 As New String(chars, 0, index) 
      Console.WriteLine("Decoded string using UnicodeEncoding.Decoder.GetString()...")
      CompareForEquality(str1, str3) 
   End Sub

   Private Sub CompareForEquality(original As String, decoded As String)
      Dim result As Boolean = original.Equals(decoded)
      Console.WriteLine("original = decoded: {0}", 
                        original.Equals(decoded, StringComparison.Ordinal))
      If Not result Then
         Console.WriteLine("Code points in original string:")
         For Each ch In original
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()

         Console.WriteLine("Code points in decoded string:")
         For Each ch In decoded
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()
      End If
   End Sub
End Module
' The example displays the following output:
'    Created original string...
'    
'    Decoded string using UnicodeEncoding.GetString()...
'    original = decoded: False
'    Code points in original string:
'    0041 0042 0020 0059 005A 0020 0031 0039 0020 D800 DC05 0020 00E4 0055 006E 0069 0063 006F
'    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
'    0020 0073 0020 0062 0308
'    Code points in decoded string:
'    0041 0042 0020 0059 005A 0020 0031 0039 0020 FFFD FFFD 0020 00E4 0055 006E 0069 0063 006F
'    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
'    0020 0073 0020 0062 0308
'    
'    Decoded string using UnicodeEncoding.Decoder.GetString()...
'    original = decoded: True
```

## <a name="choosing-a-fallback-strategy"></a><span data-ttu-id="245bb-242">Auswählen einer Fallbackstrategie</span><span class="sxs-lookup"><span data-stu-id="245bb-242">Choosing a fallback strategy</span></span>

<span data-ttu-id="245bb-243">Wenn eine Methode versucht, ein Zeichen zu codieren oder zu decodieren, aber keine Zuordnung vorhanden ist, muss eine Fallbackstrategie implementiert werden. Diese legt fest, wie die fehlende Zuordnung behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="245bb-243">When a method tries to encode or decode a character but no mapping exists, it must implement a fallback strategy that determines how the failed mapping should be handled.</span></span> <span data-ttu-id="245bb-244">Es gibt drei Arten von Fallbackstrategien:</span><span class="sxs-lookup"><span data-stu-id="245bb-244">There are three types of fallback strategies:</span></span> 

* <span data-ttu-id="245bb-245">Fallback mit ähnlichen Zeichen</span><span class="sxs-lookup"><span data-stu-id="245bb-245">Best-fit fallback</span></span>

* <span data-ttu-id="245bb-246">Ersatzfallback</span><span class="sxs-lookup"><span data-stu-id="245bb-246">Replacement fallback</span></span>

* <span data-ttu-id="245bb-247">Ausnahmefallback</span><span class="sxs-lookup"><span data-stu-id="245bb-247">Exception fallback</span></span>

> [!IMPORTANT]
> <span data-ttu-id="245bb-248">Bei Codierungsvorgängen treten Probleme am häufigsten dann auf, wenn ein Unicode-Zeichen keiner bestimmten Codepagecodierung zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="245bb-248">The most common problems in encoding operations occur when a Unicode character cannot be mapped to a particular code page encoding.</span></span> <span data-ttu-id="245bb-249">Zu den am häufigsten auftretenden Problem bei Decodierungsvorgängen gehört es, wenn ungültige Bytefolgen nicht in gültige Unicode-Zeichen übersetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="245bb-249">The most common problems in decoding operations occur when invalid byte sequences cannot be translated into valid Unicode characters.</span></span> <span data-ttu-id="245bb-250">Aus diesen Gründen sollten Sie wissen, welche Fallbackstrategien von bestimmten Codierungsobjekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="245bb-250">For these reasons, you should know which fallback strategy a particular encoding object uses.</span></span> <span data-ttu-id="245bb-251">Nach Möglichkeit sollten Sie die von einem Codierungsobjekt verwendete Fallbackstrategie beim Instanziieren des Objekts festlegen.</span><span class="sxs-lookup"><span data-stu-id="245bb-251">Whenever possible, you should specify the fallback strategy used by an encoding object when you instantiate the object.</span></span>
 
### <a name="best-fit-fallback"></a><span data-ttu-id="245bb-252">Fallback mit ähnlichen Zeichen</span><span class="sxs-lookup"><span data-stu-id="245bb-252">Best-fit fallback</span></span>

<span data-ttu-id="245bb-253">Wenn ein Zeichen nicht über eine genaue Entsprechung in der Zielcodierung verfügt, kann der Encoder versuchen, eine Zuordnung zu einem ähnlichen Zeichen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="245bb-253">When a character does not have an exact match in the target encoding, the encoder can try to map it to a similar character.</span></span> <span data-ttu-id="245bb-254">(Ein Fallback mit ähnlichen Zeichen ist meist vielmehr ein Codierungs- als ein Decodierungsproblem.</span><span class="sxs-lookup"><span data-stu-id="245bb-254">(Best-fit fallback is mostly an encoding rather than a decoding issue.</span></span> <span data-ttu-id="245bb-255">Es gibt sehr wenige Codepages, die Zeichen enthalten, die in Unicode nicht erfolgreich zugeordnet werden können.) Der Fallback mit ähnlichen Zeichen ist die Standardeinstellung für Codepage- und DBCS-Codierungen, die von der [Encoding.GetEncoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32))-Überladung und der [Encoding.GetEncoding(String)](xref:System.Text.Encoding.GetEncoding(System.String))-Überladung abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="245bb-255">There are very few code pages that contain characters that cannot be successfully mapped to Unicode.) Best-fit fallback is the default for code page and double-byte character set encodings that are retrieved by the [Encoding.GetEncoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32)) and [Encoding.GetEncoding(String)](xref:System.Text.Encoding.GetEncoding(System.String)) overloads.</span></span>

> [!NOTE]
> <span data-ttu-id="245bb-256">Theoretisch unterstützen die in .NET bereitgestellten Unicode-Codierungsklassen ([UTF8Encoding](xref:System.Text.UTF8Encoding), [UnicodeEncoding](xref:System.Text.UnicodeEncoding) und [UTF32Encoding](xref:System.Text.UTF32Encoding)) alle Zeichen in jedem Zeichensatz, sodass sie verwendet werden können, um Probleme beim Fallback mit ähnlichen Zeichen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="245bb-256">In theory, the Unicode encoding classes provided in .NET ([UTF8Encoding](xref:System.Text.UTF8Encoding), [UnicodeEncoding](xref:System.Text.UnicodeEncoding), and [UTF32Encoding](xref:System.Text.UTF32Encoding)) support every character in every character set, so they can be used to eliminate best-fit fallback issues.</span></span> 
 

<span data-ttu-id="245bb-257">Die Strategien mit ähnlichen Zeichen variieren bei den verschiedenen Codepages und sind nicht detailliert dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="245bb-257">Best-fit strategies vary for different code pages, and they are not documented in detail.</span></span> <span data-ttu-id="245bb-258">Beispielsweise werden bei einigen Codepages lateinische Zeichen in voller Breite den gängigeren halbbreiten lateinischen Zeichen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="245bb-258">For example, for some code pages, full-width Latin characters map to the more common half-width Latin characters.</span></span> <span data-ttu-id="245bb-259">Bei anderen Codepages hingegen erfolgt diese Zuordnung nicht.</span><span class="sxs-lookup"><span data-stu-id="245bb-259">For other code pages, this mapping is not made.</span></span> <span data-ttu-id="245bb-260">Selbst bei einer aggressiven Strategie mit ähnlichen Zeichen besteht in einigen Codierungen für manche Zeichen keine denkbare Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="245bb-260">Even under an aggressive best-fit strategy, there is no imaginable fit for some characters in some encodings.</span></span> <span data-ttu-id="245bb-261">Ein chinesisches ideografisches Zeichen hat z. B. keine angemessene Zuordnung in der Codepage 1252.</span><span class="sxs-lookup"><span data-stu-id="245bb-261">For example, a Chinese ideograph has no reasonable mapping to code page 1252.</span></span> <span data-ttu-id="245bb-262">Im diesem Fall wird eine Ersatzzeichenfolge verwendet.</span><span class="sxs-lookup"><span data-stu-id="245bb-262">In this case, a replacement string is used.</span></span> <span data-ttu-id="245bb-263">Standardmäßig handelt es sich bei dieser Zeichenfolge um ein einzelnes QUESTION MARK (Fragezeichen, U+003F).</span><span class="sxs-lookup"><span data-stu-id="245bb-263">By default, this string is just a single QUESTION MARK (U+003F).</span></span>

<span data-ttu-id="245bb-264">Im folgenden Beispiel wird die Codepage 1252 (Windows-Codepage für westeuropäische Sprachen) verwendet, um eine Zuordnung mit ähnlichen Zeichen und deren Nachteile zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="245bb-264">The following example uses code page 1252 (the Windows code page for Western European languages) to illustrate best-fit mapping and its drawbacks.</span></span> <span data-ttu-id="245bb-265">Die [Encoding.GetEncoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32))-Methode wird verwendet, um ein Codierungsobjekt für Codepage 1252 abzurufen.</span><span class="sxs-lookup"><span data-stu-id="245bb-265">The [Encoding.GetEncoding(Int32](xref:System.Text.Encoding.GetEncoding(System.Int32)) method is used to retrieve an encoding object for code page 1252.</span></span> <span data-ttu-id="245bb-266">Standardmäßig wird eine Zuordnung mit ähnlichen Zeichen für nicht unterstützte Unicode-Zeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="245bb-266">By default, it uses a best-fit mapping for Unicode characters that it does not support.</span></span> <span data-ttu-id="245bb-267">Im Beispiel wird eine Zeichenfolge instanziiert, die drei durch Leerzeichen getrennte Nicht-ASCII-Zeichen enthält: CIRCLED LATIN CAPITAL LETTER S (eingekreister lateinischer Großbuchstabe S, U+24C8), SUPERSCRIPT FIVE (hochgestellte Fünf, U+2075) und INFINITY (Unendlichkeit, U+221E).</span><span class="sxs-lookup"><span data-stu-id="245bb-267">The example instantiates a string that contains three non-ASCII characters - CIRCLED LATIN CAPITAL LETTER S (U+24C8), SUPERSCRIPT FIVE (U+2075), and INFINITY (U+221E) - separated by spaces.</span></span> <span data-ttu-id="245bb-268">Die Ausgabe im Beispiel zeigt, dass die drei ursprünglichen Nicht-Leerzeichen bei der Codierung der Zeichenfolge durch QUESTION MARK (Fragezeichen, U+003F), DIGIT FIVE (Ziffer Fünf, U+0035) und DIGIT EIGHT (Ziffer Acht, U+0038) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="245bb-268">As the output from the example shows, when the string is encoded, the three original non-space characters are replaced by QUESTION MARK (U+003F), DIGIT FIVE (U+0035), and DIGIT EIGHT (U+0038).</span></span> <span data-ttu-id="245bb-269">Insbesondere DIGIT EIGHT (Ziffer Acht) ist ein ungeeigneter Ersatz für das nicht unterstützte INFINITY-Zeichen (Unendlichkeit), und QUESTION MARK (Fragezeichen) weist darauf hin, dass für das ursprüngliche Zeichen keine Zuordnung verfügbar war.</span><span class="sxs-lookup"><span data-stu-id="245bb-269">DIGIT EIGHT is a particularly poor replacement for the unsupported INFINITY character, and QUESTION MARK indicates that no mapping was available for the original character.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      // Get an encoding for code page 1252 (Western Europe character set).
      Encoding cp1252 = Encoding.GetEncoding(1252);

      // Define and display a string.
      string str = "\u24c8 \u2075 \u221e";
      Console.WriteLine("Original string: " + str);
      Console.Write("Code points in string: ");
      foreach (var ch in str)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");   

      // Encode a Unicode string.
      Byte[] bytes = cp1252.GetBytes(str);
      Console.Write("Encoded bytes: ");
      foreach (byte byt in bytes)
         Console.Write("{0:X2} ", byt);
      Console.WriteLine("\n");

      // Decode the string.
      string str2 = cp1252.GetString(bytes);
      Console.WriteLine("String round-tripped: {0}", str.Equals(str2));
      if (! str.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
      }
   }
}
// The example displays the following output:
//       Original string: Ⓢ ⁵ ∞
//       Code points in string: 24C8 0020 2075 0020 221E
//       
//       Encoded bytes: 3F 20 35 20 38
//       
//       String round-tripped: False
//       ? 5 8
//       003F 0020 0035 0020 0038
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      ' Get an encoding for code page 1252 (Western Europe character set).
      Dim cp1252 As Encoding = Encoding.GetEncoding(1252)

      ' Define and display a string.
      Dim str As String = String.Format("{0} {1} {2}", ChrW(&h24c8), ChrW(&H2075), ChrW(&h221E))
      Console.WriteLine("Original string: " + str)
      Console.Write("Code points in string: ")
      For Each ch In str
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next
      Console.WriteLine()   
      Console.WriteLine()

      ' Encode a Unicode string.
      Dim bytes() As Byte = cp1252.GetBytes(str)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the string.
      Dim str2 As String = cp1252.GetString(bytes)
      Console.WriteLine("String round-tripped: {0}", str.Equals(str2))
      If Not str.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
      End If
   End Sub
End Module
' The example displays the following output:
'       Original string: Ⓢ ⁵ ∞
'       Code points in string: 24C8 0020 2075 0020 221E
'       
'       Encoded bytes: 3F 20 35 20 38
'       
'       String round-tripped: False
'       ? 5 8
'       003F 0020 0035 0020 0038
```

<span data-ttu-id="245bb-270">Die Zuordnung mit ähnlichen Zeichen ist das Standardverhalten für ein [Encoding](xref:System.Text.Encoding)-Objekt, das Unicode-Daten in Codepagedaten codiert. Es gibt ältere Anwendungen, die auf diesem Verhalten basieren.</span><span class="sxs-lookup"><span data-stu-id="245bb-270">Best-fit mapping is the default behavior for an [Encoding](xref:System.Text.Encoding) object that encodes Unicode data into code page data, and there are legacy applications that rely on this behavior.</span></span> <span data-ttu-id="245bb-271">In den meisten neuen Anwendungen sollte dieses Verhalten jedoch aus Sicherheitsgründen vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="245bb-271">However, most new applications should avoid best-fit behavior for security reasons.</span></span> <span data-ttu-id="245bb-272">Durch eine Codierung mit ähnlichen Zeichen sollten Anwendungen z. B. keinen Domänennamen ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="245bb-272">For example, applications should not put a domain name through a best-fit encoding.</span></span>

> [!Note]
> <span data-ttu-id="245bb-273">Sie können für eine Codierung auch eine benutzerdefinierte Zuordnung mit einem Fallback mit ähnlichen Zeichen implementieren.</span><span class="sxs-lookup"><span data-stu-id="245bb-273">You can also implement a custom best-fit fallback mapping for an encoding.</span></span> <span data-ttu-id="245bb-274">Weitere Informationen finden Sie im Abschnitt [Implementieren einer benutzerdefinierten Fallbackstrategie](#implementing-a-custom-fallback-strategy).</span><span class="sxs-lookup"><span data-stu-id="245bb-274">For more information, see the [Implementing a custom fallback strategy](#implementing-a-custom-fallback-strategy) section.</span></span>
 
<span data-ttu-id="245bb-275">Wenn der Fallback mit ähnlichen Zeichen die Standardeinstellung für ein Codierungsobjekt ist, können Sie eine andere Fallbackstrategie auswählen, wenn Sie ein [Encoding](xref:System.Text.Encoding)-Objekt durch Aufrufen von [Encoding.GetEncoding(Int32, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)) abrufen oder mit [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)) überladen.</span><span class="sxs-lookup"><span data-stu-id="245bb-275">If best-fit fallback is the default for an encoding object, you can choose another fallback strategy when you retrieve an [Encoding](xref:System.Text.Encoding) object by calling the [Encoding.GetEncoding(Int32, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)) or [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)) overload.</span></span> <span data-ttu-id="245bb-276">Der folgende Abschnitt enthält ein Beispiel, in dem jedes Zeichen, das Codepage 1252 nicht zugeordnet werden kann, durch ein Sternchen (\*) ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="245bb-276">The following section includes an example that replaces each character that cannot be mapped to code page 1252 with an asterisk (\*).</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding cp1252r = Encoding.GetEncoding(1252, 
                                  new EncoderReplacementFallback("*"),
                                  new DecoderReplacementFallback("*"));

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine();

      byte[] bytes = cp1252r.GetBytes(str1);
      string str2 = cp1252r.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       Round-trip: False
//       * * *
//       002A 0020 002A 0020 002A
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim cp1252r As Encoding = Encoding.GetEncoding(1252, 
                                         New EncoderReplacementFallback("*"),
                                         New DecoderReplacementFallback("*"))

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()

      Dim bytes() As Byte = cp1252r.GetBytes(str1)
      Dim str2 As String = cp1252r.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       Round-trip: False
'       * * *
'       002A 0020 002A 0020 002A
```

### <a name="replacement-fallback"></a><span data-ttu-id="245bb-277">Ersatzfallback</span><span class="sxs-lookup"><span data-stu-id="245bb-277">Replacement fallback</span></span>

<span data-ttu-id="245bb-278">Wenn ein Zeichen nicht über eine genaue Entsprechung im Zielschema verfügt und kein entsprechendes Zeichen für eine Zuordnung vorhanden ist, kann die Anwendung ein Ersatzzeichen oder eine Ersatzzeichenfolge angeben.</span><span class="sxs-lookup"><span data-stu-id="245bb-278">When a character does not have an exact match in the target scheme, but there is no appropriate character that it can be mapped to, the application can specify a replacement character or string.</span></span> <span data-ttu-id="245bb-279">Dies ist das Standardverhalten für den Unicode-Decoder, der jede&2;-Byte-Sequenz ersetzt, die nicht mit REPLACEMENT_CHARACTER (Ersatzzeichen, U+FFFD) decodiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="245bb-279">This is the default behavior for the Unicode decoder, which replaces any two-byte sequence that it cannot decode with REPLACEMENT_CHARACTER (U+FFFD).</span></span> <span data-ttu-id="245bb-280">Dies ist auch das Standardverhalten der [ASCIIEncoding](xref:System.Text.ASCIIEncoding)-Klasse, die jedes Zeichen, das nicht codiert oder decodiert werden kann, durch ein Fragezeichen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="245bb-280">It is also the default behavior of the [ASCIIEncoding](xref:System.Text.ASCIIEncoding) class, which replaces each character that it cannot encode or decode with a question mark.</span></span> <span data-ttu-id="245bb-281">Das folgende Beispiel veranschaulicht das Ersetzen von Zeichen für die Unicode-Zeichenfolge aus dem vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="245bb-281">The following example illustrates character replacement for the Unicode string from the previous example.</span></span> <span data-ttu-id="245bb-282">Wie die Ausgabe zeigt, wird jedes Zeichen, das nicht in einen ASCII-Bytewert decodiert werden kann, durch 0x3F ersetzt, dem ASCII-Code für ein Fragezeichen.</span><span class="sxs-lookup"><span data-stu-id="245bb-282">As the output shows, each character that cannot be decoded into an ASCII byte value is replaced by 0x3F, which is the ASCII code for a question mark.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding enc = Encoding.ASCII;

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");

      // Encode the original string using the ASCII encoder.
      byte[] bytes = enc.GetBytes(str1);
      Console.Write("Encoded bytes: ");
      foreach (var byt in bytes)
         Console.Write("{0:X2} ", byt);
      Console.WriteLine("\n");

      // Decode the ASCII bytes.
      string str2 = enc.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       
//       Encoded bytes: 3F 20 3F 20 3F
//       
//       Round-trip: False
//       ? ? ?
//       003F 0020 003F 0020 003F
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim enc As Encoding = Encoding.Ascii

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()
      Console.WriteLine() 

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = enc.GetBytes(str1)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Dim str2 As String = enc.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       
'       Encoded bytes: 3F 20 3F 20 3F
'       
'       Round-trip: False
'       ? ? ?
'       003F 0020 003F 0020 003F
```

<span data-ttu-id="245bb-283">.NET enthält die [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback)-Klasse und die [DecoderReplacementFallback](xref:System.Text.DecoderReplacementFallback)-Klasse, die eine Ersatzzeichenfolge verwenden, wenn in einem Codierungs- oder Decodierungsvorgang keine genaue Zuordnung für ein Zeichen möglich ist.</span><span class="sxs-lookup"><span data-stu-id="245bb-283">.NET includes the [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) and [DecoderReplacementFallback](xref:System.Text.DecoderReplacementFallback) classes, which substitute a replacement string if a character does not map exactly in an encoding or decoding operation.</span></span> <span data-ttu-id="245bb-284">Standardmäßig ist diese Ersatzzeichenfolge ein Fragezeichen. Sie können jedoch eine Klassenkonstruktorüberladung aufrufen, um eine andere Zeichenfolge auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="245bb-284">By default, this replacement string is a question mark, but you can call a class constructor overload to choose a different string.</span></span> <span data-ttu-id="245bb-285">In der Regel handelt es sich bei der Ersatzzeichenfolge um ein einzelnes Zeichen. Dies ist aber nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="245bb-285">Typically, the replacement string is a single character, although this is not a requirement.</span></span> <span data-ttu-id="245bb-286">Im folgenden Beispiel wird das Verhalten des Encoders für Codepage 1252 geändert, indem ein [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback)-Objekt instanziiert wird, das ein Sternchen (\*) als Ersatzzeichenfolge verwendet.</span><span class="sxs-lookup"><span data-stu-id="245bb-286">The following example changes the behavior of the code page 1252 encoder by instantiating an [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) object that uses an asterisk (\*) as a replacement string.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding cp1252r = Encoding.GetEncoding(1252, 
                                  new EncoderReplacementFallback("*"),
                                  new DecoderReplacementFallback("*"));

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine();

      byte[] bytes = cp1252r.GetBytes(str1);
      string str2 = cp1252r.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       Round-trip: False
//       * * *
//       002A 0020 002A 0020 002A
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim cp1252r As Encoding = Encoding.GetEncoding(1252, 
                                         New EncoderReplacementFallback("*"),
                                         New DecoderReplacementFallback("*"))

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()

      Dim bytes() As Byte = cp1252r.GetBytes(str1)
      Dim str2 As String = cp1252r.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       Round-trip: False
'       * * *
'       002A 0020 002A 0020 002A
```

> [!NOTE]
> <span data-ttu-id="245bb-287">Sie können für eine Codierung auch eine Ersatzklasse implementieren.</span><span class="sxs-lookup"><span data-stu-id="245bb-287">You can also implement a replacement class for an encoding.</span></span> <span data-ttu-id="245bb-288">Weitere Informationen finden Sie im Abschnitt [Implementieren einer benutzerdefinierten Fallbackstrategie](#implementing-a-custom-fallback-strategy).</span><span class="sxs-lookup"><span data-stu-id="245bb-288">For more information, see the [Implementing a custom fallback strategy](#implementing-a-custom-fallback-strategy) section.</span></span>
 
<span data-ttu-id="245bb-289">Zusätzlich zu QUESTION MARK (Fragezeichen, U+003F) wird in der Regel REPLACEMENT CHARACTER (Unicode-Ersatzzeichen, U+FFFD) als Ersatzzeichenfolge verwendet, insbesondere bei der Decodierung von Bytesequenzen, die nicht erfolgreich in Unicode-Zeichen übersetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="245bb-289">In addition to QUESTION MARK (U+003F), the Unicode REPLACEMENT CHARACTER (U+FFFD) is commonly used as a replacement string, particularly when decoding byte sequences that cannot be successfully translated into Unicode characters.</span></span> <span data-ttu-id="245bb-290">Allerdings können Sie eine beliebige Ersatzzeichenfolge auswählen, die mehrere Zeichen enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="245bb-290">However, you are free to choose any replacement string, and it can contain multiple characters.</span></span>

### <a name="exception-fallback"></a><span data-ttu-id="245bb-291">Ausnahmefallback</span><span class="sxs-lookup"><span data-stu-id="245bb-291">Exception fallback</span></span>

<span data-ttu-id="245bb-292">Anstatt einen Fallback mit ähnlichen Zeichen oder eine Ersatzzeichenfolge bereitzustellen, kann ein Encoder eine [EncoderFallbackException](xref:System.Text.EncoderFallbackException) auslösen, wenn die Codierung eines Satzes von Zeichen nicht möglich ist, und ein Decoder kann eine [DecoderFallbackException](xref:System.Text.DecoderFallbackException) auslösen, wenn ein Bytearray nicht decodiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="245bb-292">Instead of providing a best-fit fallback or a replacement string, an encoder can throw an [EncoderFallbackException](xref:System.Text.EncoderFallbackException) if it is unable to encode a set of characters, and a decoder can throw a [DecoderFallbackException](xref:System.Text.DecoderFallbackException) if it is unable to decode a byte array.</span></span> <span data-ttu-id="245bb-293">Um eine Ausnahme in Codierungs- und Decodierungsvorgängen auszulösen, übergeben Sie ein [EncoderFallbackException](xref:System.Text.EncoderFallbackException)-Objekt – bzw. ein [DecoderFallbackException](xref:System.Text.DecoderFallbackException)-Objekt – an die [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback))-Methode.</span><span class="sxs-lookup"><span data-stu-id="245bb-293">To throw an exception in encoding and decoding operations, you supply an [EncoderFallbackException](xref:System.Text.EncoderFallbackException) object and a [DecoderFallbackException](xref:System.Text.DecoderFallbackException) object, respectively, to the [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)) method.</span></span> <span data-ttu-id="245bb-294">Im folgenden Beispiel wird ein Ausnahmefallback mit der ASCIIEncoding-Klasse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="245bb-294">The following example illustrates exception fallback with the ASCIIEncoding class.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding enc = Encoding.GetEncoding("us-ascii", 
                                          new EncoderExceptionFallback(), 
                                          new DecoderExceptionFallback());

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");

      // Encode the original string using the ASCII encoder.
      byte[] bytes = {};
      try {
         bytes = enc.GetBytes(str1);
         Console.Write("Encoded bytes: ");
         foreach (var byt in bytes)
            Console.Write("{0:X2} ", byt);

         Console.WriteLine();
      }
      catch (EncoderFallbackException e) {
         Console.Write("Exception: ");
         if (e.IsUnknownSurrogate())
            Console.WriteLine("Unable to encode surrogate pair 0x{0:X4} 0x{1:X3} at index {2}.", 
                              Convert.ToUInt16(e.CharUnknownHigh), 
                              Convert.ToUInt16(e.CharUnknownLow), 
                              e.Index);
         else
            Console.WriteLine("Unable to encode 0x{0:X4} at index {1}.", 
                              Convert.ToUInt16(e.CharUnknown), 
                              e.Index);
         return;
      }
      Console.WriteLine();

      // Decode the ASCII bytes.
      try {
         string str2 = enc.GetString(bytes);
         Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
         if (! str1.Equals(str2)) {
            Console.WriteLine(str2);
            foreach (var ch in str2)
               Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

            Console.WriteLine();
         } 
      }
      catch (DecoderFallbackException e) {
         Console.Write("Unable to decode byte(s) ");
         foreach (byte unknown in e.BytesUnknown)
            Console.Write("0x{0:X2} ");

         Console.WriteLine("at index {0}", e.Index);
      }
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       
//       Exception: Unable to encode 0x24C8 at index 0.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim enc As Encoding = Encoding.GetEncoding("us-ascii", 
                                                 New EncoderExceptionFallback(), 
                                                 New DecoderExceptionFallback())

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()
      Console.WriteLine() 

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = {}
      Try
         bytes = enc.GetBytes(str1)
         Console.Write("Encoded bytes: ")
         For Each byt In bytes
            Console.Write("{0:X2} ", byt)
         Next
         Console.WriteLine()
      Catch e As EncoderFallbackException
         Console.Write("Exception: ")
         If e.IsUnknownSurrogate() Then
            Console.WriteLine("Unable to encode surrogate pair 0x{0:X4} 0x{1:X3} at index {2}.", 
                              Convert.ToUInt16(e.CharUnknownHigh), 
                              Convert.ToUInt16(e.CharUnknownLow), 
                              e.Index)
         Else
            Console.WriteLine("Unable to encode 0x{0:X4} at index {1}.", 
                              Convert.ToUInt16(e.CharUnknown), 
                              e.Index)
         End If                              
         Exit Sub
      End Try
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Try
         Dim str2 As String = enc.GetString(bytes)
         Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
         If Not str1.Equals(str2) Then
            Console.WriteLine(str2)
            For Each ch In str2
               Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
            Next    
            Console.WriteLine()
         End If 
      Catch e As DecoderFallbackException
         Console.Write("Unable to decode byte(s) ")
         For Each unknown As Byte In e.BytesUnknown
            Console.Write("0x{0:X2} ")
         Next
         Console.WriteLine("at index {0}", e.Index)
      End Try
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       
'       Exception: Unable to encode 0x24C8 at index 0.
```

> [!NOTE]
> <span data-ttu-id="245bb-295">Sie können für einen Codierungsvorgang auch einen benutzerdefinierten Ausnahmehandler implementieren.</span><span class="sxs-lookup"><span data-stu-id="245bb-295">You can also implement a custom exception handler for an encoding operation.</span></span> <span data-ttu-id="245bb-296">Weitere Informationen finden Sie im Abschnitt [Implementieren einer benutzerdefinierten Fallbackstrategie](#implementing-a-custom-fallback-strategy).</span><span class="sxs-lookup"><span data-stu-id="245bb-296">For more information, see the [Implementing a custom fallback strategy](#implementing-a-custom-fallback-strategy) section.</span></span>
 
<span data-ttu-id="245bb-297">Das [EncoderFallbackException](xref:System.Text.EncoderFallbackException)- und [DecoderFallbackException](xref:System.Text.DecoderFallbackException)-Objekt stellen die folgenden Informationen über die Bedingung bereit, durch die die Ausnahme ausgelöst wurde:</span><span class="sxs-lookup"><span data-stu-id="245bb-297">The [EncoderFallbackException](xref:System.Text.EncoderFallbackException) and [DecoderFallbackException](xref:System.Text.DecoderFallbackException) objects provide the following information about the condition that caused the exception:</span></span> 

* <span data-ttu-id="245bb-298">Das [EncoderFallbackException](xref:System.Text.EncoderFallbackException)-Objekt enthält eine [IsUnknownSurrogate](xref:System.Text.EncoderFallbackException.IsUnknownSurrogate)-Methode, die angibt, ob die Zeichen, die nicht codiert werden können, ein unbekanntes Ersatzzeichenpaar darstellen (in diesem Fall gibt die Methode `true` zurück), oder ob sie ein unbekanntes einzelnes Zeichen darstellen (in diesem Fall gibt die Methode `false` zurück).</span><span class="sxs-lookup"><span data-stu-id="245bb-298">The [EncoderFallbackException](xref:System.Text.EncoderFallbackException) object includes an [IsUnknownSurrogate](xref:System.Text.EncoderFallbackException.IsUnknownSurrogate) method, which indicates whether the character or characters that cannot be encoded represent an unknown surrogate pair (in which case, the method returns `true`) or an unknown single character (in which case, the method returns `false`).</span></span> <span data-ttu-id="245bb-299">Die Zeichen im Ersatzzeichenpaar sind in den Eigenschaften [EncoderFallbackException.CharUnknownHigh](xref:System.Text.EncoderFallbackException.CharUnknownHigh) und [EncoderFallbackException.CharUnknownLow](xref:System.Text.EncoderFallbackException.CharUnknownLow) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="245bb-299">The characters in the surrogate pair are available from the [EncoderFallbackException.CharUnknownHigh](xref:System.Text.EncoderFallbackException.CharUnknownHigh) and [EncoderFallbackException.CharUnknownLow](xref:System.Text.EncoderFallbackException.CharUnknownLow) properties.</span></span> <span data-ttu-id="245bb-300">Das unbekannte einzelne Zeichen ist in der Eigenschaft [EncoderFallbackException.CharUnknown](xref:System.Text.EncoderFallbackException.CharUnknown) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="245bb-300">The unknown single character is available from the [EncoderFallbackException.CharUnknown](xref:System.Text.EncoderFallbackException.CharUnknown) property.</span></span> <span data-ttu-id="245bb-301">Die [EncoderFallbackException.Index](xref:System.Text.EncoderFallbackException.Index)-Eigenschaft gibt die Position in der Zeichenfolge an, an der das erste Zeichen gefunden wurde, das nicht codiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="245bb-301">The [EncoderFallbackException.Index](xref:System.Text.EncoderFallbackException.Index) property indicates the position in the string at which the first character that could not be encoded was found.</span></span>

* <span data-ttu-id="245bb-302">Das [DecoderFallbackException](xref:System.Text.DecoderFallbackException)-Objekt enthält eine [BytesUnknown](xref:System.Text.DecoderFallbackException.BytesUnknown)-Eigenschaft, die ein Bytearray zurückgibt, das nicht decodiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="245bb-302">The [DecoderFallbackException](xref:System.Text.DecoderFallbackException) object includes a [BytesUnknown](xref:System.Text.DecoderFallbackException.BytesUnknown) property that returns an array of bytes that cannot be decoded.</span></span> <span data-ttu-id="245bb-303">Die [DecoderFallbackException.Index](xref:System.Text.DecoderFallbackException.Index)-Eigenschaft gibt die Anfangsposition der unbekannten Bytes an.</span><span class="sxs-lookup"><span data-stu-id="245bb-303">The [DecoderFallbackException.Index](xref:System.Text.DecoderFallbackException.Index) property indicates the starting position of the unknown bytes.</span></span>

<span data-ttu-id="245bb-304">Obwohl das [EncoderFallbackException](xref:System.Text.EncoderFallbackException)- und [DecoderFallbackException](xref:System.Text.DecoderFallbackException)-Objekt angemessene Diagnoseinformationen zu der Ausnahme bereitstellen, ermöglichen sie keinen Zugriff auf den Codierungs- oder Decodierungspuffer.</span><span class="sxs-lookup"><span data-stu-id="245bb-304">Although the [EncoderFallbackException](xref:System.Text.EncoderFallbackException) and [DecoderFallbackException](xref:System.Text.DecoderFallbackException) objects provide adequate diagnostic information about the exception, they do not provide access to the encoding or decoding buffer.</span></span> <span data-ttu-id="245bb-305">Daher ist es nicht möglich, innerhalb der Codierungs- oder Decodierungsmethode ungültige Daten zu ersetzen oder zu korrigieren.</span><span class="sxs-lookup"><span data-stu-id="245bb-305">Therefore, they do not allow invalid data to be replaced or corrected within the encoding or decoding method.</span></span>

## <a name="implementing-a-custom-fallback-strategy"></a><span data-ttu-id="245bb-306">Implementieren einer benutzerdefinierten Fallbackstrategie</span><span class="sxs-lookup"><span data-stu-id="245bb-306">Implementing a custom fallback strategy</span></span>

<span data-ttu-id="245bb-307">Neben der Zuordnung mit ähnlichen Zeichen, die intern von Codepages implementiert wird, beinhaltet .NET die folgenden Klassen für die Implementierung einer Fallbackstrategie:</span><span class="sxs-lookup"><span data-stu-id="245bb-307">In addition to the best-fit mapping that is implemented internally by code pages, .NET includes the following classes for implementing a fallback strategy:</span></span>

* <span data-ttu-id="245bb-308">Verwenden Sie [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) und [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer), um Zeichen in Codierungsvorgängen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="245bb-308">Use [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) and [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) to replace characters in encoding operations.</span></span>

* <span data-ttu-id="245bb-309">Verwenden Sie [DecoderReplacementFallback](xref:System.Text.DecoderReplacementFallback) und [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer), um Zeichen in Decodierungsvorgängen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="245bb-309">Use [DecoderReplacementFallback](xref:System.Text.DecoderReplacementFallback) and [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) to replace characters in decoding operations.</span></span>

* <span data-ttu-id="245bb-310">Verwenden Sie [EncoderExceptionFallback](xref:System.Text.EncoderExceptionFallback) und [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) zum Auslösen einer [EncoderFallbackException](xref:System.Text.EncoderFallbackException), wenn ein Zeichen nicht codiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="245bb-310">Use [EncoderExceptionFallback](xref:System.Text.EncoderExceptionFallback) and [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) to throw an [EncoderFallbackException](xref:System.Text.EncoderFallbackException) when a character cannot be encoded.</span></span>

* <span data-ttu-id="245bb-311">Verwenden Sie [DecoderExceptionFallback](xref:System.Text.DecoderExceptionFallback) und [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) zum Auslösen einer [DecoderFallbackException](xref:System.Text.DecoderFallbackException), wenn ein Zeichen nicht decodiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="245bb-311">Use [DecoderExceptionFallback](xref:System.Text.DecoderExceptionFallback) and [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) to throw a [DecoderFallbackException](xref:System.Text.DecoderFallbackException) when a character cannot be decoded.</span></span>

<span data-ttu-id="245bb-312">Darüber hinaus können Sie eine benutzerdefinierte Lösung implementieren, die den Fallback mit ähnlichen Zeichen, den Ersatzfallback oder den Ausnahmefallback verwendet. Führen Sie hierzu folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="245bb-312">In addition, you can implement a custom solution that uses best-fit fallback, replacement fallback, or exception fallback, by following these steps:</span></span> 

1. <span data-ttu-id="245bb-313">Leiten Sie für Codierungsvorgänge eine Klasse von [EncoderFallback](xref:System.Text.EncoderFallback) und für Decodierungsvorgänge eine Klasse von [DecoderFallback](xref:System.Text.DecoderFallback) ab.</span><span class="sxs-lookup"><span data-stu-id="245bb-313">Derive a class from [EncoderFallback](xref:System.Text.EncoderFallback) for encoding operations, and from [DecoderFallback](xref:System.Text.DecoderFallback) for decoding operations.</span></span>

2. <span data-ttu-id="245bb-314">Leiten Sie für Codierungsvorgänge eine Klasse von [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) und für Decodierungsvorgänge eine Klasse von [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) ab.</span><span class="sxs-lookup"><span data-stu-id="245bb-314">Derive a class from [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) for encoding operations, and from [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) for decoding operations.</span></span>

3. <span data-ttu-id="245bb-315">Wenn die vordefinierte [EncoderFallbackException](xref:System.Text.EncoderFallbackException)- und [DecoderFallbackException](xref:System.Text.DecoderFallbackException)-Klasse nicht Ihren Bedürfnissen entspricht, leiten Sie für den Ausnahmefallback eine Klasse von einem Ausnahmeobjekt ab, z.B. [Exception](xref:System.Exception) oder [ArgumentException](xref:System.ArgumentException).</span><span class="sxs-lookup"><span data-stu-id="245bb-315">For exception fallback, if the predefined [EncoderFallbackException](xref:System.Text.EncoderFallbackException) and [DecoderFallbackException](xref:System.Text.DecoderFallbackException) classes do not meet your needs, derive a class from an exception object such as [Exception](xref:System.Exception) or [ArgumentException](xref:System.ArgumentException).</span></span>

### <a name="deriving-from-encoderfallback-or-decoderfallback"></a><span data-ttu-id="245bb-316">Ableiten von EncoderFallback oder DecoderFallback</span><span class="sxs-lookup"><span data-stu-id="245bb-316">Deriving from EncoderFallback or DecoderFallback</span></span>

<span data-ttu-id="245bb-317">Um eine benutzerdefinierte Fallbacklösung zu implementieren, müssen Sie für Codierungsvorgänge eine Klasse erstellen, die von [EncoderFallback](xref:System.Text.EncoderFallback) erbt. Für Decodierungsvorgänge erstellen Sie eine Klasse, die von [DecoderFallback](xref:System.Text.DecoderFallback) erbt.</span><span class="sxs-lookup"><span data-stu-id="245bb-317">To implement a custom fallback solution, you must create a class that inherits from [EncoderFallback](xref:System.Text.EncoderFallback) for encoding operations, and from [DecoderFallback](xref:System.Text.DecoderFallback) for decoding operations.</span></span> <span data-ttu-id="245bb-318">Instanzen dieser Klassen werden an die [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback))-Methode übergeben und dienen als Vermittler zwischen der Codierungsklasse und der Fallbackimplementierung.</span><span class="sxs-lookup"><span data-stu-id="245bb-318">Instances of these classes are passed to the [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)) method and serve as the intermediary between the encoding class and the fallback implementation.</span></span>

<span data-ttu-id="245bb-319">Beim Erstellen einer benutzerdefinierten Fallbacklösung für einen Encoder oder einen Decoder müssen Sie die folgenden Member implementieren:</span><span class="sxs-lookup"><span data-stu-id="245bb-319">When you create a custom fallback solution for an encoder or decoder, you must implement the following members:</span></span>

* <span data-ttu-id="245bb-320">Die [EncoderFallback.MaxCharCount](xref:System.Text.EncoderFallback.MaxCharCount)-Eigenschaft oder die [DecoderFallback.MaxCharCount](xref:System.Text.DecoderFallback.MaxCharCount)-Eigenschaft, die die höchstmögliche Anzahl von Zeichen zurückgibt, die der Fallback mit ähnlichen Zeichen, der Ersatz- oder der Ausnahmefallback zurückgeben kann, um ein einzelnes Zeichen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="245bb-320">The [EncoderFallback.MaxCharCount](xref:System.Text.EncoderFallback.MaxCharCount) or [DecoderFallback.MaxCharCount](xref:System.Text.DecoderFallback.MaxCharCount) property, which returns the maximum possible number of characters that the best-fit, replacement, or exception fallback can return to replace a single character.</span></span> <span data-ttu-id="245bb-321">Für einen benutzerdefinierten Ausnahmefallback ist der Wert Null.</span><span class="sxs-lookup"><span data-stu-id="245bb-321">For a custom exception fallback, its value is zero.</span></span> 

* <span data-ttu-id="245bb-322">Die [EncoderFallback.CreateFallbackBuffer](xref:System.Text.EncoderFallback.CreateFallbackBuffer)- oder [DecoderFallback.CreateFallbackBuffer](xref:System.Text.DecoderFallback.CreateFallbackBuffer)-Methode, die Ihre benutzerdefinierte [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer)- oder [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer)-Implementierung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="245bb-322">The [EncoderFallback.CreateFallbackBuffer](xref:System.Text.EncoderFallback.CreateFallbackBuffer) or [DecoderFallback.CreateFallbackBuffer](xref:System.Text.DecoderFallback.CreateFallbackBuffer) method, which returns your custom [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) or [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) implementation.</span></span> <span data-ttu-id="245bb-323">Die Methode wird vom Encoder aufgerufen, wenn das erste Zeichen erkannt wird, das nicht erfolgreich codiert werden kann, oder vom Decoder, wenn das erste Byte erkannt wird, das nicht erfolgreich decodiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="245bb-323">The method is called by the encoder when it encounters the first character that it is unable to successfully encode, or by the decoder when it encounters the first byte that it is unable to successfully decode.</span></span>

### <a name="deriving-from-encoderfallbackbuffer-or-decoderfallbackbuffer"></a><span data-ttu-id="245bb-324">Ableiten von EncoderFallbackBuffer oder DecoderFallbackBuffer</span><span class="sxs-lookup"><span data-stu-id="245bb-324">Deriving from EncoderFallbackBuffer or DecoderFallbackBuffer</span></span>

<span data-ttu-id="245bb-325">Um eine benutzerdefinierte Fallbacklösung zu implementieren, müssen Sie für Codierungsvorgänge außerdem eine Klasse erstellen, die von [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) erbt. Für Decodierungsvorgänge erstellen Sie eine Klasse, die von [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) erbt.</span><span class="sxs-lookup"><span data-stu-id="245bb-325">To implement a custom fallback solution, you must also create a class that inherits from [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) for encoding operations, and from [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) for decoding operations.</span></span> <span data-ttu-id="245bb-326">Instanzen dieser Klassen werden von der `CreateFallbackBuffer`-Methode der [EncoderFallback](xref:System.Text.EncoderFallback)- und [DecoderFallback](xref:System.Text.DecoderFallback)-Klasse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="245bb-326">Instances of these classes are returned by the `CreateFallbackBuffer` method of the [EncoderFallback](xref:System.Text.EncoderFallback) and [DecoderFallback](xref:System.Text.DecoderFallback) classes.</span></span> <span data-ttu-id="245bb-327">Die [EncoderFallback.CreateFallbackBuffer](xref:System.Text.EncoderFallback.CreateFallbackBuffer)-Methode wird vom Encoder aufgerufen, wenn das erste Zeichen erkannt wird, das nicht codiert werden kann. Die [DecoderFallback.CreateFallbackBuffer](xref:System.Text.DecoderFallback.CreateFallbackBuffer)-Methode wird vom Decoder aufgerufen, wenn ein oder mehrere Bytes erkannt werden, die nicht decodiert werden können.</span><span class="sxs-lookup"><span data-stu-id="245bb-327">The [EncoderFallback.CreateFallbackBuffer](xref:System.Text.EncoderFallback.CreateFallbackBuffer) method is called by the encoder when it encounters the first character that it is not able to encode, and the [DecoderFallback.CreateFallbackBuffer](xref:System.Text.DecoderFallback.CreateFallbackBuffer) method is called by the decoder when it encounters one or more bytes that it is not able to decode.</span></span> <span data-ttu-id="245bb-328">Die [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer)- und [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer)-Klasse stellen die Fallbackimplementierung bereit.</span><span class="sxs-lookup"><span data-stu-id="245bb-328">The [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) and [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) classes provide the fallback implementation.</span></span> <span data-ttu-id="245bb-329">Jede Instanz stellt einen Puffer dar, der die Fallbackzeichen enthält, die das Zeichen ersetzen, das nicht codiert werden kann, bzw. die die Bytesequenz ersetzen, die nicht decodiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="245bb-329">Each instance represents a buffer that contains the fallback characters that will replace the character that cannot be encoded or the byte sequence that cannot be decoded.</span></span>

<span data-ttu-id="245bb-330">Beim Erstellen einer benutzerdefinierten Fallbacklösung für einen Encoder oder einen Decoder müssen Sie die folgenden Member implementieren:</span><span class="sxs-lookup"><span data-stu-id="245bb-330">When you create a custom fallback solution for an encoder or decoder, you must implement the following members:</span></span>

* <span data-ttu-id="245bb-331">Die [EncoderFallbackBuffer.Fallback](xref:System.Text.EncoderFallbackBuffer.%23ctor)- oder [DecoderFallbackBuffer.Fallback](xref:System.Text.DecoderFallbackBuffer.Fallback(System.Byte[],System.Int32))-Methode.</span><span class="sxs-lookup"><span data-stu-id="245bb-331">The [EncoderFallbackBuffer.Fallback](xref:System.Text.EncoderFallbackBuffer.%23ctor) or [DecoderFallbackBuffer.Fallback](xref:System.Text.DecoderFallbackBuffer.Fallback(System.Byte[],System.Int32)) method.</span></span> <span data-ttu-id="245bb-332">[EncoderFallbackBuffer.Fallback](xref:System.Text.EncoderFallbackBuffer.Fallback(System.Char,System.Char,System.Int32)) wird vom Encoder aufgerufen, um dem Fallbackpuffer Informationen über das Zeichen bereitzustellen, das nicht codiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="245bb-332">[EncoderFallbackBuffer.Fallback](xref:System.Text.EncoderFallbackBuffer.Fallback(System.Char,System.Char,System.Int32)) is called by the encoder to provide the fallback buffer with information about the character that it cannot encode.</span></span> <span data-ttu-id="245bb-333">Da das zu codierende Zeichen möglicherweise ein Ersatzzeichenpaar ist, wird diese Methode überladen.</span><span class="sxs-lookup"><span data-stu-id="245bb-333">Because the character to be encoded may be a surrogate pair, this method is overloaded.</span></span> <span data-ttu-id="245bb-334">Einer Überladung werden das zu codierende Zeichen und der zugehörige Index in der Zeichenfolge übergeben.</span><span class="sxs-lookup"><span data-stu-id="245bb-334">One overload is passed the character to be encoded and its index in the string.</span></span> <span data-ttu-id="245bb-335">Der zweiten Überladung werden das hohe und das niedrige Ersatzzeichen zusammen mit dem Index in der Zeichenfolge übergeben.</span><span class="sxs-lookup"><span data-stu-id="245bb-335">The second overload is passed the high and low surrogate along with its index in the string.</span></span> <span data-ttu-id="245bb-336">Die [DecoderFallbackBuffer.Fallback](xref:System.Text.DecoderFallbackBuffer.Fallback(System.Byte[],System.Int32))-Methode wird vom Decoder aufgerufen, um dem Fallbackpuffer Informationen über die Bytes bereitzustellen, die nicht codiert werden können.</span><span class="sxs-lookup"><span data-stu-id="245bb-336">The [DecoderFallbackBuffer.Fallback](xref:System.Text.DecoderFallbackBuffer.Fallback(System.Byte[],System.Int32)) method is called by the decoder to provide the fallback buffer with information about the bytes that it cannot decode.</span></span> <span data-ttu-id="245bb-337">Dieser Methode wird zusammen mit dem Index des ersten Bytes ein Bytearray übergeben, das nicht decodiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="245bb-337">This method is passed an array of bytes that it cannot decode, along with the index of the first byte.</span></span> <span data-ttu-id="245bb-338">Die Fallbackmethode sollte `true` zurückgeben, wenn der Fallbackpuffer ein ähnliches Zeichen oder ein bzw. mehrere Ersatzzeichen bereitstellen kann. Andernfalls sollte sie `false` zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="245bb-338">The fallback method should return `true` if the fallback buffer can supply a best-fit or replacement character or characters; otherwise, it should return `false`.</span></span> <span data-ttu-id="245bb-339">Bei einem Ausnahmefallback sollte die Fallbackmethode eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="245bb-339">For an exception fallback, the fallback method should throw an exception.</span></span>

* <span data-ttu-id="245bb-340">Die [EncoderFallbackBuffer.GetNextChar](xref:System.Text.EncoderFallbackBuffer.GetNextChar)- oder [DecoderFallbackBuffer.GetNextChar](xref:System.Text.DecoderFallbackBuffer.GetNextChar)-Methode, die wiederholt vom Encoder oder Decoder aufgerufen wird, um das nächste Zeichen aus dem Fallbackpuffer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="245bb-340">The [EncoderFallbackBuffer.GetNextChar](xref:System.Text.EncoderFallbackBuffer.GetNextChar) or [DecoderFallbackBuffer.GetNextChar](xref:System.Text.DecoderFallbackBuffer.GetNextChar) method, which is called repeatedly by the encoder or decoder to get the next character from the fallback buffer.</span></span> <span data-ttu-id="245bb-341">Wenn alle Fallbackzeichen zurückgegeben wurden, sollte die Methode U+0000 zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="245bb-341">When all fallback characters have been returned, the method should return U+0000.</span></span> 

* <span data-ttu-id="245bb-342">Die [EncoderFallbackBuffer.Remaining](xref:System.Text.EncoderFallbackBuffer.Remaining)- oder [DecoderFallbackBuffer.Remaining](xref:System.Text.DecoderFallbackBuffer.Remaining)-Eigenschaft, die die Anzahl der im Fallbackpuffer verbleibenden Zeichen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="245bb-342">The [EncoderFallbackBuffer.Remaining](xref:System.Text.EncoderFallbackBuffer.Remaining) or [DecoderFallbackBuffer.Remaining](xref:System.Text.DecoderFallbackBuffer.Remaining) property, which returns the number of characters remaining in the fallback buffer.</span></span>

* <span data-ttu-id="245bb-343">Die [EncoderFallbackBuffer.MovePrevious](xref:System.Text.EncoderFallbackBuffer.MovePrevious) oder [DecoderFallbackBuffer.MovePrevious](xref:System.Text.DecoderFallbackBuffer.MovePrevious)-Methode, die die aktuelle Position im Fallbackpuffer zum vorhergehenden Zeichen verschiebt.</span><span class="sxs-lookup"><span data-stu-id="245bb-343">The [EncoderFallbackBuffer.MovePrevious](xref:System.Text.EncoderFallbackBuffer.MovePrevious) or [DecoderFallbackBuffer.MovePrevious](xref:System.Text.DecoderFallbackBuffer.MovePrevious) method, which moves the current position in the fallback buffer to the previous character.</span></span>

* <span data-ttu-id="245bb-344">Die [EncoderFallbackBuffer.Reset](xref:System.Text.EncoderFallbackBuffer.Reset)- oder [DecoderFallbackBuffer.Reset](xref:System.Text.DecoderFallbackBuffer.Reset)-Methode, die den Fallbackpuffer erneut initialisiert.</span><span class="sxs-lookup"><span data-stu-id="245bb-344">The [EncoderFallbackBuffer.Reset](xref:System.Text.EncoderFallbackBuffer.Reset) or [DecoderFallbackBuffer.Reset](xref:System.Text.DecoderFallbackBuffer.Reset) method, which reinitializes the fallback buffer.</span></span>

<span data-ttu-id="245bb-345">Wenn es sich bei der Fallbackimplementierung um einen Fallback mit ähnlichen Zeichen oder einen Ersatzfallback handelt, enthalten die von [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) und [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) abgeleiteten Klassen außerdem zwei private Instanzfelder: die genaue Anzahl von Zeichen im Puffer und den Index des nächsten Zeichens im Puffer, das zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="245bb-345">If the fallback implementation is a best-fit fallback or a replacement fallback, the classes derived from [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) and [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) also maintain two private instance fields: the exact number of characters in the buffer; and the index of the next character in the buffer to return.</span></span>

### <a name="an-encoderfallback-example"></a><span data-ttu-id="245bb-346">Ein EncoderFallback-Beispiel</span><span class="sxs-lookup"><span data-stu-id="245bb-346">An EncoderFallback example</span></span>

<span data-ttu-id="245bb-347">In einem früheren Beispiel wurde ein Ersatzfallback verwendet, um Unicode-Zeichen, die keinen ASCII-Zeichen entsprachen, durch ein Sternchen (\*) zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="245bb-347">An earlier example used replacement fallback to replace Unicode characters that did not correspond to ASCII characters with an asterisk (\*).</span></span> <span data-ttu-id="245bb-348">Im folgenden Beispiel wird stattdessen eine benutzerdefinierte Implementierung mit ähnlichen Zeichen verwendet, um eine bessere Zuordnung von Nicht-ASCII-Zeichen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="245bb-348">The following example uses a custom best-fit fallback implementation instead to provide a better mapping of non-ASCII characters.</span></span>

<span data-ttu-id="245bb-349">Der folgende Code definiert eine von [EncoderFallback](xref:System.Text.EncoderFallback) abgeleitete Klasse mit dem Namen `CustomMapper`, um die Zuordnung mit ähnlichen Zeichen für Nicht-ASCII-Zeichen zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="245bb-349">The following code defines a class named `CustomMapper` that is derived from [EncoderFallback](xref:System.Text.EncoderFallback) to handle the best-fit mapping of non-ASCII characters.</span></span> <span data-ttu-id="245bb-350">Die `CreateFallbackBuffer`-Methode gibt ein `CustomMapperFallbackBuffer`-Objekt zurück, das die [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer)-Implementierung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="245bb-350">Its `CreateFallbackBuffer` method returns a `CustomMapperFallbackBuffer` object, which provides the [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) implementation.</span></span> <span data-ttu-id="245bb-351">Die `CustomMapper`-Klasse verwendet ein [Dictionary&lt;TKey, TValue&gt;](xref:System.Collections.Generic.Dictionary%602)-Objekt, um die Zuordnungen von nicht unterstützten Unicode-Zeichen (Schlüsselwert) und den entsprechenden 8-Bit-Zeichen (die in zwei aufeinander folgenden Bytes in einer 64-Bit-Ganzzahl gespeichert sind) zu speichern.</span><span class="sxs-lookup"><span data-stu-id="245bb-351">The `CustomMapper` class uses a [Dictionary&lt;TKey, TValue&gt;](xref:System.Collections.Generic.Dictionary%602) object to store the mappings of unsupported Unicode characters (the key value) and their corresponding 8-bit characters (which are stored in two consecutive bytes in a 64-bit integer).</span></span> <span data-ttu-id="245bb-352">Um dem Fallbackpuffer diese Zuordnung zur Verfügung zu stellen, wird die `CustomMapper`-Instanz als Parameter an den `CustomMapperFallbackBuffer`-Klassenkonstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="245bb-352">To make this mapping available to the fallback buffer, the `CustomMapper` instance is passed as a parameter to the `CustomMapperFallbackBuffer` class constructor.</span></span> <span data-ttu-id="245bb-353">Da die längste Zuordnung die Zeichenfolge "INF" für das Unicode-Zeichen U+221E ist, gibt die `MaxCharCount`-Eigenschaft 3 zurück.</span><span class="sxs-lookup"><span data-stu-id="245bb-353">Because the longest mapping is the string "INF" for the Unicode character U+221E, the `MaxCharCount` property returns 3.</span></span> 

```csharp
public class CustomMapper : EncoderFallback
{
   public string DefaultString;
   internal Dictionary<ushort, ulong> mapping;

   public CustomMapper() : this("*")
   {   
   }

   public CustomMapper(string defaultString)
   {
      this.DefaultString = defaultString;

      // Create table of mappings
      mapping = new Dictionary<ushort, ulong>();
      mapping.Add(0x24C8, 0x53);
      mapping.Add(0x2075, 0x35);
      mapping.Add(0x221E, 0x49004E0046);
   }

   public override EncoderFallbackBuffer CreateFallbackBuffer()
   {
      return new CustomMapperFallbackBuffer(this);
   }

   public override int MaxCharCount
   {
      get { return 3; }
   } 
}
```

```vb
Public Class CustomMapper : Inherits EncoderFallback
   Public DefaultString As String
   Friend mapping As Dictionary(Of UShort, ULong)

   Public Sub New()
      Me.New("?")
   End Sub

   Public Sub New(ByVal defaultString As String)
      Me.DefaultString = defaultString

      ' Create table of mappings
      mapping = New Dictionary(Of UShort, ULong)
      mapping.Add(&H24C8, &H53)
      mapping.Add(&H2075, &H35)
      mapping.Add(&H221E, &H49004E0046)
   End Sub

   Public Overrides Function CreateFallbackBuffer() As System.Text.EncoderFallbackBuffer
      Return New CustomMapperFallbackBuffer(Me)
   End Function

   Public Overrides ReadOnly Property MaxCharCount As Integer
      Get
         Return 3
      End Get
   End Property
End Class
```

<span data-ttu-id="245bb-354">Der folgende Code definiert die `CustomMapperFallbackBuffer`-Klasse, die von [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="245bb-354">The following code defines the `CustomMapperFallbackBuffer` class, which is derived from [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer).</span></span> <span data-ttu-id="245bb-355">Das Wörterbuch, das die Zuordnung mit ähnlichen Zeichen enthält und in der `CustomMapper`-Instanz definiert ist, ist über den Klassenkonstruktor verfügbar.</span><span class="sxs-lookup"><span data-stu-id="245bb-355">The dictionary that contains best-fit mappings and that is defined in the `CustomMapper` instance is available from its class constructor.</span></span> <span data-ttu-id="245bb-356">Die `Fallback`-Methode gibt `true` zurück, wenn eines der Unicode-Zeichen, das der ASCII-Encoder nicht codieren kann, im Zuordnungswörterbuch definiert ist. Andernfalls wird `false` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="245bb-356">Its `Fallback` method returns `true` if any of the Unicode characters that the ASCII encoder cannot encode are defined in the mapping dictionary; otherwise, it returns `false`.</span></span> <span data-ttu-id="245bb-357">Bei jedem Fallback gibt die private `count`-Variable die Anzahl von Zeichen an, die noch zurückgegeben werden. Die private `index`-Variable gibt die Position im Zeichenfolgenpuffer (`charsToReturn`) des nächsten zurückzugebenden Zeichens an.</span><span class="sxs-lookup"><span data-stu-id="245bb-357">For each fallback, the private `count` variable indicates the number of characters that remain to be returned, and the private `index` variable indicates the position in the string buffer, `charsToReturn`, of the next character to return.</span></span> 

```csharp
public class CustomMapperFallbackBuffer : EncoderFallbackBuffer
{
   int count = -1;                   // Number of characters to return
   int index = -1;                   // Index of character to return
   CustomMapper fb; 
   string charsToReturn; 

   public CustomMapperFallbackBuffer(CustomMapper fallback)
   {
      this.fb = fallback;
   }

   public override bool Fallback(char charUnknownHigh, char charUnknownLow, int index)
   {
      // Do not try to map surrogates to ASCII.
      return false;
   }

   public override bool Fallback(char charUnknown, int index)
   {
      // Return false if there are already characters to map.
      if (count >= 1) return false;

      // Determine number of characters to return.
      charsToReturn = String.Empty;

      ushort key = Convert.ToUInt16(charUnknown);
      if (fb.mapping.ContainsKey(key)) {
         byte[] bytes = BitConverter.GetBytes(fb.mapping[key]);
         int ctr = 0;
         foreach (var byt in bytes) {
            if (byt > 0) {
               ctr++;
               charsToReturn += (char) byt;
            }
         }
         count = ctr;
      }
      else {
         // Return default.
         charsToReturn = fb.DefaultString;
         count = 1;
      }
      this.index = charsToReturn.Length - 1;

      return true;
   }

   public override char GetNextChar()
   {
      // We'll return a character if possible, so subtract from the count of chars to return.
      count--;
      // If count is less than zero, we've returned all characters.
      if (count < 0) 
         return '\u0000';

      this.index--;
      return charsToReturn[this.index + 1];
   }

   public override bool MovePrevious()
   {
      // Original: if count >= -1 and pos >= 0
      if (count >= -1) {
         count++;
         return true;
      }
      else {
         return false;
      }
   }

   public override int Remaining 
   {
      get { return count < 0 ? 0 : count; }
   }

   public override void Reset()
   {
      count = -1;
      index = -1;
   }
}
```

```vb
Public Class CustomMapperFallbackBuffer : Inherits EncoderFallbackBuffer

   Dim count As Integer = -1        ' Number of characters to return
   Dim index As Integer = -1        ' Index of character to return
   Dim fb As CustomMapper
   Dim charsToReturn As String

   Public Sub New(ByVal fallback As CustomMapper)
      MyBase.New()
      Me.fb = fallback
   End Sub

   Public Overloads Overrides Function Fallback(ByVal charUnknownHigh As Char, ByVal charUnknownLow As Char, ByVal index As Integer) As Boolean
      ' Do not try to map surrogates to ASCII.
      Return False
   End Function

   Public Overloads Overrides Function Fallback(ByVal charUnknown As Char, ByVal index As Integer) As Boolean
      ' Return false if there are already characters to map.
      If count >= 1 Then Return False

      ' Determine number of characters to return.
      charsToReturn = String.Empty

      Dim key As UShort = Convert.ToUInt16(charUnknown)
      If fb.mapping.ContainsKey(key) Then
         Dim bytes() As Byte = BitConverter.GetBytes(fb.mapping.Item(key))
         Dim ctr As Integer
         For Each byt In bytes
            If byt > 0 Then
               ctr += 1
               charsToReturn += Chr(byt)
            End If
         Next
         count = ctr
      Else
         ' Return default.
         charsToReturn = fb.DefaultString
         count = 1
      End If
      Me.index = charsToReturn.Length - 1

      Return True
   End Function

   Public Overrides Function GetNextChar() As Char
      ' We'll return a character if possible, so subtract from the count of chars to return.
      count -= 1
      ' If count is less than zero, we've returned all characters.
      If count < 0 Then Return ChrW(0)

      Me.index -= 1
      Return charsToReturn(Me.index + 1)
   End Function

   Public Overrides Function MovePrevious() As Boolean
      ' Original: if count >= -1 and pos >= 0
      If count >= -1 Then
         count += 1
         Return True
      Else
         Return False
      End If
   End Function

   Public Overrides ReadOnly Property Remaining As Integer
      Get
         Return If(count < 0, 0, count)
      End Get
   End Property

   Public Overrides Sub Reset()
      count = -1
      index = -1
   End Sub
End Class
```

<span data-ttu-id="245bb-358">Dann instanziiert der folgende Code das `CustomMapper`-Objekt und übergibt eine Instanz davon an die [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback))-Methode.</span><span class="sxs-lookup"><span data-stu-id="245bb-358">The following code then instantiates the `CustomMapper` object and passes an instance of it to the [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)) method.</span></span> <span data-ttu-id="245bb-359">Die Ausgabe zeigt, dass die Fallbackimplementierung mit ähnlichen Zeichen die drei Nicht-ASCII-Zeichen in der ursprünglichen Zeichenfolge erfolgreich behandelt.</span><span class="sxs-lookup"><span data-stu-id="245bb-359">The output indicates that the best-fit fallback implementation successfully handles the three non-ASCII characters in the original string.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Text;

class Program
{
   static void Main()
   {
      Encoding enc = Encoding.GetEncoding("us-ascii", new CustomMapper(), new DecoderExceptionFallback());

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      for (int ctr = 0; ctr <= str1.Length - 1; ctr++) {
         Console.Write("{0} ", Convert.ToUInt16(str1[ctr]).ToString("X4"));
         if (ctr == str1.Length - 1) 
            Console.WriteLine();
      }
      Console.WriteLine();

      // Encode the original string using the ASCII encoder.
      byte[] bytes = enc.GetBytes(str1);
      Console.Write("Encoded bytes: ");
      foreach (var byt in bytes)
         Console.Write("{0:X2} ", byt);

      Console.WriteLine("\n");

      // Decode the ASCII bytes.
      string str2 = enc.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      }
   }
}
```

```vb
Imports System.Text
Imports System.Collections.Generic

Module Module1

   Sub Main()
      Dim enc As Encoding = Encoding.GetEncoding("us-ascii", New CustomMapper(), New DecoderExceptionFallback())

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&H24C8), ChrW(&H2075), ChrW(&H221E))
      Console.WriteLine(str1)
      For ctr As Integer = 0 To str1.Length - 1
         Console.Write("{0} ", Convert.ToUInt16(str1(ctr)).ToString("X4"))
         If ctr = str1.Length - 1 Then Console.WriteLine()
      Next
      Console.WriteLine()

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = enc.GetBytes(str1)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Dim str2 As String = enc.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()
      End If
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="245bb-360">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="245bb-360">See also</span></span>

[<span data-ttu-id="245bb-361">System.Text.Encoder</span><span class="sxs-lookup"><span data-stu-id="245bb-361">System.Text.Encoder</span></span>](xref:System.Text.Encoder)

[<span data-ttu-id="245bb-362">System.Text.EncoderFallback</span><span class="sxs-lookup"><span data-stu-id="245bb-362">System.Text.EncoderFallback</span></span>](xref:System.Text.EncoderFallback)

[<span data-ttu-id="245bb-363">System.Text.Decoder</span><span class="sxs-lookup"><span data-stu-id="245bb-363">System.Text.Decoder</span></span>](xref:System.Text.Decoder)

[<span data-ttu-id="245bb-364">System.Text.DecoderFallback</span><span class="sxs-lookup"><span data-stu-id="245bb-364">System.Text.DecoderFallback</span></span>](xref:System.Text.DecoderFallback)

[<span data-ttu-id="245bb-365">System.Text.Encoding</span><span class="sxs-lookup"><span data-stu-id="245bb-365">System.Text.Encoding</span></span>](xref:System.Text.Encoding)





