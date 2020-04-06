---
title: Analysieren von Zeichenfolgen in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: 717022e5d2e292c1624e6155bd7571e4daa997b9
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523800"
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="41373-102">Analysieren von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="41373-102">Parsing Strings in .NET</span></span>
<span data-ttu-id="41373-103">Bei einem Analysevorgang wird eine Zeichenfolge, die einen .NET-Basistyp darstellt, in diesen Basistyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="41373-103">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="41373-104">Beispielsweise wird ein Analysevorgang zum Konvertieren einer Zeichenfolge in eine Gleitkommazahl oder einen Wert für Datum und Uhrzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="41373-104">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="41373-105">Die beim Ausführen eines Analysevorgangs am häufigsten verwendete Methode ist die `Parse`-Methode.</span><span class="sxs-lookup"><span data-stu-id="41373-105">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="41373-106">Da die Analyse der umgekehrte Vorgang zur Formatierung (Konvertierung eines Basistyps in seine Zeichenfolgendarstellung) ist, gelten viele derselben Regeln und Konventionen.</span><span class="sxs-lookup"><span data-stu-id="41373-106">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="41373-107">Ebenso, wie bei der Formatierung ein Objekt verwendet wird, das die <xref:System.IFormatProvider>-Schnittstelle zur Bereitstellung kulturabhängiger Formatierungsinformationen implementiert, wird auch bei der Analyse ein Objekt verwendet, das die <xref:System.IFormatProvider>-Schnittstelle zur Interpretation einer Zeichenfolgendarstellung implementiert.</span><span class="sxs-lookup"><span data-stu-id="41373-107">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="41373-108">Weitere Informationen finden Sie unter [Formatieren von Typen in .NET](../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="41373-108">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="41373-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="41373-109">In This Section</span></span>  
 [<span data-ttu-id="41373-110">Verarbeiten numerischer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="41373-110">Parsing Numeric Strings</span></span>](../../../docs/standard/base-types/parsing-numeric.md)  
 <span data-ttu-id="41373-111">Beschreibt das Konvertieren von Zeichenfolgen in numerische .NET-Typen.</span><span class="sxs-lookup"><span data-stu-id="41373-111">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="41373-112">Verarbeiten von Zeichenfolgen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="41373-112">Parsing Date and Time Strings</span></span>](../../../docs/standard/base-types/parsing-datetime.md)  
 <span data-ttu-id="41373-113">Beschreibt das Konvertieren von Zeichenfolgen in **DateTime**-Typen in .NET.</span><span class="sxs-lookup"><span data-stu-id="41373-113">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="41373-114">Verarbeiten anderer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="41373-114">Parsing Other Strings</span></span>](../../../docs/standard/base-types/parsing-other.md)  
 <span data-ttu-id="41373-115">Beschreibt das Konvertieren von Zeichenfolgen in **Char**-, **Boolean**- und **Enum**-Typen.</span><span class="sxs-lookup"><span data-stu-id="41373-115">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="41373-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="41373-116">Related Sections</span></span>  
 [<span data-ttu-id="41373-117">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="41373-117">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="41373-118">Beschreibt grundlegende Formatierungsbegriffe wie „Formatbezeichner“ und „Formatanbieter“.</span><span class="sxs-lookup"><span data-stu-id="41373-118">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="41373-119">Typkonvertierung in .NET</span><span class="sxs-lookup"><span data-stu-id="41373-119">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="41373-120">Beschreibt, wie Typen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="41373-120">Describes how to convert types.</span></span>
