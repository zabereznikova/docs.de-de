---
title: Übersicht über die PrintDialog-Komponente
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0ed7f7a1f9770f71b75ae744a056b6943335c852
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728666"
---
# <a name="printdialog-component-overview-windows-forms"></a>Übersicht über die PrintDialog-Komponente (Windows Forms)

Bei der Windows Forms [PrintDialog](printdialog-component-windows-forms.md) -Komponente handelt es sich um ein vorkonfiguriertes Dialogfeld, das zum Auswählen eines Druckers, zum Auswählen der zu Druck Ende Seiten und zum bestimmen anderer Druck bezogener Einstellungen in Windows-basierten Anwendungen verwendet wird. Verwenden Sie sie als einfache Lösung für die Auswahl von Druckern und druckbezogenen Einstellungen, anstatt ein eigenes Dialogfeld zu konfigurieren. Sie können es Benutzern ermöglichen, viele Teile Ihrer Dokumente zu drucken: alle drucken, den ausgewählten Seitenbereich drucken oder eine Auswahl drucken. Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind. Die <xref:System.Windows.Forms.PrintDialog> Komponente erbt von der <xref:System.Windows.Forms.CommonDialog>-Klasse.

## <a name="working-with-the-component"></a>Arbeiten mit der Komponente

Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>-Methode, um das Dialogfeld zur Laufzeit anzuzeigen. Diese Komponente verfügt über Eigenschaften, die entweder mit einem einzelnen Druckauftrag (<xref:System.Drawing.Printing.PrintDocument>-Klasse) oder den Einstellungen eines einzelnen Druckers (<xref:System.Drawing.Printing.PrinterSettings>-Klasse) in Beziehung stehen. Beide können wiederum von mehreren Druckern gemeinsam genutzt werden.

Wenn Sie einem Formular hinzugefügt wird, wird die <xref:System.Windows.Forms.PrintDialog> Komponente in der Leiste am unteren Rand des Windows Forms-Designer in Visual Studio angezeigt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.PrintDialog>
- [PrintDialog-Komponente](printdialog-component-windows-forms.md)
