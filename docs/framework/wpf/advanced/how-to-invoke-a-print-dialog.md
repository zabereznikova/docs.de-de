---
title: 'Vorgehensweise: Aufrufen eines Druckdialogfelds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: 2ced508eb83e2955fdcd1ad87fb6415e2052446f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757147"
---
# <a name="how-to-invoke-a-print-dialog"></a>Vorgehensweise: Aufrufen eines Druckdialogfelds
Um die Funktion zum Drucken von aus der Anwendung zu ermöglichen, Sie können einfach erstellen und öffnen Sie eine <xref:System.Windows.Controls.PrintDialog> Objekt.  
  
## <a name="example"></a>Beispiel  
 Das <xref:System.Windows.Controls.PrintDialog>-Steuerelement stellt einen einheitlichen Einstiegspunkt für [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], Konfiguration und [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]-Auftragsübermittlung bereit. Das Steuerelement ist benutzerfreundlich und kann instanziiert werden, indem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Markup oder Code. Im folgende Beispiel wird veranschaulicht, wie zu instanziieren und öffnen Sie das Steuerelement in Code und daraus zu drucken. Es wird gezeigt, wie stellen Sie sicher, dass das Dialogfeld die Benutzer die Möglichkeit, einen bestimmten Bereich von Seiten festlegen erhält. Im Beispielcode wird davon ausgegangen, dass eine FixedDocumentSequence.xps-Datei im Stammverzeichnis von Laufwerk C: vorhanden ist.  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Sobald das Dialogfeld geöffnet ist, werden Benutzer auf dem Computer installierten Drucker auswählen können. Haben sie auch die Option der Auswahl der [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319) erstellen eine [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] Datei drucken.  
  
> [!NOTE]
>  Die <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> Kontrolle über [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], die in diesem Thema erläutert wird darf nicht mit verwechselt werden die <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> -Komponente von Windows Forms.  
  
 Genau genommen können Sie die <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> -Methode ohne jemals Öffnen des Dialogfelds. In dieser Hinsicht kann das Steuerelement als eine Druckkomponente verwendet werden. Aber zur Verbesserung der Leistung, es wäre besser, verwenden Sie entweder die <xref:System.Printing.PrintQueue.AddJob%2A> Methode oder eine der zahlreichen <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> und <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> Methoden der <xref:System.Windows.Xps.XpsDocumentWriter>. Weitere Informationen hierzu finden Sie unter [Programmgesteuertes Drucken von XPS-Dateien](how-to-programmatically-print-xps-files.md) und.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.PrintDialog>
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
- [Microsoft XPS-Dokument-Generator](https://go.microsoft.com/fwlink/?LinkId=147319)
