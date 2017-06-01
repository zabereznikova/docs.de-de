---
title: "Gewusst wie: Abrufen und Festlegen von Canvas-Positionierungseigenschaften | Microsoft Docs"
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
  - "Canvas-Steuerelement, Festlegen von Positionierungseigenschaften"
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Abrufen und Festlegen von Canvas-Positionierungseigenschaften
Dieses Beispiel veranschaulicht, wie die Positionierungsmethoden des <xref:System.Windows.Controls.Canvas>\-Elements zum Positionieren untergeordneter Inhalte verwendet werden.  In diesem Beispiel dient der Inhalt eines <xref:System.Windows.Controls.ListBoxItem> zur Darstellung von Positionierungswerten. Anschließend werden die Werte in Instanzen von <xref:System.Double> konvertiert, bei dem es sich um ein für die Positionierung erforderliches Argument handelt.  Die Werte werden anschließend erneut in Zeichenfolgen konvertiert und dann als Text in einem <xref:System.Windows.Controls.TextBlock>\-Element unter Verwendung der <xref:System.Windows.Controls.Canvas.GetLeft%2A>\-Methode angezeigt.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.ListBox>\-Element erstellt, das über elf auswählbare <xref:System.Windows.Controls.ListBoxItem>\-Elemente verfügt.  Das <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>\-Ereignis löst die benutzerdefinierte `ChangeLeft`\-Methode aus, die im nachfolgenden Codeblock definiert wird.  
  
 Jedes <xref:System.Windows.Controls.ListBoxItem> stellt einen <xref:System.Double>\-Wert dar. Hierbei handelt es sich um eins der Argumente, das von der <xref:System.Windows.Controls.Canvas.SetLeft%2A>\-Methode von <xref:System.Windows.Controls.Canvas> akzeptiert wird.  Um ein <xref:System.Windows.Controls.ListBoxItem> zur Darstellung einer Instanz von <xref:System.Double> zu verwenden, müssen Sie das <xref:System.Windows.Controls.ListBoxItem> zuerst in den richtigen Datentyp konvertieren.  
  
 [!code-xml[CanvasPositioningProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 Wenn ein Benutzer die <xref:System.Windows.Controls.ListBox>\-Auswahl ändert, wird die benutzerdefinierte `ChangeLeft`\-Methode aufgerufen.  Diese Methode übergibt das <xref:System.Windows.Controls.ListBoxItem> an ein <xref:System.Windows.LengthConverter>\-Objekt, das den <xref:System.Windows.Controls.ContentControl.Content%2A> eines <xref:System.Windows.Controls.ListBoxItem> in eine Instanz von <xref:System.Double> konvertiert \(dieser Wert wurde bereits in den Typ <xref:System.String> unter Verwendung der <xref:System.Windows.Controls.Control.ToString%2A>\-Methode konvertiert\).  Dieser Wert wird anschließend wieder an die <xref:System.Windows.Controls.Canvas.SetLeft%2A>\-Methode und die <xref:System.Windows.Controls.Canvas.GetLeft%2A>\-Methode von <xref:System.Windows.Controls.Canvas> übergeben, um die Position des `text1`\-Objekts zu ändern.  
  
 [!code-csharp[CanvasPositioningProperties#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.Canvas>   
 <xref:System.Windows.Controls.ListBoxItem>   
 <xref:System.Windows.LengthConverter>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)