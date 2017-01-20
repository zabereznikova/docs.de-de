---
title: "Introduction to the DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "repeating data"
  - "DataRepeater, overview"
  - "DataRepeater"
ms.assetid: 78a52a1d-65f0-4ecb-97ff-53bc114300c5
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Introduction to the DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement von Visual Basic Power Packs ist ein bildlauffähiger Container für Steuerelemente, die wiederkehrende Daten anzeigen, z. B. Zeilen in einer Datenbanktabelle.  Dieses kann als Alternative zum <xref:System.Windows.Forms.DataGridView>\-Steuerelement verwendet werden, wenn Sie eine genauere Steuerung des Datenlayouts benötigen.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> "wiederholt" eine Gruppe zusammengehöriger Steuerelemente, indem mehrere Instanzen in einer Bildlaufansicht erstellt werden.  Benutzer können so mehrere Datensätze gleichzeitig anzeigen.  
  
## Übersicht  
 Zur Entwurfszeit besteht das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement aus zwei Bereichen.  Der äußere Bereich ist der *Viewport*, in dem die Bildlaufdaten zur Laufzeit angezeigt werden.  Der innere bzw. obere Bereich ist die *Elementvorlage*. Hier werden Steuerelemente positioniert, die zur Laufzeit wiederholt werden \(in der Regel ein Steuerelement für jedes Feld in der Datenquelle\).  Die Eigenschaften und Steuerelemente in der Elementvorlage werden in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>\-Eigenschaft gekapselt.  
  
 Zur Laufzeit wird <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> in ein virtuelles <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>\-Objekt kopiert, das zum Anzeigen der Daten verwendet wird, wenn die einzelnen Datensätze per Bildlauf angezeigt werden.  Sie können die Darstellung einzelner Datensätze im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>\-Ereignis anpassen, z. B. indem Sie ein Feld basierend auf dem enthaltenen Wert hervorheben.  Weitere Informationen hierzu finden Sie unter [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement wird häufig zur Anzeige von Daten aus einer Datenbanktabelle oder anderer gebundener Datenquellen eingesetzt.  Das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement kann nicht nur an [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)]\-Datenobjekte, sondern auch an eine beliebige Klasse gebunden werden, die die <xref:System.Collections.IList>\-Schnittstelle \(einschließlich Arrays\), die <xref:System.ComponentModel.IListSource>\-Schnittstelle, die <xref:System.ComponentModel.IBindingList>\-Schnittstelle oder die <xref:System.ComponentModel.IBindingListView>\-Schnittstelle implementiert.  
  
### Datenbindung  
 Zur Datenbindung ziehen Sie in der Regel Felder aus dem Fenster **Datenquellen** auf das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement.  Weitere Informationen hierzu finden Sie unter [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
 Bei großen Datenmengen können Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>\-Eigenschaft auf `True` festlegen, um eine Teilmenge der verfügbaren Daten anzuzeigen.  Für den virtuellen Modus muss ein Datencache implementiert werden, aus dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> aufgefüllt wird. Darüber hinaus müssen Sie alle Interaktionen mit dem Datencache zur Laufzeit überwachen.  Weitere Informationen hierzu finden Sie unter [Virtual Mode in the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
 Sie können auch ungebundene Steuerelemente in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement anzeigen.  Sie können beispielsweise ein Bild anzeigen, das auf jedem Element wiederholt wird.  Weitere Informationen hierzu finden Sie unter [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
### Ereignisse  
 Die wichtigsten Ereignisse für das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement sind das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>\-Ereignis, das beim Anzeigen neuer Elemente ausgelöst wird, und das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>\-Ereignis, das beim Auswählen eines Elements ausgelöst wird.  Mit dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>\-Ereignis können Sie die Darstellung des Elements ändern.  Sie können beispielsweise negative Werte hervorheben.  Verwenden Sie das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>\-Ereignis, um auf die Werte von Steuerelementen zuzugreifen, wenn ein Element ausgewählt ist.  
  
 Das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement stellt alle Standardsteuerelementereignisse im Code\-Editor bereit.  Einige Ereignisse sollten jedoch nicht verwendet werden.  Tastatur\- und Mausereignisse wie `KeyDown`, `Click` und `MouseDown` werden zur Laufzeit nicht ausgelöst, da sich der Fokus niemals direkt auf dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement befindet.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> stellt zur Entwurfszeit keine Ereignisse bereit, da es erst zur Laufzeit erstellt wird.  Wenn Sie Tastatur\- und Mausereignisse verarbeiten möchten, können Sie zur Entwurfszeit ein <xref:System.Windows.Forms.Panel>\-Steuerelement zu <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> hinzufügen und dann die Ereignisse für <xref:System.Windows.Forms.Panel> verarbeiten.  Weitere Informationen hierzu finden Sie unter [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md).  
  
### Anpassungen  
 Das Erscheinungsbild und Verhalten des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements kann sowohl zur Entwurfszeit als auch zur Laufzeit auf vielfältige Weise angepasst werden.  Mithilfe von Eigenschaften können Sie Farben ändern, die Elementheader ausblenden oder bearbeiten, die Ausrichtung von vertikal in horizontal ändern usw.  Weitere Informationen finden Sie unter [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md), [How to: Display Item Headers in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md) und [How to: Change the Layout of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md).  
  
 Beachten Sie, dass sich einige Eigenschaften auf das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement selbst beziehen, wohingegen andere nur für <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> gelten.  Stellen Sie sicher, dass der richtige Bereich des Steuerelements ausgewählt ist, bevor Sie Eigenschaften festlegen.  Weitere Informationen hierzu finden Sie unter [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Sie können weiterhin steuern, ob Datensätze hinzugefügt bzw. gelöscht werden dürfen, Sie können Suchfunktionen hinzufügen, und Sie können zusammengehörige Daten in einem Master\- und Detailformat anzeigen.  Weitere Informationen finden Sie unter [How to: Disable Adding and Deleting DataRepeater Items](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md), [How to: Search Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md) und [How to: Create a Master\/Detail Form by Using Two DataRepeater Controls](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md).  
  
## Siehe auch  
 [DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/datarepeater-control-visual-studio.md)   
 [Exemplarische Vorgehensweise: Anzeigen von Daten in einem DataRepeater\-Steuerelement](../../../visual-basic/developing-apps/windows-forms/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)