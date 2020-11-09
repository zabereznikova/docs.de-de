---
title: Grundlegende Zeichenfolgenvorgänge in .NET
description: Erfahren Sie mehr über die grundlegenden Funktionen, die Sie für Zeichenfolgen verwenden können.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- strings [.NET], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
ms.custom: seadec18
ms.openlocfilehash: 4ab087435880c6a5357bc161899cd585982622f4
ms.sourcegitcommit: ffd4d5e824db6c5f0c3521c0e802fd9e8f0edcbe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "93342604"
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="12a3e-103">Grundlegende Zeichenfolgenvorgänge in .NET</span><span class="sxs-lookup"><span data-stu-id="12a3e-103">Basic string operations in .NET</span></span>

<span data-ttu-id="12a3e-104">Anwendungen antworten Benutzern oft durch Erstellen von Nachrichten auf Grundlage der Benutzereingabe.</span><span class="sxs-lookup"><span data-stu-id="12a3e-104">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="12a3e-105">Beispielsweise ist es nicht ungewöhnlich, dass Websites neu angemeldeten Benutzern mit einer speziellen Begrüßung antworten, die den Namen des Benutzers enthält.</span><span class="sxs-lookup"><span data-stu-id="12a3e-105">For example, it is not uncommon for websites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span>

<span data-ttu-id="12a3e-106">Mit einigen Methoden in den <xref:System.String?displayProperty=nameWithType>- und <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Klassen können Sie dynamisch benutzerdefinierte Zeichenfolgen für die Anzeige auf Ihrer Benutzeroberfläche erstellen.</span><span class="sxs-lookup"><span data-stu-id="12a3e-106">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="12a3e-107">Mit diesen Methoden können Sie auch eine Reihe grundlegender Zeichenfolgenoperationen wie das Erstellen neuer Zeichenfolgen aus Bytearrays, das Vergleichen der Werte von Zeichenfolgen und das Ändern vorhandener Zeichenfolgen durchführen.</span><span class="sxs-lookup"><span data-stu-id="12a3e-107">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>

## <a name="related-sections"></a><span data-ttu-id="12a3e-108">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="12a3e-108">Related sections</span></span>

<span data-ttu-id="12a3e-109">[Typkonvertierung in .NET](type-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="12a3e-109">[Type Conversion in .NET](type-conversion.md)</span></span>\
<span data-ttu-id="12a3e-110">Beschreibt, wie Sie einen Typ in einen anderen Typ konvertieren.</span><span class="sxs-lookup"><span data-stu-id="12a3e-110">Describes how to convert one type into another type.</span></span>

<span data-ttu-id="12a3e-111">[Formatierung von Typen](formatting-types.md)</span><span class="sxs-lookup"><span data-stu-id="12a3e-111">[Formatting Types](formatting-types.md)</span></span>\
<span data-ttu-id="12a3e-112">Beschreibt, wie Zeichenfolgen über Formatbezeichner formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="12a3e-112">Describes how to format strings using format specifiers.</span></span>
