---
title: "Gewusst wie: Verwenden der FontSizeConverter-Klasse | Microsoft Docs"
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
  - "FontSizeConverter-Objekte"
  - "Typografie, FontSizeConverter-Objekte"
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Verwenden der FontSizeConverter-Klasse
## Beispiel  
 In diesem Beispiel wird erläutert, wie eine Instanz der <xref:System.Windows.FontSizeConverter>\-Klasse erstellt und zum Ändern eines Schriftgrads verwendet wird.  
  
 In dem Beispiel wird eine benutzerdefinierte Methode mit dem Namen `changeSize` definiert, mithilfe derer der Inhalt von <xref:System.Windows.Controls.ListBoxItem> \(definiert in einer separaten [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Datei\) in eine Instanz von <xref:System.Double> und danach in <xref:System.String> konvertiert wird.  Durch diese Methode wird das <xref:System.Windows.Controls.ListBoxItem> an ein <xref:System.Windows.FontSizeConverter>\-Objekt übergeben, das den <xref:System.Windows.Controls.ContentControl.Content%2A> eines <xref:System.Windows.Controls.ListBoxItem> in eine Instanz von <xref:System.Double> konvertiert.  Dieser Wert wird dann als Wert der <xref:System.Windows.Controls.TextBlock.FontSize%2A>\-Eigenschaft des <xref:System.Windows.Controls.TextBlock>\-Elements zurückgegeben.  
  
 Außerdem wird in diesem Beispiel eine zweite benutzerdefinierte Methode mit dem Namen `changeFamily` definiert.  Diese Methode konvertiert den <xref:System.Windows.Controls.ContentControl.Content%2A> des <xref:System.Windows.Controls.ListBoxItem> in einen <xref:System.String>\-Wert, der anschließend an die <xref:System.Windows.Controls.TextBlock.FontFamily%2A>\-Eigenschaft des <xref:System.Windows.Controls.TextBlock>\-Elements übergeben wird.  
  
 Dieses Beispiel wird nicht ausgeführt.  
  
 [!code-csharp[FontSizeConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## Siehe auch  
 <xref:System.Windows.FontSizeConverter>