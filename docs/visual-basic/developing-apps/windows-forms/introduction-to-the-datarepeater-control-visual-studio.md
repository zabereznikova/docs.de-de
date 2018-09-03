---
title: Einführung in das DataRepeater-Steuerelement (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- repeating data
- DataRepeater, overview
- DataRepeater
ms.assetid: 78a52a1d-65f0-4ecb-97ff-53bc114300c5
ms.openlocfilehash: fc0cf9c358faf3e738eb3b24ec61577b88dbce4a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485715"
---
# <a name="introduction-to-the-datarepeater-control-visual-studio"></a>Einführung in das DataRepeater-Steuerelement (Visual Studio)
Das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement aus dem Visual Basic Power Packs ist ein scrollfähiger Container für Steuerelemente, die sich wiederholende Daten anzeigen, z. B. Zeilen in einer Datenbanktabelle. Es kann als Alternative zum <xref:System.Windows.Forms.DataGridView> -Steuerelement verwendet werden, wenn Sie mehr Kontrolle über das Layout der Daten benötigen. Die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> "wiederholt" eine Gruppe von verwandten Steuerelementen durch Erstellen mehrerer Instanzen in einer fortlaufenden Ansicht. Dadurch können Benutzer mehrere Einträge gleichzeitig anzuzeigen.  
  
## <a name="overview"></a>Übersicht  
 Zur Entwurfszeit die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement besteht aus zwei Abschnitten. Der äußeren Bereich ist die *Viewport*, in die fortlaufenden Daten zur Laufzeit angezeigt werden soll. Der innere (oben) Bereich als die *Elementvorlage*, ist, in dem Sie Steuerelemente positionieren, der zur Laufzeit in der Regel ein Steuerelement für jedes Feld in der Datenquelle wiederholt wird. Die Eigenschaften und Steuerelemente in der Elementvorlage in gekapselt werden die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> Eigenschaft.  
  
 Zur Laufzeit die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> wird in einem virtuellen kopiert <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> -Objekt, das verwendet wird, um die Daten anzuzeigen, wenn jeder Datensatz in die Ansicht gescrollt wird. Sie können anpassen, dass die Anzeige der einzelnen Datensätze in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> -Ereignis, z. B. Hervorheben eines Felds basierend auf den Wert an, die sie enthält. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Die häufigste Verwendung für eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement ist, um Daten aus einer Datenbanktabelle oder anderen gebundenen Datenquelle anzuzeigen. Zusätzlich zu [!INCLUDE[vstecado](~/includes/vstecado-md.md)] Datenobjekte, die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement kann an jede Klasse, die implementiert binden die <xref:System.Collections.IList> -Schnittstelle (einschließlich Arrays), jede Klasse, die implementiert die <xref:System.ComponentModel.IListSource> Schnittstelle, die jede Klasse, die implementiert die <xref:System.ComponentModel.IBindingList> Schnittstelle oder in einer Klasse, die implementiert die <xref:System.ComponentModel.IBindingListView> Schnittstelle.  
  
### <a name="data-binding"></a>Datenbindung  
 In der Regel erreichen Sie die Datenbindung durch Ziehen von Feldern aus der **Datenquellen** Fenster auf die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
 Bei der Arbeit mit großen Datenmengen können Sie festlegen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> Eigenschaft `True` um eine Teilmenge der verfügbaren Daten anzuzeigen. Virtueller Modus erfordert die Implementierung einer Zwischenspeicherung von Daten aus dem die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> aufgefüllt wird, und Sie müssen alle Interaktionen mit dem Datencache zur Laufzeit steuern. Weitere Informationen finden Sie unter [Virtueller Modus im DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
 Sie können auch anzeigen nicht gebundener Steuerelemente in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. Beispielsweise können Sie ein Bild, das wiederholt wird für jedes Element anzeigen. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen nicht gebundener Steuerelemente in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
### <a name="events"></a>Ereignisse  
 Die wichtigsten Ereignisse für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> sind die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> -Ereignis, das ausgelöst wird, wenn neue Elemente in die Ansicht gescrollt werden, und die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> -Ereignis, das ausgelöst wird, wenn ein Element ausgewählt ist. Sie können die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> Ereignis, um die Darstellung des Elements zu ändern. Beispielsweise können Sie negative Werte hervorheben. Verwenden der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> Ereignis, um die Werte von Steuerelementen zugreifen, wenn ein Element ausgewählt ist.  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement macht alle Ereignisse im Code-Editor verfügbar. Einige der Ereignisse sollte jedoch nicht verwendet werden. Tastatur- und Mausereignisse wie z. B. `KeyDown`, `Click`, und `MouseDown` wird nicht zur Laufzeit ausgelöst werden, da die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement selbst nie den Fokus besitzt.  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> macht nicht zur Entwurfszeit Ereignisse verfügbar, da es nur zur Laufzeit erstellt wird. Wenn Sie eine Tastatur und Maus-Ereignisse behandeln möchten, können Sie hinzufügen eine <xref:System.Windows.Forms.Panel> die Steuerung an die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> am Entwurfszeit- und behandeln Sie anschließend auf die Ereignisse für die <xref:System.Windows.Forms.Panel>. Weitere Informationen finden Sie unter [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md).  
  
### <a name="customizations"></a>Anpassungen  
 Es gibt viele Möglichkeiten zum Anpassen der Darstellung und Verhalten von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> steuern, die zur Laufzeit und Entwurfszeit. Eigenschaften können festgelegt werden, um Farben ändern, ausblenden oder ändern die Elementheader, ändern Sie die Ausrichtung von vertikal in horizontal und vieles mehr. Weitere Informationen finden Sie unter [wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md), [Vorgehensweise: Anzeigen von Elementheadern in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md), und [Vorgehensweise: Ändern des Layouts einer DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md).  
  
 Beachten Sie, die für einige Eigenschaften gelten die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> selbst steuern können, während andere Themen beziehen sich nur auf die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>. Stellen Sie sicher, dass Sie den richtigen Abschnitt des Steuerelements ausgewählt werden, damit Sie Eigenschaften festlegen. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Andere Anpassungen enthalten, steuern die Möglichkeit zum Hinzufügen oder Löschen von Datensätzen, Hinzufügen von Suchfunktionen und Anzeigen von verknüpften Daten in einem Master- und Detailtabelle-Format. Weitere Informationen finden Sie unter [wie: Hinzufügen zu deaktivieren und Löschen von DataRepeater-Elementen](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md), [wie: Suchen von Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md), und [wie: Erstellen Sie eine Master-/Detailformulars durch zwei verwenden DataRepeater-Steuerelementen (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md).  
  
## <a name="see-also"></a>Siehe auch  
 [DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/datarepeater-control-visual-studio.md)  
 [Exemplarische Vorgehensweise: Anzeigen von Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio.md)  
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
