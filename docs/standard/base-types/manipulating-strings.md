---
title: Bearbeiten von Zeichenfolgen in .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- strings [.NET Framework], manipulating
- manipulating strings
ms.assetid: d4568ff3-9f83-4549-acd8-47aec2194ac0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca4e24cb882daf7efd14da83011d50d05a85232b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="manipulating-strings-in-net"></a><span data-ttu-id="c6d1d-102">Bearbeiten von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="c6d1d-102">Manipulating Strings in .NET</span></span>
<span data-ttu-id="c6d1d-103">.NET bietet einen umfangreichen Satz von Routinen, mit denen Sie Zeichenfolgen effizient erstellen, vergleichen und ändern sowie große Mengen von Text und Daten schnell analysieren können, um Textmuster zu suchen, zu entfernen und zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c6d1d-103">.NET provides an extensive set of routines that enable you to efficiently create, compare, and modify strings as well as rapidly parse large amounts of text and data to search for, remove, and replace text patterns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6d1d-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c6d1d-104">In This Section</span></span>  
 [<span data-ttu-id="c6d1d-105">Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="c6d1d-105">Best Practices for Using Strings</span></span>](../../../docs/standard/base-types/best-practices-strings.md)  
 <span data-ttu-id="c6d1d-106">Untersucht die Methoden für die Sortierung, den Vergleich und die Schreibweise in .NET und stellt Empfehlungen für das Auswählen einer Methode zur Zeichenfolgenverarbeitung bereit.</span><span class="sxs-lookup"><span data-stu-id="c6d1d-106">Examines string-sorting, comparison, and casing methods in .NET, and provides recommendations for selecting a string-handling method .</span></span>  
  
 [<span data-ttu-id="c6d1d-107">Reguläre Ausdrücke von .NET</span><span class="sxs-lookup"><span data-stu-id="c6d1d-107">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="c6d1d-108">Enthält ausführliche Informationen zu regulären .NET-Ausdrücken, einschließlich Sprachelementen, Verhalten von regulären Ausdrücken und Beispielen.</span><span class="sxs-lookup"><span data-stu-id="c6d1d-108">Provides detailed information about .NET regular expressions, including language elements, regular expression behavior, and examples.</span></span>  
  
 [<span data-ttu-id="c6d1d-109">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="c6d1d-109">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)  
 <span data-ttu-id="c6d1d-110">Beschreibt Zeichenfolgenvorgänge, die von den Klassen <xref:System.String?displayProperty=nameWithType> und <xref:System.Text.StringBuilder?displayProperty=nameWithType> bereitgestellt werden, einschließlich der Erstellung neuer Zeichenfolgen aus Bytearrays, des Vergleichs von Zeichenfolgenwerten und der Änderung vorhandener Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="c6d1d-110">Describes string operations provided by the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes, including creating new strings from arrays of bytes, comparing string values, and modifying existing strings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c6d1d-111">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="c6d1d-111">Related Sections</span></span>  
 [<span data-ttu-id="c6d1d-112">Typkonvertierung in .NET</span><span class="sxs-lookup"><span data-stu-id="c6d1d-112">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="c6d1d-113">Erläutert die Verfahren und Regeln, die zum Konvertieren von Typen mit .NET verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6d1d-113">Explains the techniques and rules used to convert types using .NET.</span></span>  
  
 [<span data-ttu-id="c6d1d-114">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="c6d1d-114">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="c6d1d-115">Bietet Informationen darüber, wie mittels der Basisklassenbibliothek Formatierungen implementiert, numerische Typen formatiert, Zeichenfolgentypen formatiert und Formatierungen für eine bestimmte Kultur vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="c6d1d-115">Provides how to use the base class library to implement formatting, how to format numeric types, how to format string types, and how to format for a specific culture.</span></span>  
  
 [<span data-ttu-id="c6d1d-116">Parsing Strings</span><span class="sxs-lookup"><span data-stu-id="c6d1d-116">Parsing Strings</span></span>](../../../docs/standard/base-types/parsing-strings.md)  
 <span data-ttu-id="c6d1d-117">Beschreibt, wie Objekte mit den Werten initialisiert werden, die durch Zeichenfolgenentsprechungen dieser Objekte beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c6d1d-117">Describes how to initialize objects to the values described by string representations of those objects.</span></span> <span data-ttu-id="c6d1d-118">Das Verarbeiten ist die Umkehroperation zum Formatieren.</span><span class="sxs-lookup"><span data-stu-id="c6d1d-118">Parsing is the inverse operation of formatting.</span></span>
