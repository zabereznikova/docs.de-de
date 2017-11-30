---
title: Analysieren von Zeichenfolgen in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 811db42e04e73d7acbc03e303297b19fdf643384
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="432d8-102">Analysieren von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="432d8-102">Parsing Strings in .NET</span></span>
<span data-ttu-id="432d8-103">Bei einem Analysevorgang wird eine Zeichenfolge, die einen .NET-Basistyp darstellt, in diesen Basistyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="432d8-103">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="432d8-104">Beispielsweise wird ein Analysevorgang zum Konvertieren einer Zeichenfolge in eine Gleitkommazahl oder einen Wert für Datum und Uhrzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="432d8-104">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="432d8-105">Die beim Ausführen eines Analysevorgangs am häufigsten verwendete Methode ist die `Parse`-Methode.</span><span class="sxs-lookup"><span data-stu-id="432d8-105">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="432d8-106">Da die Analyse der umgekehrte Vorgang zur Formatierung (Konvertierung eines Basistyps in seine Zeichenfolgendarstellung) ist, gelten viele derselben Regeln und Konventionen.</span><span class="sxs-lookup"><span data-stu-id="432d8-106">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="432d8-107">Formatieren wird ein Objekt, implementiert die <xref:System.IFormatProvider> Schnittstelle, um kulturabhängige Formatierungsinformationen zur Analyse auch verwendet, ein Objekt bereitstellen, implementiert die <xref:System.IFormatProvider> Schnittstelle, um zu bestimmen, wie die Darstellung einer Zeichenfolge zu interpretieren .</span><span class="sxs-lookup"><span data-stu-id="432d8-107">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="432d8-108">Weitere Informationen finden Sie unter [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="432d8-108">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="432d8-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="432d8-109">In This Section</span></span>  
 [<span data-ttu-id="432d8-110">Verarbeiten numerischer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="432d8-110">Parsing Numeric Strings</span></span>](../../../docs/standard/base-types/parsing-numeric.md)  
 <span data-ttu-id="432d8-111">Beschreibt das Konvertieren von Zeichenfolgen in .NET numerischen Typen.</span><span class="sxs-lookup"><span data-stu-id="432d8-111">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="432d8-112">Verarbeiten von Zeichenfolgen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="432d8-112">Parsing Date and Time Strings</span></span>](../../../docs/standard/base-types/parsing-datetime.md)  
 <span data-ttu-id="432d8-113">Beschreibt das Konvertieren von Zeichenfolgen in .NET **"DateTime"** Typen.</span><span class="sxs-lookup"><span data-stu-id="432d8-113">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="432d8-114">Verarbeiten anderer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="432d8-114">Parsing Other Strings</span></span>](../../../docs/standard/base-types/parsing-other.md)  
 <span data-ttu-id="432d8-115">Beschreibt das Konvertieren von Zeichenfolgen in **Char**, **booleschen**, und **Enum** Typen.</span><span class="sxs-lookup"><span data-stu-id="432d8-115">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="432d8-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="432d8-116">Related Sections</span></span>  
 [<span data-ttu-id="432d8-117">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="432d8-117">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="432d8-118">Beschreibt grundlegende Formatierung Konzepte wie Formatbezeichner und Formatanbieter.</span><span class="sxs-lookup"><span data-stu-id="432d8-118">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="432d8-119">Typkonvertierung in .NET</span><span class="sxs-lookup"><span data-stu-id="432d8-119">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="432d8-120">Beschreibt, wie Datentypen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="432d8-120">Describes how to convert types.</span></span>  
  
 [<span data-ttu-id="432d8-121">Basistypen</span><span class="sxs-lookup"><span data-stu-id="432d8-121">Base Types</span></span>](../../../docs/standard/base-types/index.md)  
 <span data-ttu-id="432d8-122">Beschreibt allgemeine Vorgänge, die für .NET-Basistypen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="432d8-122">Describes common operations that you can perform on .NET base types.</span></span>
