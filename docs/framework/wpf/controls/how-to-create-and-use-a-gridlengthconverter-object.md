---
title: "Gewusst wie: Erstellen und Verwenden eines GridLengthConverter-Objekts | Microsoft Docs"
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
  - "Grid-Steuerelement, Erstellen, GridLengthConverter-Objekte"
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Erstellen und Verwenden eines GridLengthConverter-Objekts
## Beispiel  
 Im folgenden Beispiel wird das Erstellen und Verwenden einer Instanz von <xref:System.Windows.GridLengthConverter> veranschaulicht.  Im Beispiel wird eine benutzerdefinierte Methode mit dem Namen `changeCol` definiert, die <xref:System.Windows.Controls.ListBoxItem> an ein <xref:System.Windows.GridLengthConverter>\-Objekt übergibt. Dieses konvertiert <xref:System.Windows.Controls.ContentControl.Content%2A> von <xref:System.Windows.Controls.ListBoxItem> in eine Instanz von <xref:System.Windows.GridLength>.  Der konvertierte Wert wird dann als Wert der <xref:System.Windows.Controls.ColumnDefinition.Width%2A>\-Eigenschaft des <xref:System.Windows.Controls.ColumnDefinition>\-Elements zurückgegeben.  
  
 Außerdem wird im Beispiel eine zweite benutzerdefinierte Methode mit dem Namen `changeColVal` definiert.  Diese benutzerdefinierte Methode konvertiert <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> von <xref:System.Windows.Controls.Slider> in <xref:System.String> und gibt diesen Wert dann an <xref:System.Windows.Controls.ColumnDefinition> als <xref:System.Windows.Controls.ColumnDefinition.Width%2A> des Elements zurück.  
  
 Beachten Sie, dass eine separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Datei den Inhalt eines <xref:System.Windows.Controls.ListBoxItem> definiert.  
  
 [!code-csharp[gridlengthConverterGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## Siehe auch  
 <xref:System.Windows.GridLengthConverter>   
 <xref:System.Windows.GridLength>