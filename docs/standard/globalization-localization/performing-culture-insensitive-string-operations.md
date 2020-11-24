---
title: Durchführen kulturunabhängiger Zeichenfolgenoperationen
ms.date: 08/22/2018
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
ms.openlocfilehash: 868f36a1025f0b121a8765edf50bb42679736240
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829764"
---
# <a name="performing-culture-insensitive-string-operations"></a>Durchführen kulturunabhängiger Zeichenfolgenoperationen

Die meisten .NET-Methoden, die standardmäßig kulturabhängige Zeichenfolgenoperationen durchführen, stellen Methodenüberladungen bereit, für die Sie die zu verwendende Kultur explizit angeben können, indem Sie einen <xref:System.Globalization.CultureInfo>-Parameter übergeben. Diese Überladungen ermöglichen es Ihnen, kulturelle Variationen in Groß-/Kleinschreibungszuordnungen und Sortierregeln zu eliminieren und kulturunabhängige Ergebnisse zu gewährleisten.  
  
 Dieser Abschnitt enthält die folgenden Artikel, in denen erläutert wird, wie kulturunabhängige Zeichenfolgenoperationen mit .NET-Methoden durchgeführt werden, die standardmäßig kulturabhängig sind.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Durchführen kulturunabhängiger Zeichenfolgenvergleiche](performing-culture-insensitive-string-comparisons.md)  
 Beschreibt die Verwendung der <xref:System.String.Compare%2A?displayProperty=nameWithType>- und <xref:System.String.CompareTo%2A?displayProperty=nameWithType>-Methode für kulturunabhängige Zeichenfolgenvergleiche.  
  
 [Durchführen kulturunabhängiger Schreibungsänderungen](performing-culture-insensitive-case-changes.md)  
 Beschreibt die Verwendung der <xref:System.String.ToUpper%2A?displayProperty=nameWithType>-, <xref:System.String.ToLower%2A?displayProperty=nameWithType>-, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>- und <xref:System.Char.ToLower%2A?displayProperty=nameWithType>-Methode für kulturunabhängige Schreibungsänderungen.  
  
 [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Auflistungen](performing-culture-insensitive-string-operations-in-collections.md)  
 Beschreibt die Verwendung von <xref:System.Collections.CaseInsensitiveComparer>- und <xref:System.Collections.CaseInsensitiveHashCodeProvider>-Klasse, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> und <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> für kulturunabhängige Operationen in Sammlungen.  
  
 [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Arrays](performing-culture-insensitive-string-operations-in-arrays.md)  
 Beschreibt die Verwendung von <xref:System.Array.Sort%2A?displayProperty=nameWithType>- und <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>-Methode für kulturunabhängige Operationen in Arrays.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Kulturunabhängige Zeichenfolgenoperationen](culture-insensitive-string-operations.md)  
 Beschreibt, warum Sie die Kultur berücksichtigen sollten, wenn Sie Operationen mit Zeichenfolgen ausführen, und enthält Richtlinien dazu, wann kulturabhängige Operationen und wann kulturunabhängige Operationen ausgeführt werden sollten.

## <a name="see-also"></a>Weitere Informationen

- [Sortiergewichtungstabellen (für .NET auf Windows-Systemen)](https://www.microsoft.com/download/details.aspx?id=10921)
- [Default Unicode Collation Element Table (für .NET Core unter Linux und macOS)](https://www.unicode.org/Public/UCA/latest/allkeys.txt)
