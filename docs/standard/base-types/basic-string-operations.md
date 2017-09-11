---
title: Grundlegende Zeichenfolgenoperationen
description: Grundlegende Zeichenfolgenoperationen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 9658098d-de60-4868-ba5b-0c278748a90f
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: b8bdbeccd226c412e725200fcaf81ec568afc5bc
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="basic-string-operations"></a><span data-ttu-id="3305b-104">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="3305b-104">Basic string operations</span></span>

<span data-ttu-id="3305b-105">Anwendungen antworten Benutzern oft durch Erstellen von Nachrichten auf Grundlage der Benutzereingabe.</span><span class="sxs-lookup"><span data-stu-id="3305b-105">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="3305b-106">Beispielsweise ist es nicht ungewöhnlich, dass Websites neu angemeldeten Benutzern mit einer speziellen Begrüßung antworten, die den Namen des Benutzers enthält.</span><span class="sxs-lookup"><span data-stu-id="3305b-106">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="3305b-107">Mit einigen Methoden in den [System.String](xref:System.String)- und [System.Text.StringBuilder](xref:System.Text.StringBuilder)-Klassen können Sie benutzerdefinierte Zeichenfolgen für die Anzeige in Ihrer Benutzeroberfläche dynamisch erstellen.</span><span class="sxs-lookup"><span data-stu-id="3305b-107">Several methods in the [System.String](xref:System.String) and [System.Text.StringBuilder](xref:System.Text.StringBuilder) classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="3305b-108">Mit diesen Methoden können Sie auch eine Reihe grundlegender Zeichenfolgenoperationen wie das Erstellen neuer Zeichenfolgen aus Bytearrays, das Vergleichen der Werte von Zeichenfolgen und das Ändern vorhandener Zeichenfolgen durchführen.</span><span class="sxs-lookup"><span data-stu-id="3305b-108">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3305b-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3305b-109">In This Section</span></span>

<span data-ttu-id="3305b-110">[Erstellen neuer Zeichenfolgen](creating-new.md): Beschreibt grundlegende Verfahren, um Objekte in Zeichenfolgen zu konvertieren und Zeichenfolgen zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="3305b-110">[Creating new strings](creating-new.md) - Describes basic ways to convert objects into strings and to combine strings.</span></span>

<span data-ttu-id="3305b-111">[Herausnehmen und Entfernen von Zeichen](trimming.md): Beschreibt, wie Zeichen aus einer Zeichenfolge herausgenommen oder daraus entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="3305b-111">[Trimming and removing characters](trimming.md) - Describes how to trim or remove characters in a string.</span></span> 

<span data-ttu-id="3305b-112">[Auffüllen von Zeichenfolgen](padding.md): Beschreibt, wie Zeichen oder Leerzeichen in eine Zeichenfolge eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="3305b-112">[Padding strings](padding.md) - Describes how to insert characters or empty spaces into a string.</span></span>

<span data-ttu-id="3305b-113">[Vergleichen von Zeichenfolgen](comparing.md): Beschreibt, wie Sie den Inhalt von zwei oder mehr Zeichenfolgen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="3305b-113">[Comparing strings](comparing.md) - Describes how to compare the contents of two or more strings.</span></span>

<span data-ttu-id="3305b-114">[Groß-/Kleinschreibung ändern](changing-case.md): Beschreibt, wie Sie die Groß-/Kleinschreibung von Zeichen in einer Zeichenfolge ändern.</span><span class="sxs-lookup"><span data-stu-id="3305b-114">[Changing case](changing-case.md) - Describes how to change the case of characters within a string.</span></span>

<span data-ttu-id="3305b-115">[Verwenden der StringBuilder-Klasse](stringbuilder.md): Beschreibt das Erstellen und Ändern dynamischer Zeichenfolgenobjekte mit der [StringBuilder](xref:System.Text.StringBuilder)-Klasse.</span><span class="sxs-lookup"><span data-stu-id="3305b-115">[Using the StringBuilder class](stringbuilder.md) - Describes how to create and modify dynamic string objects with the [StringBuilder](xref:System.Text.StringBuilder) class.</span></span>

<span data-ttu-id="3305b-116">[Ausführen von grundlegenden Zeichenfolgenbearbeitungen](basic-manipulations.md): Veranschaulicht die Verwendung grundlegender Zeichenfolgenoperationen.</span><span class="sxs-lookup"><span data-stu-id="3305b-116">[How to: Perform basic string manipulations](basic-manipulations.md) - Demonstrates the use of basic string operations.</span></span>

## <a name="related-sections"></a><span data-ttu-id="3305b-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="3305b-117">Related Sections</span></span>

<span data-ttu-id="3305b-118">[Typkonvertierung](type-conversion.md): Beschreibt, wie Sie einen Typ in einen anderen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="3305b-118">[Type conversion](type-conversion.md) - Describes how to convert from one type to another.</span></span>

<span data-ttu-id="3305b-119">[Formatieren von Typen](formatting-types.md): Beschreibt, wie Zeichenfolgen über die Zeichenfolgen-Formatbezeichner formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="3305b-119">[Formatting types](formatting-types.md) - Describes how to format strings using the string format specifiers.</span></span>



