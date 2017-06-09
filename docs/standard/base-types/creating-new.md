---
title: "Erstellen neuer Zeichenfolgen in .NET Framework | Microsoft Docs"
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
  - "Concat-Methode"
  - "CopyTo-Methode"
  - "Format-Methode"
  - "Insert-Methode"
  - "Join-Methode"
  - "Zeichenfolgen [.NET Framework], Erstellen"
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Erstellen neuer Zeichenfolgen in .NET Framework
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] ermöglicht mit einer einfachen Zuweisung das Erstellen von Zeichenfolgen und überlädt gleichzeitig einen Klassenkonstruktor, um das Erstellen von Zeichenfolgen mit einer Reihe verschiedener Parameter zu unterstützen.  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] stellt ebenfalls mehrere Methoden in der <xref:System.String?displayProperty=fullName>\-Klasse zur Verfügung, mit denen neue Zeichenfolgenobjekte erstellt werden, indem verschiedene Zeichenfolgen, Arrays von Zeichenfolgen oder Objekte kombiniert werden.  
  
## Zeichenfolgen mit einer Zuweisung erstellen  
 Der einfachste Weg zum Erstellen eines neuen <xref:System.String>\-Objekts besteht aus dem einfachen Zuweisen eines Zeichenfolgenliterals zu einem <xref:System.String>\-Objekt.  
  
## Zeichenfolgen mit einem Klassenkonstruktor erstellen  
 Sie können Überladungen des <xref:System.String>\-Klassenkonstruktors verwenden, um Zeichenfolgen aus Zeichenarrays zu erstellen.  Sie können eine neue Zeichenfolge auch erstellen, indem Sie ein bestimmtes Zeichen mit einer festgelegten Häufigkeit duplizieren.  
  
## Methoden, die Zeichenfolgen zurückgeben  
 In der folgenden Tabelle sind mehrere nützliche Methoden aufgeführt, die neue Zeichenfolgenobjekte zurückgeben.  
  
|Methodenname|Verwendung|  
|------------------|----------------|  
|<xref:System.String.Format%2A?displayProperty=fullName>|Erstellt aus einer Reihe von Eingabeobjekten eine formatierte Zeichenfolge.|  
|<xref:System.String.Concat%2A?displayProperty=fullName>|Erstellt Zeichenfolgen aus zwei oder mehreren Zeichenfolgen.|  
|<xref:System.String.Join%2A?displayProperty=fullName>|Erstellt eine neue Zeichenfolge, indem ein Array von Zeichenfolgen kombiniert wird.|  
|<xref:System.String.Insert%2A?displayProperty=fullName>|Erstellt eine neue Zeichenfolge, indem eine Zeichenfolge in den angegebenen Index einer bestehenden Zeichenfolge eingefügt wird.|  
|<xref:System.String.CopyTo%2A?displayProperty=fullName>|Kopiert die angegebenen Zeichen in einer Zeichenfolge an die angegebene Position in einem Zeichenarray.|  
  
### Format  
 Mit der **String.Format**\-Methode können Sie formatierte Zeichenfolgen erstellen und Zeichenfolgen verketten, die mehrere Objekte darstellen.  Diese Methode konvertiert automatisch alle übergebenen Objekte in eine Zeichenfolge.  Wenn in der Anwendung beispielsweise ein **Int32**\-Wert und ein **DateTime**\-Wert für den Benutzer angezeigt werden sollen, können Sie mit der **Format**\-Methode problemlos eine Zeichenfolge erstellen, die diese Werte darstellt.  Weitere Informationen zu Formatierungskonventionen für diese Methode finden Sie im Abschnitt [Kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md).  
  
 Im folgenden Beispiel wird mit der **Format**\-Methode eine Zeichenfolge erstellt, die eine ganzzahlige Variable verwendet.  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 In diesem Beispiel zeigt <xref:System.DateTime.Now%2A?displayProperty=fullName> das aktuelle Datum und die aktuelle Uhrzeit entsprechend der mit dem aktuellen Thread verknüpften Kultur an.  
  
### Concat  
 Mit der **String.Concat**\-Methode können Sie auf einfache Weise ein neues Zeichenfolgenobjekt aus zwei oder mehreren bestehenden Objekten erstellen.  Sie stellt eine sprachunabhängige Methode zur Verkettung von Zeichenfolgen dar.  Diese Methode akzeptiert jede Klasse, die von **System.Object** ableitet.  Im folgenden Beispiel wird eine Zeichenfolge aus zwei vorhandenen Zeichenfolgenobjekten und einem Trennzeichen erstellt.  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### Join  
 Mit der **String.Join**\-Methode wird aus einem Array von Zeichenfolgen und einer aus Trennzeichen bestehenden Zeichenfolge eine neue Zeichenfolge erstellt.  Diese Methode ist hilfreich, wenn Sie mehrere Zeichenfolgen verketten möchten, etwa in einer durch Kommas getrennten Liste.  
  
 Im folgenden Beispiel wird ein Leerzeichen verwendet, um ein Zeichenfolgenarray zu binden.  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### Insert  
 Mit der **String.Insert**\-Methode wird eine neue Zeichenfolge erstellt, indem eine Zeichenfolge an einer bestimmten Position in eine andere Zeichenfolge eingefügt wird.  Diese Methode verwendet einen nullbasierten Index.  Im folgenden Beispiel wird eine Zeichenfolge an der fünften Indexposition von `MyString` eingefügt und mit diesem Wert eine neue Zeichenfolge erstellt.  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### CopyTo  
 Mit der **String.CopyTo**\-Methode werden Teile einer Zeichenfolge in ein Zeichenarray kopiert.  Sie können sowohl den Startindex der Zeichenfolge als auch die Anzahl der zu kopierenden Zeichen angeben.  Diese Methode nimmt den Quellindex, ein Zeichenarray, den Zielindex und die Anzahl der zu kopierenden Zeichen an.  Alle Indizes sind nullbasiert.  
  
 Im folgenden Beispiel wird die **CopyTo**\-Methode verwendet, um die Zeichen des Begriffs "Hello" aus einem Zeichenfolgenobjekt an die erste Indexposition eines Zeichenarrays zu kopieren.  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## Siehe auch  
 [Grundlegende Zeichenfolgenoperationen](../../../docs/standard/base-types/basic-string-operations.md)   
 [Kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md)