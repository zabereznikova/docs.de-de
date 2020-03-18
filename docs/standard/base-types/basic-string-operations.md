---
title: Grundlegende Zeichenfolgenvorgänge in .NET
description: Erfahren Sie mehr über die grundlegenden Funktionen, die Sie für Zeichenfolgen verwenden können.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- strings [.NET Framework], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
ms.custom: seadec18
ms.openlocfilehash: 05cdf399e104fc9e528c954adb19634a5c136664
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73132911"
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="fdfa8-103">Grundlegende Zeichenfolgenvorgänge in .NET</span><span class="sxs-lookup"><span data-stu-id="fdfa8-103">Basic String Operations in .NET</span></span>
<span data-ttu-id="fdfa8-104">Anwendungen antworten Benutzern oft durch Erstellen von Nachrichten auf Grundlage der Benutzereingabe.</span><span class="sxs-lookup"><span data-stu-id="fdfa8-104">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="fdfa8-105">Beispielsweise ist es nicht ungewöhnlich, dass Websites neu angemeldeten Benutzern mit einer speziellen Begrüßung antworten, die den Namen des Benutzers enthält.</span><span class="sxs-lookup"><span data-stu-id="fdfa8-105">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="fdfa8-106">Mit einigen Methoden in den <xref:System.String?displayProperty=nameWithType>- und <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Klassen können Sie dynamisch benutzerdefinierte Zeichenfolgen für die Anzeige auf Ihrer Benutzeroberfläche erstellen.</span><span class="sxs-lookup"><span data-stu-id="fdfa8-106">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="fdfa8-107">Mit diesen Methoden können Sie auch eine Reihe grundlegender Zeichenfolgenoperationen wie das Erstellen neuer Zeichenfolgen aus Bytearrays, das Vergleichen der Werte von Zeichenfolgen und das Ändern vorhandener Zeichenfolgen durchführen.</span><span class="sxs-lookup"><span data-stu-id="fdfa8-107">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fdfa8-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fdfa8-108">In This Section</span></span>  
 [<span data-ttu-id="fdfa8-109">Erstellen neuer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="fdfa8-109">Creating New Strings</span></span>](../../../docs/standard/base-types/creating-new.md)  
 <span data-ttu-id="fdfa8-110">Beschreibt grundlegende Verfahren, um Objekte in Zeichenfolgen zu konvertieren und Zeichenfolgen zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="fdfa8-110">Describes basic ways to convert objects into strings and to combine strings.</span></span>  
  
 [<span data-ttu-id="fdfa8-111">Herausnehmen und Entfernen von Zeichen</span><span class="sxs-lookup"><span data-stu-id="fdfa8-111">Trimming and Removing Characters</span></span>](../../../docs/standard/base-types/trimming.md)  
 <span data-ttu-id="fdfa8-112">Beschreibt, wie Zeichen aus einer Zeichenfolge herausgenommen oder daraus entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="fdfa8-112">Describes how to trim or remove characters in a string.</span></span>  
  
 [<span data-ttu-id="fdfa8-113">Auffüllen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="fdfa8-113">Padding Strings</span></span>](../../../docs/standard/base-types/padding.md)  
 <span data-ttu-id="fdfa8-114">Beschreibt, wie Zeichen oder Leerzeichen in eine Zeichenfolge eingefügt werden</span><span class="sxs-lookup"><span data-stu-id="fdfa8-114">Describes how to insert characters or empty spaces into a string.</span></span>  
  
 [<span data-ttu-id="fdfa8-115">Vergleichen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="fdfa8-115">Comparing Strings</span></span>](../../../docs/standard/base-types/comparing.md)  
 <span data-ttu-id="fdfa8-116">Beschreibt, wie Sie den Inhalt von mindestens zwei Zeichenfolgen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="fdfa8-116">Describes how to compare the contents of two or more strings.</span></span>  
  
 [<span data-ttu-id="fdfa8-117">Ändern der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="fdfa8-117">Changing Case</span></span>](../../../docs/standard/base-types/changing-case.md)  
 <span data-ttu-id="fdfa8-118">Beschreibt, wie Sie die Groß-/Kleinschreibung von Zeichen in einer Zeichenfolge ändern.</span><span class="sxs-lookup"><span data-stu-id="fdfa8-118">Describes how to change the case of characters within a string.</span></span>  
  
 [<span data-ttu-id="fdfa8-119">Verwenden der StringBuilder-Klasse</span><span class="sxs-lookup"><span data-stu-id="fdfa8-119">Using the StringBuilder Class</span></span>](../../../docs/standard/base-types/stringbuilder.md)  
 <span data-ttu-id="fdfa8-120">Beschreibt das Erstellen und Ändern dynamischer Zeichenfolgenobjekte mithilfe der <xref:System.Text.StringBuilder>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="fdfa8-120">Describes how to create and modify dynamic string objects with the <xref:System.Text.StringBuilder> class.</span></span>  
  
 [<span data-ttu-id="fdfa8-121">Ausführen von grundlegenden Zeichenfolgenbearbeitungen</span><span class="sxs-lookup"><span data-stu-id="fdfa8-121">How to: Perform Basic String Manipulations</span></span>](../../../docs/standard/base-types/basic-manipulations.md)  
 <span data-ttu-id="fdfa8-122">Veranschaulicht die Verwendung von grundlegenden Zeichenfolgenvorgängen.</span><span class="sxs-lookup"><span data-stu-id="fdfa8-122">Demonstrates the use of basic string operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fdfa8-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="fdfa8-123">Related Sections</span></span>  
 [<span data-ttu-id="fdfa8-124">Typkonvertierung in .NET</span><span class="sxs-lookup"><span data-stu-id="fdfa8-124">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="fdfa8-125">Beschreibt, wie Sie einen Typ in einen anderen Typ konvertieren.</span><span class="sxs-lookup"><span data-stu-id="fdfa8-125">Describes how to convert one type into another type.</span></span>  
  
 [<span data-ttu-id="fdfa8-126">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="fdfa8-126">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="fdfa8-127">Beschreibt, wie Zeichenfolgen über Formatbezeichner formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="fdfa8-127">Describes how to format strings using format specifiers.</span></span>
