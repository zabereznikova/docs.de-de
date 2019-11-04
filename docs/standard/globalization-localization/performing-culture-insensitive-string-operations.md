---
title: Durchführen kulturunabhängiger Zeichenfolgenoperationen
ms.date: 08/22/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
ms.openlocfilehash: 183078b1f7a3eb3530fea8af06dbb59055d7d25d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120799"
---
# <a name="performing-culture-insensitive-string-operations"></a>Durchführen kulturunabhängiger Zeichenfolgenoperationen
Die meisten .NET Framework-Methoden, die standardmäßig kulturabhängige Zeichenfolgenoperationen durchführen, stellen Methodenüberladungen bereit, für die Sie die zu verwendende Kultur explizit angeben können, indem Sie einen <xref:System.Globalization.CultureInfo>-Parameter übergeben. Diese Überladungen ermöglichen es Ihnen, kulturelle Variationen in Groß-/Kleinschreibungszuordnungen und Sortierregeln zu eliminieren und kulturunabhängige Ergebnisse zu gewährleisten.  
  
 Dieser Abschnitt enthält die folgenden Themen, in denen erläutert wird, wie kulturunabhängige Zeichenfolgenoperationen mit .NET Framework-Methoden durchgeführt werden, die standardmäßig kulturabhängig sind.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Durchführen kulturunabhängiger Zeichenfolgenvergleiche](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 Beschreibt die Verwendung der <xref:System.String.Compare%2A?displayProperty=nameWithType>- und <xref:System.String.CompareTo%2A?displayProperty=nameWithType>-Methode für kulturunabhängige Zeichenfolgenvergleiche.  
  
 [Durchführen kulturunabhängiger Schreibungsänderungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 Beschreibt die Verwendung der <xref:System.String.ToUpper%2A?displayProperty=nameWithType>-, <xref:System.String.ToLower%2A?displayProperty=nameWithType>-, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>- und <xref:System.Char.ToLower%2A?displayProperty=nameWithType>-Methode für kulturunabhängige Schreibungsänderungen.  
  
 [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Auflistungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 Beschreibt die Verwendung von <xref:System.Collections.CaseInsensitiveComparer>- und <xref:System.Collections.CaseInsensitiveHashCodeProvider>-Klasse, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> und <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> für kulturunabhängige Operationen in Sammlungen.  
  
 [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Arrays](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 Beschreibt die Verwendung von <xref:System.Array.Sort%2A?displayProperty=nameWithType>- und <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>-Methode für kulturunabhängige Operationen in Arrays.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Kulturunabhängige Zeichenfolgenoperationen](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 Beschreibt, warum Sie die Kultur berücksichtigen sollten, wenn Sie Operationen mit Zeichenfolgen ausführen, und enthält Richtlinien dazu, wann kulturabhängige Operationen und wann kulturunabhängige Operationen ausgeführt werden sollten.

## <a name="see-also"></a>Siehe auch

- [Sortiergewichtungstabellen (für .NET auf Windows-Systemen)](https://www.microsoft.com/download/details.aspx?id=10921)
- [Default Unicode Collation Element Table (für .NET Core unter Linux und macOS)](https://www.unicode.org/Public/UCA/latest/allkeys.txt)
