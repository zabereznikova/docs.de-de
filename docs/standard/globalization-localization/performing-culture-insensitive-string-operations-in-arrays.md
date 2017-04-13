---
title: "Durchf&#252;hren kulturunabh&#228;ngiger Zeichenfolgenoperationen in Arrays | Microsoft Docs"
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
  - "Arrays [.NET Framework], Kulturunabhängige Zeichenfolgenoperationen"
  - "comparer-Parameter"
  - "Kulturunabhängige Zeichenfolgenoperationen, In Arrays"
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Durchf&#252;hren kulturunabh&#228;ngiger Zeichenfolgenoperationen in Arrays
Überladungen der <xref:System.Array.Sort%2A?displayProperty=fullName>\-Methode und der <xref:System.Array.BinarySearch%2A?displayProperty=fullName>\>\-Methode führen standardmäßig kulturabhängige Sortierungen mithilfe der <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=fullName>\-Eigenschaft durch.  Die von diesen Methoden zurückgegebenen kulturabhängigen Ergebnisse können aufgrund von Unterschieden in den Sortierreihenfolgen der verschiedenen Kulturen variieren.  Verwenden Sie zum Beseitigen des kulturabhängigen Verhaltens eine der Überladungen dieser Methode, die einen `comparer`\-Parameter erwartet.  Der `comparer`\-Parameter gibt die <xref:System.Collections.IComparer>\-Implementierung an, die beim Vergleichen von Elementen im Array verwendet wird.  Geben Sie für den Parameter eine benutzerdefinierte, invariante Comparer\-Klasse an, die <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> verwendet.  Ein Beispiel für eine benutzerdefinierte, invariante Comparer\-Klasse finden Sie im untergeordneten Thema "Verwenden der SortedList\-Klasse" des Themas [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Auflistungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md).  
  
 **Hinweis** Beim Übergeben von **CultureInfo.InvariantCulture** an eine Vergleichsmethode wird ein kulturunabhängiger Vergleich ausgeführt.  Es wird jedoch kein nicht linguistischer Vergleich ausgeführt, z. B. auf Dateipfade, Registrierungsschlüssel und Umgebungsvariablen.  Eine Grundlage für Sicherheitsentscheidungen anhand des Vergleichsergebnisses ist dadurch nicht gegeben.  Wenn Sie einen nicht linguistischen Vergleich oder eine Grundlage für ergebnisbasierte Sicherheitsentscheidungen benötigen, muss die Anwendung eine Vergleichsmethode verwenden, die einen <xref:System.StringComparison>\-Wert akzeptiert.  Die Anwendung muss dann <xref:System.StringComparison> übergeben.  
  
## Siehe auch  
 <xref:System.Array.Sort%2A?displayProperty=fullName>   
 <xref:System.Array.BinarySearch%2A?displayProperty=fullName>   
 <xref:System.Collections.IComparer>   
 [Durchführen kulturunabhängiger Zeichenfolgenoperationen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)