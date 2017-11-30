---
title: Bearbeiten von Zeichenfolgen in .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strings [.NET Framework], manipulating
- manipulating strings
ms.assetid: d4568ff3-9f83-4549-acd8-47aec2194ac0
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f56dbd878012019f5cab68f2836286d9a6c2f548
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="manipulating-strings-in-net"></a><span data-ttu-id="44f03-102">Bearbeiten von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="44f03-102">Manipulating Strings in .NET</span></span>
<span data-ttu-id="44f03-103">.NET bietet einen umfangreichen Satz von Routinen, mit denen Sie Zeichenfolgen effizient erstellen, vergleichen und ändern sowie große Mengen von Text und Daten schnell analysieren können, um Textmuster zu suchen, zu entfernen und zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="44f03-103">.NET provides an extensive set of routines that enable you to efficiently create, compare, and modify strings as well as rapidly parse large amounts of text and data to search for, remove, and replace text patterns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44f03-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="44f03-104">In This Section</span></span>  
 [<span data-ttu-id="44f03-105">Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="44f03-105">Best Practices for Using Strings</span></span>](../../../docs/standard/base-types/best-practices-strings.md)  
 <span data-ttu-id="44f03-106">Sortieren von Zeichenfolge, Vergleichsoperatoren und Schreibweise Methoden in .NET untersucht und enthält Vorschläge zum Auswählen einer Methode für die Behandlung von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="44f03-106">Examines string-sorting, comparison, and casing methods in .NET, and provides recommendations for selecting a string-handling method .</span></span>  
  
 [<span data-ttu-id="44f03-107">Reguläre Ausdrücke von .NET</span><span class="sxs-lookup"><span data-stu-id="44f03-107">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="44f03-108">Enthält ausführliche Informationen zu regulären Ausdrücken von .NET, einschließlich Sprachelemente, Verhalten regulärer Ausdrücke und Beispielen.</span><span class="sxs-lookup"><span data-stu-id="44f03-108">Provides detailed information about .NET regular expressions, including language elements, regular expression behavior, and examples.</span></span>  
  
 [<span data-ttu-id="44f03-109">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="44f03-109">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)  
 <span data-ttu-id="44f03-110">Beschreibt gebotenen Zeichenfolgenoperationen stellen jedoch die <xref:System.String?displayProperty=nameWithType> und <xref:System.Text.StringBuilder?displayProperty=nameWithType> Klassen, einschließlich u. a. Vergleichen von Zeichenfolgenwerten, Erstellen neuer Zeichenfolgen aus Bytearrays und vorhandene Zeichenfolgen ändern.</span><span class="sxs-lookup"><span data-stu-id="44f03-110">Describes string operations provided by the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes, including creating new strings from arrays of bytes, comparing string values, and modifying existing strings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="44f03-111">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="44f03-111">Related Sections</span></span>  
 [<span data-ttu-id="44f03-112">Typkonvertierung in .NET</span><span class="sxs-lookup"><span data-stu-id="44f03-112">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="44f03-113">Erläutert die Verfahren und Regeln, die zum Konvertieren von Typen, die mit .NET.</span><span class="sxs-lookup"><span data-stu-id="44f03-113">Explains the techniques and rules used to convert types using .NET.</span></span>  
  
 [<span data-ttu-id="44f03-114">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="44f03-114">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="44f03-115">Bietet mit der Basisklassenbibliothek implementieren Formatierung, Formatieren von numerischen Typen, wie Zeichenfolgentypen formatiert und für eine bestimmte Kultur zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="44f03-115">Provides how to use the base class library to implement formatting, how to format numeric types, how to format string types, and how to format for a specific culture.</span></span>  
  
 [<span data-ttu-id="44f03-116">Analysieren von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="44f03-116">Parsing Strings</span></span>](../../../docs/standard/base-types/parsing-strings.md)  
 <span data-ttu-id="44f03-117">Beschreibt, wie Objekte mit den Werten initialisiert werden, die durch Zeichenfolgenentsprechungen dieser Objekte beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="44f03-117">Describes how to initialize objects to the values described by string representations of those objects.</span></span> <span data-ttu-id="44f03-118">Das Verarbeiten ist die Umkehroperation zum Formatieren.</span><span class="sxs-lookup"><span data-stu-id="44f03-118">Parsing is the inverse operation of formatting.</span></span>
