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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9c2193dd1b1f3c0478efb5fc9c2b80250ef1878f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="ca6f0-102">Analysieren von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="ca6f0-102">Parsing Strings in .NET</span></span>
<span data-ttu-id="ca6f0-103">Bei einem Analysevorgang wird eine Zeichenfolge, die einen .NET-Basistyp darstellt, in diesen Basistyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ca6f0-103">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="ca6f0-104">Beispielsweise wird ein Analysevorgang zum Konvertieren einer Zeichenfolge in eine Gleitkommazahl oder einen Wert für Datum und Uhrzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca6f0-104">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="ca6f0-105">Die beim Ausführen eines Analysevorgangs am häufigsten verwendete Methode ist die `Parse`-Methode.</span><span class="sxs-lookup"><span data-stu-id="ca6f0-105">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="ca6f0-106">Da die Analyse der umgekehrte Vorgang zur Formatierung (Konvertierung eines Basistyps in seine Zeichenfolgendarstellung) ist, gelten viele derselben Regeln und Konventionen.</span><span class="sxs-lookup"><span data-stu-id="ca6f0-106">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="ca6f0-107">Ebenso, wie bei der Formatierung ein Objekt verwendet wird, das die <xref:System.IFormatProvider>-Schnittstelle zur Bereitstellung kulturabhängiger Formatierungsinformationen implementiert, wird auch bei der Analyse ein Objekt verwendet, das die <xref:System.IFormatProvider>-Schnittstelle zur Interpretation einer Zeichenfolgendarstellung implementiert.</span><span class="sxs-lookup"><span data-stu-id="ca6f0-107">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="ca6f0-108">Weitere Informationen finden Sie unter [Formatieren von Typen in .NET](../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="ca6f0-108">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca6f0-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ca6f0-109">In This Section</span></span>  
 [<span data-ttu-id="ca6f0-110">Verarbeiten numerischer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ca6f0-110">Parsing Numeric Strings</span></span>](../../../docs/standard/base-types/parsing-numeric.md)  
 <span data-ttu-id="ca6f0-111">Beschreibt das Konvertieren von Zeichenfolgen in numerische .NET-Typen.</span><span class="sxs-lookup"><span data-stu-id="ca6f0-111">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="ca6f0-112">Verarbeiten von Zeichenfolgen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ca6f0-112">Parsing Date and Time Strings</span></span>](../../../docs/standard/base-types/parsing-datetime.md)  
 <span data-ttu-id="ca6f0-113">Beschreibt das Konvertieren von Zeichenfolgen in **DateTime**-Typen in .NET.</span><span class="sxs-lookup"><span data-stu-id="ca6f0-113">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="ca6f0-114">Verarbeiten anderer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ca6f0-114">Parsing Other Strings</span></span>](../../../docs/standard/base-types/parsing-other.md)  
 <span data-ttu-id="ca6f0-115">Beschreibt das Konvertieren von Zeichenfolgen in **Char**-, **Boolean**- und **Enum**-Typen.</span><span class="sxs-lookup"><span data-stu-id="ca6f0-115">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ca6f0-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ca6f0-116">Related Sections</span></span>  
 [<span data-ttu-id="ca6f0-117">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="ca6f0-117">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="ca6f0-118">Beschreibt grundlegende Formatierungsbegriffe wie „Formatbezeichner“ und „Formatanbieter“.</span><span class="sxs-lookup"><span data-stu-id="ca6f0-118">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="ca6f0-119">Typkonvertierung in .NET</span><span class="sxs-lookup"><span data-stu-id="ca6f0-119">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="ca6f0-120">Beschreibt, wie Typen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="ca6f0-120">Describes how to convert types.</span></span>  
  
 [<span data-ttu-id="ca6f0-121">Basistypen</span><span class="sxs-lookup"><span data-stu-id="ca6f0-121">Base Types</span></span>](../../../docs/standard/base-types/index.md)  
 <span data-ttu-id="ca6f0-122">Beschreibt allgemeine Vorgänge, die für .NET-Basistypen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="ca6f0-122">Describes common operations that you can perform on .NET base types.</span></span>
