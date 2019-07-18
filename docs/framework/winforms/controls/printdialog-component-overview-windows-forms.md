---
title: Übersicht über die PrintDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 2478990e3cec00df9a748dbd9875485e5f060ed7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211757"
---
# <a name="printdialog-component-overview-windows-forms"></a>Übersicht über die PrintDialog-Komponente (Windows Forms)

Die Windows-Formulare [PrintDialog](printdialog-component-windows-forms.md) Komponente ist ein vorkonfiguriertes Dialogfeld zum Auswählen eines Druckers, die zu druckenden Seiten auswählen sowie weitere druckbezogene Einstellungen in Windows-basierten Anwendungen ermitteln. Verwenden Sie sie als einfache Lösung für die Auswahl von Druckern und druckbezogenen Einstellungen, anstatt ein eigenes Dialogfeld zu konfigurieren. Sie können Benutzern ermöglichen, verschiedene Teile ihrer Dokumente zu drucken: Alles drucken, Drucken ein ausgewählten Seitenbereichs oder Drucken einer Auswahl. Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind. Die <xref:System.Windows.Forms.PrintDialog> Komponente erbt von der <xref:System.Windows.Forms.CommonDialog> Klasse.

## <a name="working-with-the-component"></a>Arbeiten mit der Komponente

Verwenden der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen. Diese Komponente verfügt über Eigenschaften, die sich auf einen einzelnen Druckauftrag beziehen (<xref:System.Drawing.Printing.PrintDocument> Klasse) oder die einen einzelnen Drucker (<xref:System.Drawing.Printing.PrinterSettings> Klasse). Entweder diese kann wiederum mehrere Drucker freigegeben werden.

Wenn es auf ein Formular hinzugefügt wird die <xref:System.Windows.Forms.PrintDialog> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer in Visual Studio angezeigt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.PrintDialog>
- [PrintDialog-Komponente](printdialog-component-windows-forms.md)
