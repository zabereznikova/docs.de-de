---
title: Konvertieren von Zeichenfolgen in Typen
description: Machen Sie sich mit dem Analysieren von Zeichenfolgen in .NET vertraut. Beim Analysieren wird eine Zeichenfolge, die einen .NET-Basistyp darstellt, in diesen Basistyp konvertiert. Das Analysieren ist der entgegengesetzte Vorgang zum Formatieren.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: 3d23fa9c7ecc3593f03f70dbd5ea7bda841e8f4f
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400852"
---
# <a name="parse-strings-in-net"></a><span data-ttu-id="8ab75-105">Analysieren von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="8ab75-105">Parse strings in .NET</span></span>

<span data-ttu-id="8ab75-106">Bei einem *Analysevorgang* wird eine Zeichenfolge, die einen .NET-Basistyp darstellt, in diesen Basistyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="8ab75-106">A *parsing* operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="8ab75-107">Beispielsweise wird ein Analysevorgang zum Konvertieren einer Zeichenfolge in eine Gleitkommazahl oder einen Wert für Datum und Uhrzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="8ab75-107">For example, a parsing operation is used to convert a string to a floating-point number or to a date-and-time value.</span></span> <span data-ttu-id="8ab75-108">Die beim Ausführen eines Analysevorgangs am häufigsten verwendete Methode ist die `Parse`-Methode.</span><span class="sxs-lookup"><span data-stu-id="8ab75-108">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="8ab75-109">Da die Analyse der umgekehrte Vorgang zur Formatierung (Konvertierung eines Basistyps in seine Zeichenfolgendarstellung) ist, gelten viele derselben Regeln und Konventionen.</span><span class="sxs-lookup"><span data-stu-id="8ab75-109">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="8ab75-110">Ebenso, wie bei der Formatierung ein Objekt verwendet wird, das die <xref:System.IFormatProvider>-Schnittstelle zur Bereitstellung kulturabhängiger Formatierungsinformationen implementiert, wird auch bei der Analyse ein Objekt verwendet, das die <xref:System.IFormatProvider>-Schnittstelle zur Interpretation einer Zeichenfolgendarstellung implementiert.</span><span class="sxs-lookup"><span data-stu-id="8ab75-110">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="8ab75-111">Weitere Informationen finden Sie unter [Formatieren von Typen](formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="8ab75-111">For more information, see [Format types](formatting-types.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8ab75-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8ab75-112">In This Section</span></span>
 <span data-ttu-id="8ab75-113">[Analysieren numerischer Zeichenfolgen](parsing-numeric.md)</span><span class="sxs-lookup"><span data-stu-id="8ab75-113">[Parsing Numeric Strings](parsing-numeric.md)</span></span>\
 <span data-ttu-id="8ab75-114">Beschreibt das Konvertieren von Zeichenfolgen in numerische .NET-Typen.</span><span class="sxs-lookup"><span data-stu-id="8ab75-114">Describes how to convert strings into .NET numeric types.</span></span>

 <span data-ttu-id="8ab75-115">[Analysieren von Zeichenfolgen für Datum und Uhrzeit](parsing-datetime.md)</span><span class="sxs-lookup"><span data-stu-id="8ab75-115">[Parsing Date and Time Strings](parsing-datetime.md)</span></span>\
 <span data-ttu-id="8ab75-116">Beschreibt das Konvertieren von Zeichenfolgen in **DateTime** -Typen in .NET.</span><span class="sxs-lookup"><span data-stu-id="8ab75-116">Describes how to convert strings into .NET **DateTime** types.</span></span>

 <span data-ttu-id="8ab75-117">[Analysieren anderer Zeichenfolgen](parsing-other.md)</span><span class="sxs-lookup"><span data-stu-id="8ab75-117">[Parsing Other Strings](parsing-other.md)</span></span>\
 <span data-ttu-id="8ab75-118">Beschreibt das Konvertieren von Zeichenfolgen in **Char** -, **Boolean** - und **Enum** -Typen.</span><span class="sxs-lookup"><span data-stu-id="8ab75-118">Describes how to convert strings into **Char** , **Boolean** , and **Enum** types.</span></span>

## <a name="related-sections"></a><span data-ttu-id="8ab75-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="8ab75-119">Related Sections</span></span>
 <span data-ttu-id="8ab75-120">[Formatierung von Typen](formatting-types.md)</span><span class="sxs-lookup"><span data-stu-id="8ab75-120">[Formatting Types](formatting-types.md)</span></span>\
 <span data-ttu-id="8ab75-121">Beschreibt grundlegende Formatierungsbegriffe wie „Formatbezeichner“ und „Formatanbieter“.</span><span class="sxs-lookup"><span data-stu-id="8ab75-121">Describes basic formatting concepts like format specifiers and format providers.</span></span>

 <span data-ttu-id="8ab75-122">[Typkonvertierung in .NET](type-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="8ab75-122">[Type Conversion in .NET](type-conversion.md)</span></span>\
 <span data-ttu-id="8ab75-123">Beschreibt, wie Typen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="8ab75-123">Describes how to convert types.</span></span>
