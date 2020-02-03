---
title: Standardfunktionen im DataGridView-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b695883ac7ec3fb0c459adb66214b0eceab3a128
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746136"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Standardfunktionalität des DataGridView-Steuerelements von Windows Forms
Das Windows Forms <xref:System.Windows.Forms.DataGridView>-Steuerelement bietet Benutzern eine beträchtliche Menge an Standardfunktionen.  
  
## <a name="default-functionality"></a>Standardfunktionalität  
 Standardmäßig ist ein <xref:System.Windows.Forms.DataGridView>-Steuerelement:  
  
- Zeigt automatisch Spaltenkopfzeilen und Zeilen Header an, die sichtbar bleiben, wenn die Tabelle vertikal scrollt.  
  
- Verfügt über einen Zeilen Header, der einen Auswahl Indikator für die aktuelle Zeile enthält.  
  
- Hat ein Auswahl Rechteck in der ersten Zelle.  
  
- Enthält Spalten, deren Größe automatisch geändert werden kann, wenn der Benutzer auf die Spalten unter Teiler doppelklickt.  
  
- Unterstützt automatisch visuelle Stile unter Windows XP und der Windows Server 2003-Familie, wenn die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>-Methode von der `Main`-Methode der Anwendung aufgerufen wird.  
  
 Außerdem kann der Inhalt eines <xref:System.Windows.Forms.DataGridView> Steuer Elements standardmäßig bearbeitet werden:  
  
- Wenn der Benutzer auf F2 in einer Zelle doppelklickt oder diese drückt, versetzt das Steuerelement die Zelle automatisch in den Bearbeitungsmodus und aktualisiert den Inhalt der Zelle als Benutzer.  
  
- Wenn der Benutzer einen Bildlauf zum Ende des Rasters durchführt, wird dem Benutzer angezeigt, dass eine Zeile zum Hinzufügen neuer Datensätze vorhanden ist. Wenn der Benutzer auf diese Zeile klickt, wird dem <xref:System.Windows.Forms.DataGridView>-Steuerelement eine neue Zeile mit Standardwerten hinzugefügt. Wenn der Benutzer ESC drückt, verschwindet diese neue Zeile.  
  
- Wenn der Benutzer auf einen Zeilen Header klickt, wird die gesamte Zeile ausgewählt.  
  
 Wenn Sie ein <xref:System.Windows.Forms.DataGridView>-Steuerelement an eine Datenquelle binden, indem Sie dessen <xref:System.Windows.Forms.DataGridView.DataSource%2A>-Eigenschaft festlegen, wird das-Steuerelement:  
  
- Verwendet automatisch die Namen der Datenquellen Spalten als Spaltenheader Text.  
  
- Wird mit dem Inhalt der Datenquelle aufgefüllt. <xref:System.Windows.Forms.DataGridView> Spalten werden für jede Spalte in der Datenquelle automatisch erstellt.  
  
- Erstellt eine Zeile für jede sichtbare Zeile in der Tabelle.  
  
- Sortiert die Zeilen automatisch basierend auf den zugrunde liegenden Daten, wenn der Benutzer auf einen Spaltenheader klickt.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- [DataGridView-Steuerelement](datagridview-control-windows-forms.md)
