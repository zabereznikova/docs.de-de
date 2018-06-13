---
title: Standardfunktionalität des DataGridView-Steuerelements von Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: a475d8bce388860c88571fbf638d206bfe01223d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526626"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Standardfunktionalität des DataGridView-Steuerelements von Windows Forms
Windows Forms <xref:System.Windows.Forms.DataGridView> Steuerelement bietet Benutzern eine beträchtliche Menge an Standardeinstellung Funktionalität.  
  
## <a name="default-functionality"></a>Standardfunktionen  
 Wird standardmäßig ein <xref:System.Windows.Forms.DataGridView> Steuerelement:  
  
-   Zeigt automatisch Spaltenüberschriften und Zeilenüberschriften, die sichtbar bleiben, wenn die Tabelle vertikal einen Bildlauf durchführt.  
  
-   Verfügt über einen Zeilenkopf, der einen Auswahlindikator für die aktuelle Zeile enthält.  
  
-   Verfügt über ein Auswahlrechteck in der ersten Zelle ein.  
  
-   Enthält Spalten, die automatisch angepasst werden können, wenn der Benutzer die Spaltenunterteiler doppelklickt.  
  
-   Automatisch visuelle Stile unter Windows XP und Windows Server 2003-Produktfamilie unterstützt bei der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode wird aufgerufen, aus der Anwendungsverzeichnis `Main` Methode.  
  
 Darüber hinaus den Inhalt einer <xref:System.Windows.Forms.DataGridView> -Steuerelement standardmäßig bearbeitet werden kann:  
  
-   Wenn der Benutzer doppelklickt oder in einer Zelle F2 drückt, wird das Steuerelement automatisch versetzt die Zelle in den Bearbeitungsmodus, und aktualisiert den Inhalt der Zelle als vom Benutzer eingegebenen.  
  
-   Wenn der Benutzer einen Bildlauf bis zum Ende des Rasters durchführt, wird der Benutzer angezeigt, dass eine Zeile für neue Datensätze hinzufügen vorhanden ist. Wenn der Benutzer diese Zeile klickt, wird eine neue Zeile hinzugefügt, um die <xref:System.Windows.Forms.DataGridView> Steuerelement mit Standardwerten. Wenn der Benutzer die ESC-Taste drückt, verschwindet dieser neuen Zeile auf.  
  
-   Wenn der Benutzer auf einen Zeilenheader klickt, wird die gesamte Zeile ausgewählt.  
  
 Beim Binden einer <xref:System.Windows.Forms.DataGridView> Steuerelement mit einer Datenquelle durch Festlegen seiner <xref:System.Windows.Forms.DataGridView.DataSource%2A> -Eigenschaft, die das Steuerelement:  
  
-   Verwendet automatisch die Namen der Spalten der Datenquelle, wie der Text der Spaltenüberschrift.  
  
-   Wird mit dem Inhalt der Datenquelle aufgefüllt. <xref:System.Windows.Forms.DataGridView> Spalten werden für jede Spalte in der Datenquelle automatisch erstellt.  
  
-   Erstellt eine Zeile für jede sichtbare Zeile in der Tabelle an.  
  
-   Automatisch sortiert die Zeilen basierend auf den zugrunde liegenden Daten, wenn der Benutzer auf einen Spaltenheader klickt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 [DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
