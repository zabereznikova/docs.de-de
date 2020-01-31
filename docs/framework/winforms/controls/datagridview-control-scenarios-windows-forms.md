---
title: Szenarios für das DataGridView-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
ms.openlocfilehash: 160d967c6445fb753cb6c73babfb02a734a07e28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742460"
---
# <a name="datagridview-control-scenarios-windows-forms"></a>Szenarien für das DataGridView-Steuerelement (Windows Forms)
Mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement können Sie tabellarische Daten aus einer Vielzahl von Datenquellen anzeigen. Für einfache Verwendungszwecke können Sie eine <xref:System.Windows.Forms.DataGridView> manuell auffüllen und die Daten direkt über das-Steuerelement bearbeiten. In der Regel speichern Sie die Daten jedoch in einer externen Datenquelle und binden das Steuerelement über eine <xref:System.Windows.Forms.BindingSource> Komponente an die Datenquelle.  
  
 In diesem Thema werden einige gängige Szenarios beschrieben, in denen das <xref:System.Windows.Forms.DataGridView>-Steuerelement enthalten ist.  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a>Szenario 1: Anzeigen kleiner Datenmengen  
 Sie müssen Ihre Daten nicht in einer externen Datenquelle speichern, um Sie im <xref:System.Windows.Forms.DataGridView>-Steuerelement anzuzeigen. Wenn Sie mit einer kleinen Menge von Daten arbeiten, können Sie das Steuerelement selbst auffüllen und die Daten über das Steuerelement bearbeiten. Dies wird als *ungebundener Modus*bezeichnet. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines ungebundenen Windows Forms DataGridView-Steuer](how-to-create-an-unbound-windows-forms-datagridview-control.md)Elements.  
  
### <a name="scenario-key-points"></a>Szenariohauptpunkte  
  
- Im ungebundenen Modus füllen Sie das Steuerelement manuell auf.  
  
- Der ungebundene Modus eignet sich besonders für kleine Mengen Schreib geschützter Daten.  
  
- Der ungebundene Modus eignet sich auch für Tabellen ähnlich oder dünn aufgefüllte Tabellen.  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a>Szenario 2: anzeigen und Aktualisieren von Daten, die in einer externen Datenquelle gespeichert sind  
 Sie können das <xref:System.Windows.Forms.DataGridView>-Steuerelement als Benutzeroberfläche verwenden, über die Benutzer auf Daten zugreifen können, die in einer Datenquelle, z. b. einer Datenbanktabelle oder einer Sammlung von Geschäftsobjekten, gespeichert sind. Weitere Informationen finden Sie unter Gewusst [wie: Binden von Daten an das Windows Forms DataGridView-Steuer](how-to-bind-data-to-the-windows-forms-datagridview-control.md)Element.  
  
### <a name="scenario-key-points"></a>Szenariohauptpunkte  
  
- Der gebundene Modus ermöglicht Ihnen das Herstellen einer Verbindung mit einer Datenquelle, das automatische Generieren von Spalten basierend auf den Datenquellen Eigenschaften oder Daten Bank Spalten und das automatische Auffüllen des-Steuer Elements.  
  
- Der gebundene Modus eignet sich für eine starke Interaktion zwischen Benutzern und Daten. Daten können für die Anzeige formatiert werden, und benutzerdefinierte Daten können in das von der Datenquelle erwartete Format analysiert werden. Formatierungs Fehler und Daten Bank Einschränkungs Fehler können erkannt werden, damit Benutzer gewarnt und fehlerhafte Zellen korrigiert werden können.  
  
- Zusätzliche Funktionen, wie z. b. Spalten Sortierung, Einfrieren und Neusortieren, ermöglichen Benutzern das Anzeigen von Daten auf die für den Workflow am besten geeignete Weise.  
  
- Die Unterstützung der Zwischenablage ermöglicht Benutzern das Kopieren von Daten aus Ihrer Anwendung in andere Anwendungen.  
  
## <a name="scenario-3-advanced-data"></a>Szenario 3: erweiterte Daten  
 Wenn Sie besondere Anforderungen haben, die das Standard-Daten Bindungs Modell nicht adressiert, können Sie die Interaktion zwischen dem Steuerelement und Ihren Daten durch Implementieren des *virtuellen Modus*verwalten. Das Implementieren des virtuellen Modus bedeutet, dass ein oder mehrere Ereignishandler implementiert werden, die es dem Steuerelement ermöglichen, Informationen zu Zellen anzufordern, wenn die Informationen benötigt werden.  
  
 Wenn Sie z. b. mit großen Datenmengen arbeiten, möchten Sie möglicherweise den virtuellen Modus implementieren, um eine optimale Effizienz zu gewährleisten. Der virtuelle Modus ist auch nützlich, um die Werte von ungebundenen Spalten zu verwalten, die Sie zusammen mit Spalten anzeigen, die aus einer anderen Datenquelle abgerufen wurden.  
  
 Weitere Informationen zum virtuellen Modus finden Sie unter Exemplarische Vorgehensweise [: Implementieren des virtuellen Modus im Windows Forms DataGridView-Steuer](implementing-virtual-mode-wf-datagridview-control.md)Element.  
  
### <a name="scenario-key-points"></a>Szenariohauptpunkte  
  
- Der virtuelle Modus eignet sich zum Anzeigen sehr großer Datenmengen, wenn Sie die Leistung optimieren müssen.  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a>Szenario 4: Automatisches Ändern der Größe von Zeilen und Spalten  
 Wenn Sie Daten anzeigen, die regelmäßig aktualisiert werden, können Sie die Größe von Zeilen und Spalten automatisch ändern, um sicherzustellen, dass der gesamte Inhalt sichtbar ist. Das <xref:System.Windows.Forms.DataGridView>-Steuerelement bietet verschiedene Optionen zum Aktivieren oder Deaktivieren der manuellen Größenänderung, zum programmgesteuerten Ändern der Größe zu bestimmten Zeitpunkten oder zum automatischen Ändern der Größe, wenn sich der Inhalt ändert. Weitere Informationen finden Sie unter [Größen Anpassungsoptionen im Windows Forms DataGridView-Steuer](sizing-options-in-the-windows-forms-datagridview-control.md)Element.  
  
### <a name="scenario-key-points"></a>Szenariohauptpunkte  
  
- Durch die manuelle Größenänderung können Benutzer Zellen Höhen und breiten anpassen.  
  
- Die automatische Größenänderung ermöglicht es Ihnen, Zellgrößen beizubehalten, damit Zellen Inhalt nie abgeschnitten wird.  
  
- Mithilfe der programmatischen Größenänderung können Sie die Größe der Zellen zu bestimmten Zeitpunkten ändern, um die Leistungseinbußen bei der kontinuierlichen automatischen Größenänderung zu vermeiden.  
  
## <a name="scenario-5-simple-customization"></a>Szenario 5: einfache Anpassung  
 Das <xref:System.Windows.Forms.DataGridView>-Steuerelement bietet viele Möglichkeiten, seine grundlegende Darstellung und Verhalten zu ändern. Weitere Informationen finden Sie unter [Zellen Stile im Windows Forms DataGridView-Steuer](cell-styles-in-the-windows-forms-datagridview-control.md)Element.  
  
### <a name="scenario-key-points"></a>Szenariohauptpunkte  
  
- mit <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekten können Sie Farb-, Schriftart-, Formatierungs-und Positionsinformationen auf mehreren Ebenen und für einzelne Elemente des Steuer Elements bereitstellen.  
  
- Zell Stile können von mehreren Elementen geschichtet und gemeinsam genutzt werden, sodass Sie Code wieder verwenden können.  
  
## <a name="scenario-6-advanced-customization"></a>Szenario 6: Erweiterte Anpassung  
 Das <xref:System.Windows.Forms.DataGridView>-Steuerelement bietet viele Möglichkeiten, seine Darstellung und das Verhalten anzupassen.  
  
### <a name="scenario-key-points"></a>Szenariohauptpunkte  
  
- Sie können Ihren eigenen zellzeichnungs Code bereitstellen. Weitere Informationen finden Sie unter Gewusst [wie: Anpassen der Darstellung von Zellen im Windows Forms DataGridView-Steuer](customize-the-appearance-of-cells-in-the-datagrid.md)Element.  
  
- Sie können Ihr eigenes Zeilenzeichen bereitstellen. Dies ist beispielsweise hilfreich, um Zeilen mit Inhalten zu erstellen, die sich über mehrere Spalten erstrecken. Weitere Informationen finden Sie unter Gewusst [wie: Anpassen der Darstellung von Zeilen im Windows Forms DataGridView-Steuer](customize-the-appearance-of-rows-in-the-datagrid.md)Element.  
  
- Sie können Ihre eigenen Zell-und Spalten Klassen implementieren, um die Zellen Darstellung anzupassen. Weitere Informationen finden Sie unter Gewusst [wie: Anpassen von Zellen und Spalten im Windows Forms DataGridView-Steuerelement durch Erweiterung ihres Verhaltens und ihrer](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)Darstellung.  
  
- Sie können Ihre eigenen Zell-und Spalten Klassen implementieren, um die Steuerelemente zu hosten, die von den integrierten Spaltentypen bereitgestellt werden. Weitere Informationen finden Sie unter Gewusst [wie: Hosten von Steuerelementen in Windows Forms DataGridView-Zellen](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- [Übersicht über das DataGridView-Steuerelement](datagridview-control-overview-windows-forms.md)
