---
title: "Enumerationsformatzeichenfolgen | Microsoft Docs"
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
  - "Enumerationsformatzeichenfolgen"
  - "Formatbezeichner, Enumerationsformatzeichenfolgen"
  - "Formatieren [.NET Framework], Enumeration"
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Enumerationsformatzeichenfolgen
Sie können mit der <xref:System.Enum.ToString%2A?displayProperty=fullName>\-Methode ein neues Zeichenfolgenobjekt erstellen, das den numerischen, hexadezimalen oder den Zeichenfolgenwert eines Enumerationsmembers darstellt.  Diese Methode übernimmt eine der Enumerationsformatzeichenfolgen, um den Wert anzugeben, den Sie zurückgeben möchten.  
  
 In der folgenden Tabelle werden die Enumerationsformatzeichenfolgen und die Werte aufgelistet, die von diesen zurückgegeben werden.  Bei diesen Formatbezeichnern wird die Groß\- und Kleinschreibung nicht berücksichtigt.  
  
|Formatzeichenfolge|Ergebnis|  
|------------------------|--------------|  
|G oder g|Zeigt, soweit möglich, den Enumerationseintrag als Zeichenfolgenwert an. Andernfalls wird der Ganzzahlwert der aktuellen Instanz angezeigt.  Wenn die Enumeration mit festgelegtem **Flags**\-Attribut definiert ist, werden die Zeichenfolgenwerte der einzelnen gültigen Einträge verkettet und durch Kommas getrennt.  Wenn das **Flags**\-Attribut nicht festgelegt ist, wird ein ungültiger Wert als numerischer Eintrag angezeigt.  Im folgenden Beispiel wird der G\-Formatbezeichner veranschaulicht.<br /><br /> [!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)]
 [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]|  
|F oder f|Zeigt den Enumerationseintrag, soweit möglich, als Zeichenfolgenwert an.  Wenn der Wert vollständig als eine Summe der Einträge in der Enumeration angezeigt werden kann \(auch wenn das **Flags**\-Attribut fehlt\), werden die Zeichenfolgenwerte der einzelnen gültigen Einträge verkettet und durch Kommas getrennt.  Wenn der Wert nicht vollständig durch die Enumerationseinträge bestimmt werden kann, wird der Wert als Ganzzahlwert formatiert.  Im folgenden Beispiel wird der F\-Formatbezeichner veranschaulicht.<br /><br /> [!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)]
 [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]|  
|D oder d|Zeigt den Enumerationseintrag als Ganzzahlwert in der kürzesten möglichen Darstellung an.  Im folgenden Beispiel wird der D\-Formatbezeichner veranschaulicht.<br /><br /> [!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)]
 [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]|  
|X oder x|Zeigt den Enumerationseintrag als hexadezimalen Wert an.  Der Wert wird mit ggf. mit vorangestellten Nullen dargestellt, damit der Wert mindestens acht Ziffern enthält.  Im folgenden Beispiel wird der X\-Formatbezeichner veranschaulicht.<br /><br /> [!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)]
 [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]|  
  
## Beispiel  
 Im folgenden Beispiel wird eine Enumeration mit der Bezeichnung `Colors` definiert, die drei Einträge enthält: `Red`, `Blue` und `Green`.  
  
 [!code-csharp[Formatting.Enum#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
 [!code-vb[Formatting.Enum#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]  
  
 Nachdem die Enumeration definiert wurde, kann folgendermaßen eine Instanz deklariert werden.  
  
 [!code-csharp[Formatting.Enum#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
 [!code-vb[Formatting.Enum#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]  
  
 Die `Color.ToString(System.String)`\-Methode kann dann dazu verwendet werden, den Enumerationswert auf verschiedene Arten anzuzeigen. Wie er angezeigt wird, hängt vom übergebenen Formatbezeichner ab.  
  
 [!code-csharp[Formatting.Enum#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
 [!code-vb[Formatting.Enum#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]  
  
## Siehe auch  
 [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)