---
title: Übersicht über die PageSetupDialog-Komponente
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: a891cb8cc77007d7591d41461c94f61c077eb300
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744338"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>Übersicht über die PageSetupDialog-Komponente (Windows Forms)

Bei der Windows Forms <xref:System.Windows.Forms.PageSetupDialog> Komponente handelt es sich um ein vorkonfiguriertes Dialogfeld, das zum Festlegen von Seitendetails für das Drucken in Windows-basierten Anwendungen verwendet wird. Verwenden Sie es in Ihrer Windows-basierten Anwendung als einfache Lösung, damit Benutzer Seiteneinstellungen festlegen können, anstatt ein eigenes Dialogfeld zu konfigurieren. Sie können es Benutzern ermöglichen, Rahmen-und Rand Anpassungen, Kopf-und Fußzeilen sowie hoch-oder Querformat festzulegen. Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind.

## <a name="key-properties-and-methods"></a>Schlüsseleigenschaften und-Methoden

Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>-Methode, um das Dialogfeld zur Laufzeit anzuzeigen. Diese Komponente verfügt über Eigenschaften, die Sie festlegen können, die sich entweder auf eine einzelne Seite (<xref:System.Drawing.Printing.PrintDocument> Klasse) oder auf ein beliebiges Dokument (<xref:System.Drawing.Printing.PageSettings> Klasse) beziehen. Darüber hinaus kann die <xref:System.Windows.Forms.PageSetupDialog> Komponente verwendet werden, um bestimmte Druckereinstellungen zu bestimmen, die in der <xref:System.Drawing.Printing.PrinterSettings>-Klasse gespeichert werden.

Wenn Sie einem Formular hinzugefügt wird, wird die <xref:System.Windows.Forms.PageSetupDialog> Komponente in der Leiste am unteren Rand des Windows Forms-Designer in Visual Studio angezeigt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.PageSetupDialog>
- [PageSetupDialog Component](pagesetupdialog-component-windows-forms.md)
