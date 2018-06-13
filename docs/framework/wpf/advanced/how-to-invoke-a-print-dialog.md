---
title: 'Gewusst wie: Aufrufen eines Druckdialogfelds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: f94a965f724e85fb63ed9c98ebddba40938eb9b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545557"
---
# <a name="how-to-invoke-a-print-dialog"></a>Gewusst wie: Aufrufen eines Druckdialogfelds
Um die Möglichkeit zum Drucken aus der Anwendung zu ermöglichen, Sie können einfach erstellen und Öffnen einer <xref:System.Windows.Controls.PrintDialog> Objekt.  
  
## <a name="example"></a>Beispiel  
 Das <xref:System.Windows.Controls.PrintDialog>-Steuerelement stellt einen einheitlichen Einstiegspunkt für [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], Konfiguration und [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]-Auftragsübermittlung bereit. Das Steuerelement ist einfach zu verwenden und instanziiert werden kann, mithilfe von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Markup oder-Code. Im folgende Beispiel wird demonstriert, wie zu instanziieren und öffnen das Steuerelement im Code und daraus zu drucken. Es wird gezeigt, wie stellen Sie sicher, dass das Dialogfeld "dem Benutzer die Möglichkeit, einen bestimmten Bereich von Seiten bereitgestellt wird. Im Beispielcode wird davon ausgegangen, dass eine FixedDocumentSequence.xps-Datei im Stammverzeichnis des Laufwerks "c:" vorhanden ist.  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Sobald das Dialogfeld geöffnet ist, werden Benutzer auf ihrem Computer installierten Drucker auswählen können. Sie müssen auch die Möglichkeit auszuwählen der [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319) zum Erstellen einer [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] Datei nicht drucken.  
  
> [!NOTE]
>  Die <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> Kontrolle über [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], die in diesem Thema erläutert wird dürfen nicht mit verwechselt werden die <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> -Komponente von Windows Forms.  
  
 Streng genommen, können Sie die <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> Methode ohne jemals das Dialogfeld zu öffnen. In dieser Hinsicht kann das Steuerelement als ein Druckkomponente verwendet werden. Aber aus Gründen der Leistung wäre es besser, verwenden Sie entweder die <xref:System.Printing.PrintQueue.AddJob%2A> Methode oder eine der vielen <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> und <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> Methoden die <xref:System.Windows.Xps.XpsDocumentWriter>. Weitere Informationen hierzu finden Sie unter [Programmgesteuertes Drucken XPS-Dateien](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) und.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.PrintDialog>  
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)
