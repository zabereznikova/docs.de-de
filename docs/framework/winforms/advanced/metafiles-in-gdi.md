---
title: "Metadateien in GDI+ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "GDI+, Metadateien"
  - "Bilder [Windows Forms], Metadateien"
  - "Metadateien"
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Metadateien in GDI+
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] stellt die <xref:System.Drawing.Imaging.Metafile>\-Klasse zum Aufzeichnen und Anzeigen von Metadateien bereit.  Eine Metadatei, auch Vektorbild genannt, ist ein Bild, das als eine Folge von Zeichenbefehlen und ‑einstellungen gespeichert wird.  Die in einem <xref:System.Drawing.Imaging.Metafile>\-Objekt aufgezeichneten Befehle und Einstellungen können im Arbeitsspeicher abgelegt oder in einer Datei oder einem Stream gespeichert werden.  
  
## Metadateiformate  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] kann Metadateien anzeigen, die in folgenden Formaten gespeichert wurden:  
  
-   Windows Metafile \(WMF\)  
  
-   Enhanced Metafile \(EMF\)  
  
-   EMF\+  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] kann Metadateien im EMF\- und im EMF\+\-Format, nicht jedoch im WMF\-Format aufzeichnen.  
  
 EMF\+ ist eine Erweiterung zu EMF, die die Speicherung von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]\-Aufzeichnungen ermöglicht.  Das EMF\+‑Format hat zwei Varianten: EMF\+ Only und EMF\+ Dual.  EMF\+ Only\-Metadateien enthalten nur [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]\-Aufzeichnungen.  Solche Metadateien können von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], aber nicht von [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] angezeigt werden.  EMF\+ Dual\-Metadateien enthalten Aufzeichnungen von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  Jeder [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]\-Aufzeichnung in einer EMF\+ Dual\-Metadatei ist eine alternative [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]\-Aufzeichnung zugeordnet.  Solche Metadateien können von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] oder von [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] angezeigt werden.  
  
 Das folgende Beispiel veranschaulicht eine Metadatei, die zuvor als Datei gespeichert wurde.  Die linke obere Ecke der Metadatei befindet sich an Position \(100, 100\).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)