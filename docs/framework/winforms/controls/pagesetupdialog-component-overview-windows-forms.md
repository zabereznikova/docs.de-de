---
title: Übersicht über die PageSetupDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: 989183b6152dfccb6167d89433317cea596d83c5
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211744"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>Übersicht über die PageSetupDialog-Komponente (Windows Forms)

Die Windows-Formulare <xref:System.Windows.Forms.PageSetupDialog> Komponente ist ein vorkonfiguriertes Dialogfeld zum Festlegen von Seitendetails für das Drucken in Windows-basierten Anwendungen verwendet. Verwenden Sie es in Ihrer Windows-basierten Anwendung als einfache Lösung, die für Benutzer zum Festlegen der Einstellungen anstatt ein eigenes Dialogfeld zu konfigurieren. Sie können die Benutzer zum Festlegen von Rahmen und Rand Anpassungen, Kopfzeilen und Fußzeilen und hoch-oder Querformat aktivieren. Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind.

## <a name="key-properties-and-methods"></a>Wichtige Eigenschaften und Methoden

Verwenden der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen. Diese Komponente weist Eigenschaften können Sie festlegen, die entweder eine einzelne Seite beziehen (<xref:System.Drawing.Printing.PrintDocument> Klasse) oder eines Dokuments, (<xref:System.Drawing.Printing.PageSettings> Klasse). Darüber hinaus die <xref:System.Windows.Forms.PageSetupDialog> Komponente kann verwendet werden, um bestimmte Druckereinstellungen fest, zu bestimmen, und im rowsetcache der <xref:System.Drawing.Printing.PrinterSettings> Klasse.

Wenn es auf ein Formular hinzugefügt wird die <xref:System.Windows.Forms.PageSetupDialog> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer in Visual Studio angezeigt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.PageSetupDialog>
- [PageSetupDialog-Komponente](pagesetupdialog-component-windows-forms.md)
