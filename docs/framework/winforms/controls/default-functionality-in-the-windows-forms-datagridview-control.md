---
title: Standardfunktionalität des DataGridView-Steuerelements von Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b84d5a279bfe7cd99262ca904daeceabc9d0355d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648068"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Standardfunktionalität des DataGridView-Steuerelements von Windows Forms
Die Windows-Formulare <xref:System.Windows.Forms.DataGridView> Steuerelement bietet Benutzern eine beträchtliche Menge an Standardfunktionen.  
  
## <a name="default-functionality"></a>Standardfunktionen  
 Standardmäßig eine <xref:System.Windows.Forms.DataGridView> Steuerelement:  
  
- Zeigt automatisch Spaltenüberschriften und Zeilenüberschriften, die sichtbar bleiben, wie vertikalem der Tabelle Bildlauf an.  
  
- Verfügt über einen Zeilenkopf, der einen Auswahlindikator für die aktuelle Zeile enthält.  
  
- Verfügt über ein Auswahlrechteck in der ersten Zelle ein.  
  
- Enthält Spalten, die automatisch geändert werden können, wenn der Benutzer die Spaltenunterteiler doppelklickt.  
  
- Visuelle Stile automatisch auf Windows XP und Windows Server 2003-Produktfamilie unterstützt bei der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode wird aufgerufen, von der Anwendung `Main` Methode.  
  
 Darüber hinaus den Inhalt einer <xref:System.Windows.Forms.DataGridView> -Steuerelement standardmäßig bearbeitet werden kann:  
  
- Wenn der Benutzer doppelklickt, oder drücken F2 in einer Zelle, die Zelle in den Bearbeitungsmodus versetzt das Steuerelement automatisch und aktualisiert den Inhalt der Zelle, wenn der Benutzer eingibt.  
  
- Wenn der Benutzer einen Bildlauf bis zum Ende des Rasters durchführt, wird der Benutzer finden Sie, dass eine Zeile für neue Datensätze hinzufügen vorhanden ist. Wenn der Benutzer diese Zeile klickt, wird eine neue Zeile hinzugefügt, um die <xref:System.Windows.Forms.DataGridView> Steuerelement, mit Standardwerten. Wenn der Benutzer die ESC-Taste drückt, wird nicht mehr dieser neuen Zeile.  
  
- Wenn der Benutzer einen Zeilenkopf klickt, wird die gesamte Zeile ausgewählt.  
  
 Beim Binden einer <xref:System.Windows.Forms.DataGridView> Steuerelement mit einer Datenquelle durch Festlegen seiner <xref:System.Windows.Forms.DataGridView.DataSource%2A> -Eigenschaft, die das Steuerelement:  
  
- Verwendet automatisch die Namen der Spalten für die Datenquelle, als den Spaltenkopftext.  
  
- Wird mit dem Inhalt der Datenquelle aufgefüllt. <xref:System.Windows.Forms.DataGridView> Spalten werden für jede Spalte in der Datenquelle automatisch erstellt.  
  
- Erstellt eine Zeile für jede sichtbare Zeile in der Tabelle an.  
  
- Automatisch sortiert die Zeilen basierend auf den zugrunde liegenden Daten, wenn der Benutzer einen Spaltenheader klickt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- [DataGridView-Steuerelement](datagridview-control-windows-forms.md)
