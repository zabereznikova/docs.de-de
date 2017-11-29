---
title: "Übersicht über die PageSetupDialog-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 082dbff66c8a0f06635936011f802c99b88e41df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>Übersicht über die PageSetupDialog-Komponente (Windows Forms)
Windows Forms <xref:System.Windows.Forms.PageSetupDialog> Komponente ist ein vorkonfiguriertes Dialogfeld zum Festlegen der Seite Details für das Drucken in Windows-basierten Anwendungen verwendet. Verwenden Sie es in Ihrer Windows basierenden Anwendung als einfache Lösung, die für Benutzer zum Festlegen der Einstellungen für anstatt ein eigenes Dialogfeld zu konfigurieren. Sie können Benutzer zum Festlegen von Rahmen und Rand Korrekturen, Kopf- und Fußzeilen sowie hoch-oder Querformat aktivieren. Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind.  
  
## <a name="key-properties-and-methods"></a>Wichtige Eigenschaften und Methoden  
 Verwenden der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen. Diese Komponente verfügt über Eigenschaften, die Sie festlegen können, die entweder eine einzelne Seite beziehen (<xref:System.Drawing.Printing.PrintDocument> Klasse) oder einem beliebigen Dokument (<xref:System.Drawing.Printing.PageSettings> Klasse). Darüber hinaus die <xref:System.Windows.Forms.PageSetupDialog> Komponente kann verwendet werden, um zu bestimmen, und im rowsetcache bestimmte Druckereinstellungen fest, die <xref:System.Drawing.Printing.PrinterSettings> Klasse.  
  
 Wenn sie zu einem Formular hinzugefügt wird die <xref:System.Windows.Forms.PageSetupDialog> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [PageSetupDialog-Komponente](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)
