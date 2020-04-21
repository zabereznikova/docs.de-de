---
title: Verbesserungen der Barrierefreiheit von Windows Forms
description: Erfahren Sie mehr darüber, wie .NET Core Windows Forms versucht, die Barrierefreiheit im Vergleich zu .NET Framework Windows Forms zu verbessern.
ms.date: 04/20/2020
helpviewer_keywords:
- Windows Forms accessibility
- accessibility
author: M-Lipin
ms.openlocfilehash: 30eb8b3bd0aaf646ea23f4f036e822f9bba78dc4
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739763"
---
# <a name="accessibility-improvements-in-windows-forms-controls-for-net-core-30"></a>Verbesserungen der Barrierefreiheit in Windows Forms-Steuerelementen für .NET Core 3.0

Windows Forms verbessert weiterhin die Funktionsweise mit Eingabehilfen, um Windows Forms-Kunden besser zu unterstützen. Diese Verbesserungen umfassen folgende Änderungen:

- Änderungen in verschiedenen Bereichen der Interaktion mit Zugriffsclientanwendungen, einschließlich Sprachausgabe.
- Änderungen an der Hierarchie der Barrierefreiheit (Verbesserung der Navigation durch die Benutzeroberflächenautomatisierungsstruktur)
- Änderungen in der Tastaturnavigation.

> [!IMPORTANT]
> Barrierefreiheitsänderungen, die in .NET Framework 4.7.1 und .NET Framework 4.8 vorgenommen wurden, sind in .NET Core 3.0 und höher enthalten und standardmäßig aktiviert. Die .NET Framework unterstütztKompatibilitäts-Switches, die es Anwendungen ermöglichten, das neue Eingabehilfenverhalten zu deaktivieren. Andererseits unterstützt .NET Core diese Einstellungen nicht und erlaubt es Anwendungen nicht, sich vom Eingabefähigkeitsverhalten abzumelden.
  
Ab .NET Core 3.0 profitieren Windows Forms-Anwendungen von allen neuen Eingabehilfen (in .NET Framework 4.7.1 - 4.8) ohne zusätzliche Konfiguration.

## <a name="listbox-accessibility-support"></a>ListBox Barrierefreiheitunterstützung

Die folgenden Änderungen <xref:System.Windows.Forms.ListBox> gelten für das Steuerelement:

- Unterstützte für die `ListBox` Benutzeroberflächenautomatisierung für die Steuerung.
- Verbesserte `ListBox` Barrierefreiheitsunterstützung <xref:System.Windows.Automation.ScrollItemPattern> durch `ListBox` Hinzufügen der Elemente und Durch die Verbesserung der Eingabehilfen- und -behandlung und Der Sprachausgabenavigation durch die Elemente (die Navigation mit der Sperre ist nicht korrekt und wirft die Navigation nicht unbeabsichtigt außerhalb des Steuerelements).

## <a name="checkedlistbox-accessibility-support"></a>CheckedListBox Barrierefreiheit unterstützung

Die folgenden Änderungen <xref:System.Windows.Forms.CheckedListBox> gelten für das Steuerelement:

- Korrigierte `CheckedListBox` Grenzen, die von Barrierefreiheitseigenschaften für Einträge bereitgestellt werden.
- Verbesserte `ListBox` Gesamt- und `CheckedListBox` Barrierefreiheit: korrigierte Eigenschaftswerte und Ereignismodell.

## <a name="combobox-accessibility-support"></a>ComboBox Barrierefreiheit unterstützung

Die folgenden Änderungen <xref:System.Windows.Forms.ComboBox> gelten für das Steuerelement:

- Der Vorgang des `ComboBox` Abrufens von Zugriffsobjekten für Elemente wurde aktualisiert, um das Generieren von IDs <xref:System.Object.GetHashCode%2A> für Elemente zu ermöglichen, anstatt Hashcodes von Elementen abzubekommen, was für den Fall, dass die Funktion überschrieben wird, möglicherweise unsicher ist.

## <a name="datagridview-accessibility-support"></a>DataGridView Barrierefreiheitsunterstützung

Die folgenden Änderungen <xref:System.Windows.Forms.DataGridView> gelten für das Steuerelement:

- Korrigiert `DataGridView.Bounds` durch Barrierefreiheitseigenschaften für Spalten, Zeilen, Zellen und entsprechende Header, verbesserte Leistung bei der Berechnung des umgebenden Rechtecks. Alle Barrierefreiheitsgrenzen werden unter Berücksichtigung der Grenzen des gesamten Steuerelements zusammen mit seinem Ansichtsfenster korrekt dargestellt.
- Korrigierter `Value.IsReadOnly` Eigenschaftswert für barrierefreie Clientanwendungen. Die Eigenschaft zeigt `IsReadOnly` nun den korrekten Status für Zellen an.
- Das Problem <xref:System.Windows.Forms.DataGridView.CellParsing> mit der Ereigniserhöhung für die erste Zelländerung wurde behoben. Der Zellenwert kann ohne Probleme `DataGridView` geändert werden, einschließlich der ersten Steuerungsinteraktion.
- Verbesserter `DataGridView` Hintergrundfarbkontrast bei Verwendung von Windows High Contrast-Designs. Die `DataGridView` Standardfarbe für die Rückseite wurde geändert, wenn die Designs HC 1, HC2 und HC Black verwendet wurden.

## <a name="propertygrid-accessibility-support"></a>PropertyGrid Barrierefreiheitsunterstützung

Die folgenden Änderungen <xref:System.Windows.Forms.PropertyGrid> gelten für das Steuerelement:

- Korrigiert `PropertyGrid.Bounds` durch Barrierefreiheitseigenschaften für Rastereinträge, verbesserte Leistung bei der Berechnung von umgebenden Rechtecken. Vorerst werden alle Barrierefreiheitsgrenzen unter Berücksichtigung der Grenzen des gesamten Steuerelements zusammen mit seinem Ansichtsfenster korrekt dargestellt.
- Barrierefreie Namen und Beschreibungen von Untersteuerelementen wurden korrigiert, um keine Steuerelementtypnamen einzuschließen und doppelte Ankündigungen für Steuerelementtypnamen zu vermeiden.

## <a name="toolstrip-accessibility-support"></a>ToolStrip Barrierefreiheit unterstützung

Die folgenden Änderungen <xref:System.Windows.Forms.ToolStrip> gelten für das Steuerelement:

- Verbesserte Navigation `ToolStrip` `MenuStrip`durch `StatusStrip` , und Elemente. `ToolStrip` Korrigierte `MenuStrip` und Shift-Tab-Navigation, Back-Looping der Menüelemente, wenn Shift-Tab-Up-Pfeil gedrückt wird, die zum unteren Menüelement navigiert.
- Verbesserte `MenuStrip` zugängliche Navigation, korrigierte Menü zugänglichE Steuerelementtypen für Untermenüs, um Untermenüs vom Typ 'Menü' anstelle von 'MenuItem' zu machen.

## <a name="printpreviewcontrol-and-printpreviewdialog-accessibility-support"></a>Unterstützung für PrintPreviewControl und PrintPreviewDialog Barrierefreiheit

Die folgenden Änderungen gelten für die Drucksteuerelemente:

- Verbesserte zugängliche Navigation (einschließlich Sprachausgabenavigation) durch Menüelemente.
- Verbesserte High-Kontrast-Themen unterstützen und das Steuerelement-Element kontrastierter.

## <a name="stringcollectioneditor-accessibility-support"></a>Unterstützung für Die Barrierefreiheit von StringCollectionEditor

Windows Forms Designer verwendet jetzt den Zeichenfolgensammlungs-Editor mit verbesserter Barrierefreiheitsunterstützung.

## <a name="monthcalendar-accessibility-support-available-in-net-core-31"></a>MonthCalendar Barrierefreiheitsunterstützung (verfügbar in .NET Core 3.1)

Die folgenden Änderungen <xref:System.Windows.Forms.MonthCalendar> gelten für das Steuerelement:

- Ui Automation Server-Anbieter `MonthCalendar` hinzugefügt, um zu steuern, hinzugefügt UI Automation Grid Muster und Tabelle Muster-Anbieter.
- Geänderter Steuerelementtyp für die _geänderte Tabelle_ für _kalenderzugänglichen_ Steuerelementtyp, `MonthCalendar` `MonthCalendar` außer in dem Fall, wenn das Steuerelement über ein vorangehendes Beschriftungssteuerelement verfügt, das den Namen des Steuerelements definiert, wird der zugriffzugängliche Steuerelementtyp in _Tabelle_.
- Verbesserte Ankündigung des `MonthCalendar` ausgewählten Datums für die Steuerung.
- Verbesserte `MonthCalendar` Steuerungsunterstützung für Bildschirmleseprogramme und andere Eingabehilfen. In diesem Moment können Benutzer durch die Steuerelemente navigieren und mit diesen Elementen über nur Tastatureingaben interagieren. Verwenden Sie mit der Sprachausgabe CAPS + Pfeiltasten die Navigation durch die Steuerelemente und CAPS + Enter, um die Elementstandardaktion aufzurufen.
- Verbesserte Pfeiltastennavigation `MonthCalendar` über untergeordnete Elemente mit einem Fokusrechteck: blaues Fokusrechteck für die Sprachausgabe.
- Verbesserte Zugänglichkeit für Treffertestaktionen für `MonthCalendar` `MonthCalendar` Steuerelemente, um das Zugriff auf untergeordnete Elemente durch bereitgestellte Koordinaten zu ermöglichen.

## <a name="tooltips-accessibility-available-in-net-core-31"></a>ToolTips-Barrierefreiheit (verfügbar in .NET Core 3.1)

- Es wurde die Möglichkeit hinzugefügt, einen QuickInfo-Text durch Bildschirmsprachausgabeanwendungen wie NVDA und Sprachausgabe anzukündigen. Die Bildschirmsprachausgabeanwendung kann jetzt den Text der Tastatur- oder Maus-Tooltip eines beliebigen Windows Forms-Steuerelements ankündigen, das für die Anzeige von QuickInfos konfiguriert wurde.

## <a name="ui-automation-support-for-datagridview-propertygrid-listbox-combobox-toolstrip-and-other-controls"></a>Unterstützung der Benutzeroberflächenautomatisierung für DataGridView, PropertyGrid, ListBox, ComboBox, ToolStrip und andere Steuerelemente

Die Unterstützung für die Benutzeroberflächenautomatisierung ist für Steuerelemente zur Laufzeit aktiviert, wird aber während der Entwurfszeit nicht verwendet. Einen Überblick über die Benutzeroberflächenautomatisierung finden Sie unter [Benutzeroberflächenautomatisierung: Übersicht](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).

## <a name="see-also"></a>Siehe auch

- [Best Practices für Barrierefreiheit](../ui-automation/accessibility-best-practices.md).
