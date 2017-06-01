---
title: "Gewusst wie: Extrahieren eines mit einer Datei verkn&#252;pften Symbols in Windows Forms | Microsoft Docs"
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
  - "Anzeigen eines Dateinamens und seines Dateitypsymbols in einem ListView-Steuerelement [Windows Forms]"
  - "Extrahieren von Dateitypen zugeordneten Symbolen [Windows Forms]"
  - "Dateinamenerweiterung-Symbole [Windows Forms], Anzeigen in einer ListView"
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Extrahieren eines mit einer Datei verkn&#252;pften Symbols in Windows Forms
Viele Dateien verfügen über eingebettete Symbole, die eine visuelle Darstellung des zugeordneten Dateityps ermöglichen.  Zum Beispiel enthalten Microsoft Word\-Dokumente ein Symbol, das sie als Word\-Dokumente kennzeichnet.  Beim Anzeigen von Dateien in einem Listensteuerelement oder einem Tabellensteuerelement möchten Sie möglicherweise das Symbol, das den Dateityp darstellt, jeweils neben dem Dateinamen anzeigen lassen.  Dies kann auf einfache Weise mithilfe der <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A>\-Methode ausgeführt werden.  
  
## Beispiel  
 Das folgende Codebeispiel zeigt, wie das einer Datei zugeordnete Symbol extrahiert wird und der Dateiname sowie das zugehörige Symbol im <xref:System.Windows.Forms.ListView>\-Steuerelement angezeigt werden können.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## Kompilieren des Codes  
 So kompilieren Sie das Beispiel  
  
-   Fügen Sie den oben aufgeführten Code in ein Windows Form ein, und rufen Sie die `ExtractAssociatedIconExample`\-Methode aus dem Konstruktor oder aus der <xref:System.Windows.Forms.Form.Load>\-Ereignisbehandlungsmethode des Formulars auf.  
  
     Stellen Sie sicher, dass das Formular den <xref:System.IO>\-Namespace importiert.  
  
## Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)