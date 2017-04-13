---
title: "Gewusst wie: Auflisten installierter Schriftarten | Microsoft Docs"
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
  - "Beispiele [Windows Forms], Schriftarten"
  - "Schriftarten, Aufzählen der installierten"
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Auflisten installierter Schriftarten
Die <xref:System.Drawing.Text.InstalledFontCollection>\-Klasse erbt von der abstrakten <xref:System.Drawing.Text.FontCollection>\-Basisklasse.  Mit einem <xref:System.Drawing.Text.InstalledFontCollection>\-Objekt können Sie die Schriftarten aufzählen lassen, die auf dem Computer installiert sind.  Die <xref:System.Drawing.Text.FontCollection.Families%2A>\-Eigenschaft eines <xref:System.Drawing.Text.InstalledFontCollection>\-Objekts entspricht einem Array von <xref:System.Drawing.FontFamily>\-Objekten.  
  
## Beispiel  
 Im folgenden Beispiel werden die Namen aller auf dem Computer installierten Schriftfamilien aufgelistet.  Der Code ruft die <xref:System.Drawing.FontFamily.Name%2A>\-Eigenschaft jedes <xref:System.Drawing.FontFamily>\-Objekts im Array ab, das von der <xref:System.Drawing.Text.FontCollection.Families%2A>\-Eigenschaft zurückgegeben wird.  Beim Abrufen werden die Kategorienamen verkettet, sodass sie eine durch Trennzeichen getrennte Liste ergeben.  Anschließend wird die durch Trennzeichen getrennte Liste von der <xref:System.Drawing.Graphics.DrawString%2A>\-Methode der <xref:System.Drawing.Graphics>\-Klasse in einem Rechteck gezeichnet.  
  
 Wenn Sie den Beispielcode ausführen, erhalten Sie ein Ergebnis, das mit dem in der folgenden Abbildung vergleichbar ist.  
  
 ![Installierte Schriftarten](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  Zusätzlich sollten Sie den <xref:System.Drawing.Text>\-Namespace importieren.  
  
## Siehe auch  
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)