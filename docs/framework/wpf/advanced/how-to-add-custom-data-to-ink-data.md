---
title: "Gewusst wie: Hinzuf&#252;gen von benutzerdefinierten Daten zu Freihanddaten | Microsoft Docs"
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
  - "Freihanddaten, Hinzufügen benutzerdefinierter Daten"
  - "InkCanvas, Anzeigen"
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Hinzuf&#252;gen von benutzerdefinierten Daten zu Freihanddaten
Benutzerdefinierte Daten können Freihanddaten hinzugefügt werden, die gespeichert werden, wenn die Freihanddaten als ISF \(Ink Serialized Format\)\-Daten gespeichert werden.  Sie können die benutzerdefinierten Daten in dem Objekt <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection> oder <xref:System.Windows.Ink.Stroke> speichern.  Durch die Möglichkeit benutzerdefinierte Daten in drei Objekten zu speichern, kann der beste Ort zum Speichern ausgewählt werden.  Alle drei Klassen verwenden ähnliche Methoden, um benutzerdefinierte Daten zu speichern und auf diese zuzugreifen.  
  
 Nur die folgenden Typen können als benutzerdefinierte Daten gespeichert werden:  
  
-   <xref:System.Boolean>  
  
-   <xref:System.Boolean>\[\]  
  
-   <xref:System.Byte>  
  
-   <xref:System.Byte>\[\]  
  
-   <xref:System.Char>  
  
-   <xref:System.Char>\[\]  
  
-   <xref:System.DateTime>  
  
-   <xref:System.DateTime>\[\]  
  
-   <xref:System.Decimal>  
  
-   <xref:System.Decimal>\[\]  
  
-   <xref:System.Double>  
  
-   <xref:System.Double>\[\]  
  
-   <xref:System.Int16>  
  
-   <xref:System.Int16>\[\]  
  
-   <xref:System.Int32>  
  
-   <xref:System.Int32>\[\]  
  
-   <xref:System.Int64>  
  
-   <xref:System.Int64>\[\]  
  
-   <xref:System.Single>  
  
-   <xref:System.Single>\[\]  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <xref:System.UInt16>\[\]  
  
-   <xref:System.UInt32>  
  
-   <xref:System.UInt32>\[\]  
  
-   <xref:System.UInt64>  
  
-   <xref:System.UInt64>\[\]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie benutzerdefinierte Daten einem <xref:System.Windows.Ink.StrokeCollection>\-Objekt hinzugefügt und daraus abgerufen werden.  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 Im folgenden Beispiel wird eine Anwendung erstellt, die ein <xref:System.Windows.Controls.InkCanvas>\-Steuerelement und zwei Schaltflächen anzeigt.  Die Schaltfläche `switchAuthor` aktiviert zwei Stifte, die von zwei verschiedenen Autoren verwendet werden können.  Die Schaltfläche `changePenColors` ändert je nach Autor die Farbe jedes Strichs auf dem <xref:System.Windows.Controls.InkCanvas>\-Steuerelement.  Die Anwendung definiert zwei <xref:System.Windows.Ink.DrawingAttributes>\-Objekte und fügt jedem eine benutzerdefinierte Eigenschaft hinzu, die anzeigt, von welchem Autor <xref:System.Windows.Ink.Stroke> gezeichnet wurde.  Wenn der Benutzer auf `changePenColors` klickt, ändert die Anwendung dem Wert der benutzerdefinierten Eigenschaft entsprechend die Darstellung des Strichs.  
  
 [!code-xml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]