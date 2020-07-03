---
title: Analysieren von Zeichenfolgen in .NET
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
ms.openlocfilehash: 5e297c8f689fdabc268ee6e269a7969155befe7b
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769287"
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="7a061-105">Analysieren von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="7a061-105">Parsing Strings in .NET</span></span>
<span data-ttu-id="7a061-106">Bei einem Analysevorgang wird eine Zeichenfolge, die einen .NET-Basistyp darstellt, in diesen Basistyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7a061-106">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="7a061-107">Beispielsweise wird ein Analysevorgang zum Konvertieren einer Zeichenfolge in eine Gleitkommazahl oder einen Wert für Datum und Uhrzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="7a061-107">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="7a061-108">Die beim Ausführen eines Analysevorgangs am häufigsten verwendete Methode ist die `Parse`-Methode.</span><span class="sxs-lookup"><span data-stu-id="7a061-108">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="7a061-109">Da die Analyse der umgekehrte Vorgang zur Formatierung (Konvertierung eines Basistyps in seine Zeichenfolgendarstellung) ist, gelten viele derselben Regeln und Konventionen.</span><span class="sxs-lookup"><span data-stu-id="7a061-109">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="7a061-110">Ebenso, wie bei der Formatierung ein Objekt verwendet wird, das die <xref:System.IFormatProvider>-Schnittstelle zur Bereitstellung kulturabhängiger Formatierungsinformationen implementiert, wird auch bei der Analyse ein Objekt verwendet, das die <xref:System.IFormatProvider>-Schnittstelle zur Interpretation einer Zeichenfolgendarstellung implementiert.</span><span class="sxs-lookup"><span data-stu-id="7a061-110">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="7a061-111">Weitere Informationen finden Sie unter [Formatieren von Typen in .NET](formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="7a061-111">For more information, see [Formatting Types](formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a061-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7a061-112">In This Section</span></span>  
 [<span data-ttu-id="7a061-113">Verarbeiten numerischer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="7a061-113">Parsing Numeric Strings</span></span>](parsing-numeric.md)  
 <span data-ttu-id="7a061-114">Beschreibt das Konvertieren von Zeichenfolgen in numerische .NET-Typen.</span><span class="sxs-lookup"><span data-stu-id="7a061-114">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="7a061-115">Verarbeiten von Zeichenfolgen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="7a061-115">Parsing Date and Time Strings</span></span>](parsing-datetime.md)  
 <span data-ttu-id="7a061-116">Beschreibt das Konvertieren von Zeichenfolgen in **DateTime**-Typen in .NET.</span><span class="sxs-lookup"><span data-stu-id="7a061-116">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="7a061-117">Verarbeiten anderer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="7a061-117">Parsing Other Strings</span></span>](parsing-other.md)  
 <span data-ttu-id="7a061-118">Beschreibt das Konvertieren von Zeichenfolgen in **Char**-, **Boolean**- und **Enum**-Typen.</span><span class="sxs-lookup"><span data-stu-id="7a061-118">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7a061-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="7a061-119">Related Sections</span></span>  
 [<span data-ttu-id="7a061-120">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="7a061-120">Formatting Types</span></span>](formatting-types.md)  
 <span data-ttu-id="7a061-121">Beschreibt grundlegende Formatierungsbegriffe wie „Formatbezeichner“ und „Formatanbieter“.</span><span class="sxs-lookup"><span data-stu-id="7a061-121">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="7a061-122">Typkonvertierung in .NET</span><span class="sxs-lookup"><span data-stu-id="7a061-122">Type Conversion in .NET</span></span>](type-conversion.md)  
 <span data-ttu-id="7a061-123">Beschreibt, wie Typen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="7a061-123">Describes how to convert types.</span></span>
