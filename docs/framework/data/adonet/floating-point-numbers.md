---
title: "Gleitkommazahlen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 73c218c6-1c44-4402-a167-4f6262629a91
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Gleitkommazahlen
In diesem Thema werden einige der Probleme beschrieben, auf die Entwickler beim Arbeiten mit Gleitkommazahlen in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] häufig stoßen.  Ursache für diese Probleme, die nicht spezifisch für einen bestimmten Anbieter wie <xref:System.Data.SqlClient> oder <xref:System.Data.OracleClient> sind, ist die Art und Weise, wie Computer Gleitkommazahlen speichern.  
  
 Für Gleitkommazahlen gibt es in der Regel keine genaue binäre Darstellung.  Stattdessen speichert der Computer einen Näherungswert der Zahl.  Es ist möglich, dass zu unterschiedlichen Zeiten auch unterschiedliche Binärziffern zur Darstellung der Zahl verwendet werden.  Wenn die Darstellung einer Gleitkommazahl in eine andere Darstellung umgewandelt wird, können die letzten gültigen Ziffern dieser Zahl geringfügig anders ausfallen.  Zu einer solchen Umwandlung kommt es in der Regel dann, wenn die Zahl von einem Typ in einen anderen Typ konvertiert wird.  Die Abweichung tritt unabhängig davon auf, ob die Umwandlung innerhalb einer Datenbank, zwischen Typen, die Datenbankwerte darstellen, oder zwischen Typen erfolgt.  Aufgrund dieser Änderungen können sich Zahlen, die logisch gleich sind, in ihren letzten gültigen Ziffern unterscheiden, sodass sie verschiedene Werte besitzen.  Die Anzahl der präzisen Ziffern in der Zahl kann höher oder niedriger als erwartet ausfallen.  Beim Formatieren als Zeichenfolge zeigt die Zahl u. U. nicht den erwarteten Wert.  
  
 Um diese Effekte so gering wie möglich zu halten, sollten Sie die bestmögliche Übereinstimmung zwischen den Ihnen zur Verfügung stehenden numerischen Typen verwenden.  Wenn Sie z. B. mit [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] arbeiten, kann sich der exakte numerische Wert ändern, wenn Sie einen Transact\-SQL\-Wert des Typs \<legacyBold\>real\<\/legacyBold\> in einen Wert des Typs \<legacyBold\>float\<\/legacyBold\> ändern.  In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] kann auch die Umwandlung von <xref:System.Single> zu <xref:System.Double> zu unerwarteten Ergebnissen führen.  In beiden Fällen empfiehlt es sich, dafür zu sorgen, dass alle Werte in der Anwendung denselben numerischen Typ verwenden.  Sie können auch einen Dezimaltyp mit fester Genauigkeit verwenden oder Gleitkommazahlen in Dezimalzahlen mit fester Genauigkeit umwandeln, bevor Sie mit ihnen arbeiten.  
  
 Wenn Sie Probleme mit Gleichheitsvergleichen umgehen möchten, überlegen Sie, ob Sie Ihre Anwendung nicht so programmieren können, dass Abweichungen bei den letzten gültigen Ziffern ignoriert werden.  So können Sie z. B. statt zu vergleichen, ob zwei Zahlen gleich sind, eine Zahl von der anderen Zahl subtrahieren.  Wenn die Differenz in einem akzeptablen Rundungsbereich liegt, kann Ihre Anwendung die Zahlen so behandeln, als wären sie gleich.  
  
## Siehe auch  
 [Warum Gleitkommazahlen an Genauigkeit verlieren können](../Topic/Why%20Floating-Point%20Numbers%20May%20Lose%20Precision.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)