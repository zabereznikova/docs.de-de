---
title: Grundlegende Zeichenfolgenoperationen in .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strings [.NET Framework], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f241b99f97cad081a65fd8654169e444a1b588cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="a6389-102">Grundlegende Zeichenfolgenoperationen in .NET</span><span class="sxs-lookup"><span data-stu-id="a6389-102">Basic String Operations in .NET</span></span>
<span data-ttu-id="a6389-103">Anwendungen antworten Benutzern oft durch Erstellen von Nachrichten auf Grundlage der Benutzereingabe.</span><span class="sxs-lookup"><span data-stu-id="a6389-103">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="a6389-104">Beispielsweise ist es nicht ungewöhnlich, dass Websites neu angemeldeten Benutzern mit einer speziellen Begrüßung antworten, die den Namen des Benutzers enthält.</span><span class="sxs-lookup"><span data-stu-id="a6389-104">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="a6389-105">Einige Methoden in der <xref:System.String?displayProperty=nameWithType> und <xref:System.Text.StringBuilder?displayProperty=nameWithType> Klassen können Sie benutzerdefinierte Zeichenfolgen, die in der Benutzeroberfläche dynamisch zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a6389-105">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="a6389-106">Mit diesen Methoden können Sie auch eine Reihe grundlegender Zeichenfolgenoperationen wie das Erstellen neuer Zeichenfolgen aus Bytearrays, das Vergleichen der Werte von Zeichenfolgen und das Ändern vorhandener Zeichenfolgen durchführen.</span><span class="sxs-lookup"><span data-stu-id="a6389-106">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a6389-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a6389-107">In This Section</span></span>  
 [<span data-ttu-id="a6389-108">Erstellen neuer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="a6389-108">Creating New Strings</span></span>](../../../docs/standard/base-types/creating-new.md)  
 <span data-ttu-id="a6389-109">Beschreibt grundlegende Methoden, um Objekte in Zeichenfolgen konvertiert und Kombinieren von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="a6389-109">Describes basic ways to convert objects into strings and to combine strings.</span></span>  
  
 [<span data-ttu-id="a6389-110">Herausnehmen und Entfernen von Zeichen</span><span class="sxs-lookup"><span data-stu-id="a6389-110">Trimming and Removing Characters</span></span>](../../../docs/standard/base-types/trimming.md)  
 <span data-ttu-id="a6389-111">Beschreibt, wie zum Kürzen oder Entfernen von Zeichen in einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a6389-111">Describes how to trim or remove characters in a string.</span></span>  
  
 [<span data-ttu-id="a6389-112">Auffüllen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="a6389-112">Padding Strings</span></span>](../../../docs/standard/base-types/padding.md)  
 <span data-ttu-id="a6389-113">Beschreibt, wie Zeichen oder Leerzeichen in eine Zeichenfolge eingefügt werden</span><span class="sxs-lookup"><span data-stu-id="a6389-113">Describes how to insert characters or empty spaces into a string.</span></span>  
  
 [<span data-ttu-id="a6389-114">Vergleichen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="a6389-114">Comparing Strings</span></span>](../../../docs/standard/base-types/comparing.md)  
 <span data-ttu-id="a6389-115">Beschreibt, wie der Inhalt von zwei oder mehr Zeichenfolgen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="a6389-115">Describes how to compare the contents of two or more strings.</span></span>  
  
 [<span data-ttu-id="a6389-116">Ändern der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="a6389-116">Changing Case</span></span>](../../../docs/standard/base-types/changing-case.md)  
 <span data-ttu-id="a6389-117">Beschreibt, wie die Groß-/Kleinschreibung Zeichen innerhalb einer Zeichenfolge zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a6389-117">Describes how to change the case of characters within a string.</span></span>  
  
 [<span data-ttu-id="a6389-118">Verwenden der StringBuilder-Klasse</span><span class="sxs-lookup"><span data-stu-id="a6389-118">Using the StringBuilder Class</span></span>](../../../docs/standard/base-types/stringbuilder.md)  
 <span data-ttu-id="a6389-119">Beschreibt das Erstellen und ändern die dynamische Zeichenfolgenobjekten mit den <xref:System.Text.StringBuilder> Klasse.</span><span class="sxs-lookup"><span data-stu-id="a6389-119">Describes how to create and modify dynamic string objects with the <xref:System.Text.StringBuilder> class.</span></span>  
  
 [<span data-ttu-id="a6389-120">Ausführen von grundlegenden Zeichenfolgenbearbeitungen</span><span class="sxs-lookup"><span data-stu-id="a6389-120">How to: Perform Basic String Manipulations</span></span>](../../../docs/standard/base-types/basic-manipulations.md)  
 <span data-ttu-id="a6389-121">Veranschaulicht die Verwendung von grundlegender Zeichenfolgenoperationen.</span><span class="sxs-lookup"><span data-stu-id="a6389-121">Demonstrates the use of basic string operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a6389-122">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="a6389-122">Related Sections</span></span>  
 [<span data-ttu-id="a6389-123">Typkonvertierung in .NET</span><span class="sxs-lookup"><span data-stu-id="a6389-123">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="a6389-124">Beschreibt, wie ein Typ in einen anderen Typ umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="a6389-124">Describes how to convert one type into another type.</span></span>  
  
 [<span data-ttu-id="a6389-125">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="a6389-125">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="a6389-126">Beschreibt das Formatieren von Zeichenfolgen mithilfe von Formatbezeichnern.</span><span class="sxs-lookup"><span data-stu-id="a6389-126">Describes how to format strings using format specifiers.</span></span>
