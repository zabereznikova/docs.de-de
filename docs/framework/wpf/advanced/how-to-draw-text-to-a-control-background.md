---
title: "Gewusst wie: Zeichnen von Text im Hintergrund eines Steuerelements | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Hintergründe, Zeichnen von Text in"
  - "Steuerelemente, Zeichnen von Text in Hintergründen"
  - "Zeichnen, Text zum Steuern von Hintergründen"
  - "Text, Zeichnen zum Steuern von Hintergründen"
  - "Typografie, Zeichnen von Text zum Steuern von Hintergründen"
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Zeichnen von Text im Hintergrund eines Steuerelements
Sie können Text direkt im Hintergrund eines Steuerelements zeichnen, indem Sie die Textzeichenfolge in ein <xref:System.Windows.Media.FormattedText>\-Objekt konvertieren und daraufhin das Objekt im <xref:System.Windows.Media.DrawingContext> des Steuerelements zeichnen.  Sie können diese Vorgehensweise auch verwenden, um im Hintergrund von Objekten zu zeichnen, die aus <xref:System.Windows.Controls.Panel> abgeleitet werden, z. B. <xref:System.Windows.Controls.Canvas> und <xref:System.Windows.Controls.StackPanel>.  
  
 ![Steuerelemente zur Anzeige von Text als Hintergrund](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")  
Beispiel für Steuerelemente mit benutzerdefinierten Texthintergründen  
  
## Beispiel  
 Um im Hintergrund eines Steuerelements zu zeichnen, erstellen Sie ein neues <xref:System.Windows.Media.DrawingBrush>\-Objekt und zeichnen den konvertierten Text im <xref:System.Windows.Media.DrawingContext> des Objekts.  Danach weisen Sie das neue <xref:System.Windows.Media.DrawingBrush>\-Objekt der Hintergrundeigenschaft des Steuerelements zu.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie ein <xref:System.Windows.Media.FormattedText>\-Objekt erstellen und es im Hintergrund der Objekte <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.Button> zeichnen.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## Siehe auch  
 <xref:System.Windows.Media.FormattedText>   
 [Zeichnen von formatiertem Text](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)