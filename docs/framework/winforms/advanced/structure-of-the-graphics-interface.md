---
title: "Struktur der grafischen Oberfl&#228;che | Microsoft Docs"
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
  - "GDI+, Verwenden einer verwalteten Schnittstelle"
  - "Grafiken, Klassenstruktur"
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Struktur der grafischen Oberfl&#228;che
Die [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]\-Schnittstelle für verwaltete Klassen enthält ca. 60 Klassen, 50 Enumerationen und 8 Strukturen.  Das Kernstück der [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]\-Funktionen bildet die <xref:System.Drawing.Graphics>\-Klasse. Dies ist die Klasse, durch die Linien, Kurven, Formen, Bilder und Text tatsächlich gezeichnet werden.  
  
## Wichtige Klassen  
 Viele Klassen funktionieren in Verbindung mit der <xref:System.Drawing.Graphics>\-Klasse.  Beispielsweise erhält die <xref:System.Drawing.Graphics.DrawLine%2A>\-Methode ein <xref:System.Drawing.Pen>\-Objekt, das Attribute \(Farbe, Stärke, Strichelungsstil usw.\) der zu zeichnenden Linie enthält.  Die <xref:System.Drawing.Graphics.FillRectangle%2A>\-Methode kann einen Zeiger auf ein <xref:System.Drawing.Drawing2D.LinearGradientBrush>\-Objekt erhalten, der in Verbindung mit dem <xref:System.Drawing.Graphics>\-Objekt ein Rechteck mit einem Farbverlauf füllt.  <xref:System.Drawing.Font>\-Objekte und <xref:System.Drawing.StringFormat>\-Objekte beeinflussen, wie ein <xref:System.Drawing.Graphics>\-Objekt Text zeichnet.  Ein <xref:System.Drawing.Drawing2D.Matrix>\-Objekt speichert und bearbeitet die globale Transformation eines <xref:System.Drawing.Graphics>\-Objekts, das zum Drehen, Skalieren und Kippen von Bildern verwendet wird.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] stellt mehrere Strukturen \(z. B. <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point> und <xref:System.Drawing.Size>\) für das Organisieren von Grafikdaten bereit.  Darüber hinaus dienen bestimmte Klassen primär als strukturierte Datentypen.  Beispielsweise ist die <xref:System.Drawing.Imaging.BitmapData>\-Klasse eine Hilfe für die <xref:System.Drawing.Bitmap>\-Klasse und die <xref:System.Drawing.Drawing2D.PathData>\-Klasse eine Hilfe für die <xref:System.Drawing.Drawing2D.GraphicsPath>\-Klasse.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] definiert eine Reihe von Enumerationen, die Auflistungen von zusammenhängenden Konstanten sind.  So enthält z. B. die <xref:System.Drawing.Drawing2D.LineJoin>\-Enumeration die Elemente <xref:System.Drawing.Drawing2D.LineJoin>, <xref:System.Drawing.Drawing2D.LineJoin> und <xref:System.Drawing.Drawing2D.LineJoin>. Diese geben Stile an, mit denen zwei Linien miteinander verbunden werden können.  
  
## Siehe auch  
 [Übersicht über Grafiken](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)   
 [Verwalteter Code in GDI\+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)   
 [Verwenden von verwalteten Grafikklassen](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)