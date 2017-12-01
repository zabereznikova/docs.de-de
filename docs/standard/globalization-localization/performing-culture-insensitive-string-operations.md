---
title: "Durchführen kulturunabhängiger Zeichenfolgenoperationen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e703e9adc531b7d1695d3e9bbed61a2c0f62ad31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="performing-culture-insensitive-string-operations"></a>Durchführen kulturunabhängiger Zeichenfolgenoperationen
Die meisten Methoden in .NET Framework, die in der Standardeinstellung kulturabhängige Zeichenfolgenoperationen ausführen bieten methodenüberladungen, mit denen Sie explizit angeben, die Kultur für die Verwendung durch das übergeben können eine <xref:System.Globalization.CultureInfo> Parameter. Diese Überladungen ermöglichen es Ihnen, kulturelle Variationen in Groß-/Kleinschreibungszuordnungen und Sortierregeln zu eliminieren und kulturunabhängige Ergebnisse zu gewährleisten.  
  
 Dieser Abschnitt enthält die folgenden Themen, in denen erläutert wird, wie kulturunabhängige Zeichenfolgenoperationen mit .NET Framework-Methoden durchgeführt werden, die standardmäßig kulturabhängig sind.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Durchführen kulturunabhängiger Zeichenfolgenvergleiche](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 Beschreibt, wie die <xref:System.String.Compare%2A?displayProperty=nameWithType> und <xref:System.String.CompareTo%2A?displayProperty=nameWithType> Methoden um kulturunabhängige Zeichenfolgenvergleiche durchzuführen.  
  
 [Durchführen kulturunabhängiger Schreibungsänderungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 Beschreibt, wie die <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, und <xref:System.Char.ToLower%2A?displayProperty=nameWithType> Methoden, um kulturunabhängige schreibungsänderungen auszuführen.  
  
 [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Auflistungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 Beschreibt, wie die <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> -Klasse, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> und <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> für kulturunabhängige Operationen in Auflistungen.  
  
 [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Arrays](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 Beschreibt, wie die <xref:System.Array.Sort%2A?displayProperty=nameWithType> und <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> Methoden für kulturunabhängige Operationen in Arrays.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Kulturunabhängige Zeichenfolgenoperationen](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 Beschreibt, warum Sie die Kultur berücksichtigen sollten, wenn Sie Operationen mit Zeichenfolgen ausführen, und enthält Richtlinien dazu, wann kulturabhängige Operationen und wann kulturunabhängige Operationen ausgeführt werden sollten.
