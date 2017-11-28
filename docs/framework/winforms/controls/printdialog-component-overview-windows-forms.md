---
title: "Übersicht über die PrintDialog-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 20bbfd02c7fe8f5ca89d67e045b0edd4f2db996c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="printdialog-component-overview-windows-forms"></a>Übersicht über die PrintDialog-Komponente (Windows Forms)
Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) Komponente ist ein vorkonfiguriertes Dialogfeld zum Auswählen eines Druckers, wählen die zu druckenden Seiten aus, und bestimmen weiterer druckbezogener Einstellungen in Windows-basierten Anwendungen verwendet. Verwenden Sie sie als einfache Lösung für die Auswahl von Druckern und druckbezogenen Einstellungen, anstatt ein eigenes Dialogfeld zu konfigurieren. Sie können Benutzern ermöglichen, verschiedene Teile ihrer Dokumente zu drucken: Alles drucken, Drucken ein ausgewählten Seitenbereichs oder Drucken einer Auswahl. Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind. Die <xref:System.Windows.Forms.PrintDialog> Komponente erbt von der <xref:System.Windows.Forms.CommonDialog> Klasse.  
  
## <a name="working-with-the-component"></a>Arbeiten mit der Komponente  
 Verwenden der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen. Diese Komponente verfügt über Eigenschaften, die entweder einen einzelnen Druckauftrag beziehen (<xref:System.Drawing.Printing.PrintDocument> Klasse) oder die Einstellungen von einem einzelnen Drucker (<xref:System.Drawing.Printing.PrinterSettings> Klasse). Einer von beiden, kann wiederum mehrere Drucker freigegeben werden.  
  
 Wenn sie zu einem Formular hinzugefügt wird die <xref:System.Windows.Forms.PrintDialog> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.PrintDialog>  
 [PrintDialog-Komponente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)
