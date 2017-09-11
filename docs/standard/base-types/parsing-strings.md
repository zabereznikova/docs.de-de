---
title: Analysieren von Zeichenfolgen in .NET
description: Analysieren von Zeichenfolgen in .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 8103c0a6-61d3-40dd-a3e9-2a32ba6a4c05
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: c741ae793d491f691a355df6ad064b81d609c7e5
ms.contentlocale: de-de
ms.lasthandoff: 03/03/2017

---

# <a name="parsing-strings-in-net"></a><span data-ttu-id="61d25-104">Analysieren von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="61d25-104">Parsing strings in .NET</span></span>

<span data-ttu-id="61d25-105">Bei einem Analysevorgang wird eine Zeichenfolge, die einen .NET-Basistyp darstellt, in diesen Basistyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="61d25-105">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="61d25-106">Beispielsweise wird ein Analysevorgang zum Konvertieren einer Zeichenfolge in eine Gleitkommazahl oder einen Wert für Datum und Uhrzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="61d25-106">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="61d25-107">Die beim Ausführen eines Analysevorgangs am häufigsten verwendete Methode ist die `Parse`-Methode.</span><span class="sxs-lookup"><span data-stu-id="61d25-107">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="61d25-108">Da die Analyse der umgekehrte Vorgang zur Formatierung (Konvertierung eines Basistyps in seine Zeichenfolgendarstellung) ist, gelten viele derselben Regeln und Konventionen.</span><span class="sxs-lookup"><span data-stu-id="61d25-108">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="61d25-109">Ebenso, wie bei der Formatierung ein Objekt verwendet wird, das die [IFormatProvider](xref:System.IFormatProvider)-Schnittstelle zur Bereitstellung kulturabhängiger Formatierungsinformationen implementiert, wird auch bei der Analyse ein Objekt verwendet, das die [IFormatProvider](xref:System.IFormatProvider)-Schnittstelle implementiert, um zu ermitteln, wie eine Zeichenfolgendarstellung zu interpretieren ist.</span><span class="sxs-lookup"><span data-stu-id="61d25-109">Just as formatting uses an object that implements the [IFormatProvider](xref:System.IFormatProvider) interface to provide culture-sensitive formatting information, parsing also uses an object that implements the [IFormatProvider](xref:System.IFormatProvider) interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="61d25-110">Weitere Informationen finden Sie unter [Formatieren von Typen in .NET](formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="61d25-110">For more information, see [Formatting Types in .NET](formatting-types.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="61d25-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="61d25-111">In This Section</span></span>

<span data-ttu-id="61d25-112">[Analysieren numerischer Zeichenfolgen in .NET](parsing-numeric.md): Beschreibt das Konvertieren von Zeichenfolgen in numerische .NET-Typen.</span><span class="sxs-lookup"><span data-stu-id="61d25-112">[Parsing Numeric Strings in .NET](parsing-numeric.md) - Describes how to convert strings into .NET numeric types.</span></span>

<span data-ttu-id="61d25-113">[Analysieren von Zeichenfolgen für Datum und Uhrzeit in .NET](parsing-datetime.md): Beschreibt das Konvertieren von Zeichenfolgen in .NET-`DateTime`-Typen.</span><span class="sxs-lookup"><span data-stu-id="61d25-113">[Parsing Date and Time Strings in .NET](parsing-datetime.md) - Describes how to convert strings into .NET `DateTime` types.</span></span>

<span data-ttu-id="61d25-114">[Analysieren anderer Zeichenfolgen in .NET](parsing-other.md): Beschreibt das Konvertieren von Zeichenfolgen in die Typen [Char](xref:System.Char), [Boolean](xref:System.Boolean) und [Enum](xref:System.Enum).</span><span class="sxs-lookup"><span data-stu-id="61d25-114">[Parsing Other Strings in .NET](parsing-other.md) - Describes how to convert strings into [Char](xref:System.Char), [Boolean](xref:System.Boolean), and [Enum](xref:System.Enum) types.</span></span>

<span data-ttu-id="61d25-115">[Formatieren von Typen in .NET](formatting-types.md): Beschreibt grundlegende Formatierungskonzepte wie Formatbezeichner und Formatanbieter.</span><span class="sxs-lookup"><span data-stu-id="61d25-115">[Formatting Types in .NET](formatting-types.md) - Describes basic formatting concepts like format specifiers and format providers.</span></span>

<span data-ttu-id="61d25-116">[Typkonvertierung in .NET](type-conversion.md): Beschreibt die Konvertierung von Typen.</span><span class="sxs-lookup"><span data-stu-id="61d25-116">[Type Conversion in .NET](type-conversion.md) - Describes how to convert types.</span></span>

<span data-ttu-id="61d25-117">[Arbeiten mit Basistypen in .NET](index.md): Beschreibt allgemeine Vorgänge, die für .NET-Basistypen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="61d25-117">[Working with Base Types in .NET](index.md) - Describes common operations that you can perform on .NET base types.</span></span>


