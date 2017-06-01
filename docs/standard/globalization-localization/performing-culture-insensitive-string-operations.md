---
title: "Durchf&#252;hren kulturunabh&#228;ngiger Zeichenfolgenoperationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Schreibungszuordnungen"
  - "Benutzerdefinierte Schreibungszuordnungen"
  - "Kultur, benutzerdefinierte Sortierregeln"
  - "Benutzerdefinierte Sortierregeln"
  - "Kulturunabhängige Zeichenfolgenoperationen, Optionen zum Durchführen"
  - "Kultur, benutzerdefinierte Schreibungszuordnungen"
  - "Kulturunabhängige Zeichenfolgenoperationen, Methodenüberladungen"
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Durchf&#252;hren kulturunabh&#228;ngiger Zeichenfolgenoperationen
Die meisten .NET Framework\-Methoden, die in der Standardeinstellung kulturabhängige Zeichenfolgenoperationen durchführen, stellen Methodenüberladungen bereit, mit denen die zu verwendende Kultur durch Übergabe eines <xref:System.Globalization.CultureInfo>\-Parameters explizit angegeben werden kann.  Mit diesen Überladungen können Sie kulturelle Variationen bei Zuordnungen von Groß\-\/Kleinschreibung und Sortierregeln eliminieren und kulturunabhängige Ergebnisse sicherstellen.  
  
 Dieser Abschnitt enthält die folgenden Themen, in denen das Durchführen von kulturunabhängigen Zeichenfolgenoperationen mithilfe von standardmäßig kulturabhängigen .NET Framework\-Methoden erläutert wird.  
  
## In diesem Abschnitt  
 [Durchführen kulturunabhängiger Zeichenfolgenvergleiche](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 Beschreibt die Verwendung der <xref:System.String.Compare%2A?displayProperty=fullName>\-Methode und der <xref:System.String.CompareTo%2A?displayProperty=fullName>\-Methode zum Durchführen kulturunabhängiger Zeichenfolgenvergleiche.  
  
 [Durchführen kulturunabhängiger Schreibungsänderungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 Beschreibt die Verwendung der Methoden <xref:System.String.ToUpper%2A?displayProperty=fullName>, <xref:System.String.ToLower%2A?displayProperty=fullName>, <xref:System.Char.ToUpper%2A?displayProperty=fullName> und <xref:System.Char.ToLower%2A?displayProperty=fullName> zum Durchführen kulturunabhängiger Änderungen der Groß\-\/Kleinschreibung.  
  
 [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Auflistungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 Beschreibt die Verwendung der Klassen [CaseInsensitiveComparer](frlrfSystemCollectionsCaseInsensitiveComparerClassTopic), <xref:System.Collections.CaseInsensitiveHashCodeProvider> und [SortedList](frlrfSystemCollectionsSortedListClassTopic) sowie der [ArrayList.Sort](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)\-Methode und [CollectionsUtil.CreateCaseInsensitiveHashtable](frlrfSystemCollectionsSpecializedCollectionsUtilClassCreateCaseInsensitiveHashtableTopic)\-Methode zum Durchführen kulturunabhängiger Operationen in Auflistungen.  
  
 [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Arrays](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 Beschreibt die Verwendung der <xref:System.Array.Sort%2A?displayProperty=fullName>\-Methode und der <xref:System.Array.BinarySearch%2A?displayProperty=fullName>\-Methode zum Durchführen kulturunabhängiger Operationen in Arrays.  
  
## Verwandte Abschnitte  
 [Kulturunabhängige Zeichenfolgenoperationen](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 Beschreibt die Bedeutung der Kultur beim Durchführen von Zeichenfolgenoperationen und enthält Richtlinien für die Verwendung von kulturabhängigen und kulturunabhängigen Operationen.