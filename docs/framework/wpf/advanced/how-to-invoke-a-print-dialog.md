---
title: "Gewusst wie: Aufrufen eines Druckdialogfelds | Microsoft Docs"
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
  - "Aufrufen von Druckdialogfeldern"
  - "Druckdialogfelder, Aufrufen"
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Aufrufen eines Druckdialogfelds
Um die Möglichkeit bereitzustellen, aus der Anwendung zu drucken, erstellen Sie einfach ein <xref:System.Windows.Controls.PrintDialog>\-Objekt und öffnen es.  
  
## Beispiel  
 Das <xref:System.Windows.Controls.PrintDialog>\-Steuerelement stellt einen einzelnen Einstiegspunkt für [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], Konfiguration und [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]\-Auftragsübermittlung bereit.  Das Steuerelement ist einfach zu verwenden und kann mithilfe von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Markup oder Code instanziiert werden.  Im folgenden Beispiel wird veranschaulicht, wie das Steuerelement in Code instanziiert und geöffnet und wie daraus gedruckt wird.  Des Weiteren wird gezeigt, wie sichergestellt wird, dass das Dialogfeld die Option enthält, mit der der Benutzer einen bestimmten Seitenbereich festlegen kann.  Im Beispielcode wird davon ausgegangen, dass eine FixedDocumentSequence.xps\-Datei im Stamm von Laufwerk C: vorhanden ist.  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Wenn das Dialogfeld geöffnet ist, können Benutzer einen der auf ihren Computern installierten Drucker auswählen.  Außerdem haben sie die Möglichkeit, den [Microsoft XPS\-Dokument\-Generator](http://go.microsoft.com/fwlink/?LinkId=147319) auszuwählen, um eine [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]\-Datei zu erstellen statt zu drucken.  
  
> [!NOTE]
>  Das <xref:System.Windows.Controls.PrintDialog?displayProperty=fullName>\-Steuerelement von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], das in diesem Thema beschrieben wird, darf nicht mit der <xref:System.Windows.Forms.PrintDialog?displayProperty=fullName>\-Komponente von [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] verwechselt werden.  
  
 Genau genommen können Sie die <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A>\-Methode verwenden, ohne je das Dialogfeld zu öffnen.  Auf diese Weise kann das Steuerelement als unsichtbare Druckkomponente verwendet werden.  Aus Leistungsgründen sollten Sie stattdessen die <xref:System.Printing.PrintQueue.AddJob%2A>\-Methode oder eine der vielen <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A>\-Methoden und <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>\-Methoden von <xref:System.Windows.Xps.XpsDocumentWriter> verwenden.  Weitere Informationen hierzu finden Sie unter [Programmgesteuertes Drucken von XPS\-Dateien](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md).  
  
## Siehe auch  
 <xref:System.Windows.Controls.PrintDialog>   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [Microsoft XPS\-Dokument\-Generator](http://go.microsoft.com/fwlink/?LinkId=147319)