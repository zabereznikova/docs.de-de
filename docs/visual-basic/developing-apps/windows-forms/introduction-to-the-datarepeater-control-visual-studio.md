---
title: "Einführung in das DataRepeater-Steuerelement (Visual Studio) | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- repeating data
- DataRepeater, overview
- DataRepeater
ms.assetid: 78a52a1d-65f0-4ecb-97ff-53bc114300c5
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 86078426494caabefc6bbfb036037007e830e1cb
ms.lasthandoff: 03/13/2017

---
# <a name="introduction-to-the-datarepeater-control-visual-studio"></a>Einführung in das DataRepeater-Steuerelement (Visual Studio)
Die Visual Basic Power Packs <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelement ist einem bildlauffähigen Container für Steuerelemente zur Anzeige von wiederholt, z. B. Datenzeilen in einer Datenbanktabelle.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Hiermit können als Alternative zu den <xref:System.Windows.Forms.DataGridView>müssen Sie mehr Kontrolle über das Layout der Daten steuern.</xref:System.Windows.Forms.DataGridView> Die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>"wiederholt" eine Gruppe von verwandten Steuerelementen durch Erstellen mehrerer Instanzen in einer Bildlaufansicht.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Dies ermöglicht Benutzern, mehrere Datensätze gleichzeitig anzuzeigen.  
  
## <a name="overview"></a>Übersicht  
 Zur Entwurfszeit die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement besteht aus zwei Abschnitten.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Der äußere Bereich ist der *Viewport*, in die fortlaufenden Daten zur Laufzeit angezeigt werden soll. Der innere (oben) Bereich als das *Elementvorlage*, ist, in dem Sie Steuerelemente positionieren, die zur Laufzeit in der Regel ein Steuerelement für jedes Feld in der Datenquelle wiederholt wird. Sind die Eigenschaften und Steuerelemente in der Elementvorlage gekapselt die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>Eigenschaft.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>  
  
 Zur Laufzeit die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>kopiert eine virtuelle <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>-Objekt, das verwendet wird, um die Daten anzuzeigen, wenn jeder Datensatz ein Bildlauf durchgeführt wird.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> Sie können anpassen, die Anzeige der einzelnen Datensätze in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>Ereignis, z. B. ein Feld basierend auf dem enthaltenen Wert hervorheben.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> Weitere Informationen finden Sie unter [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Die häufigste Verwendung für ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement wird zum Anzeigen von Daten aus einer Datenbanktabelle oder anderer gebundener Datenquellen.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Zusätzlich zu [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] Datenobjekte, die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement binden kann, für jede Klasse, die implementiert die <xref:System.Collections.IList>-Schnittstelle (einschließlich Arrays), jede Klasse, implementiert der <xref:System.ComponentModel.IListSource>Schnittstelle, Klasse, die implementiert die <xref:System.ComponentModel.IBindingList>-Schnittstelle oder eine Klasse, die implementiert die <xref:System.ComponentModel.IBindingListView>Schnittstelle.</xref:System.ComponentModel.IBindingListView> </xref:System.ComponentModel.IBindingList> </xref:System.ComponentModel.IListSource> </xref:System.Collections.IList> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
### <a name="data-binding"></a>Datenbindung  
 In der Regel erreichen Sie Binden von Daten durch Ziehen von Feldern aus der **Datenquellen** auf der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
 Bei der Arbeit mit großen Datenmengen lassen sich die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>-Eigenschaft `True` um eine Teilmenge der verfügbaren Daten anzuzeigen.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> Virtueller Modus erfordert die Implementierung eines Daten-Caches aus dem die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>aufgefüllt wird, und Sie müssen alle Interaktionen mit dem Datencache zur Laufzeit steuern.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Weitere Informationen finden Sie unter [Virtueller Modus im DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
 Sie können auch anzeigen nicht gebundener Steuerelemente in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Beispielsweise können Sie ein Bild, das wiederholt wird für jedes Element anzeigen. Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen nicht gebundener Steuerelemente in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
### <a name="events"></a>Ereignisse  
 Die wichtigsten Ereignisse für das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement werden die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>-Ereignis, das ausgelöst wird, wenn neue Elemente ein Bildlauf durchgeführt werden, und die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>-Ereignis, das ausgelöst wird, wenn ein Element ausgewählt ist.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Sie können die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>Ereignis, um die Darstellung des Elements ändern.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> Beispielsweise können Sie negative Werte hervorheben. Verwenden der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>Ereignis, um die Werte von Steuerelementen zuzugreifen, wenn ein Element ausgewählt ist.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement macht alle Ereignisse im Code-Editor verfügbar.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Einige Ereignisse sollten jedoch nicht verwendet werden. Tastatur- und Mausereignisse wie z. B. `KeyDown`, `Click`, und `MouseDown` wird nicht zur Laufzeit ausgelöst werden, da die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement selbst nicht den Fokus hat.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>keine Ereignisse zur Entwurfszeit da es nur zur Laufzeit erstellt wird.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> Wenn Sie Tastatur-und Mausereignisse verarbeiten möchten, können Sie hinzufügen eine <xref:System.Windows.Forms.Panel>die Steuerung an die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>zur Entwurfszeit und verarbeiten dann die Ereignisse für das <xref:System.Windows.Forms.Panel>.</xref:System.Windows.Forms.Panel> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> </xref:System.Windows.Forms.Panel> Weitere Informationen finden Sie unter [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md).  
  
### <a name="customizations"></a>Anpassungen  
 Es gibt viele Methoden zum Anpassen der Darstellung und Verhalten von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>steuern, sowohl zur Laufzeit und Entwurfszeit.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Eigenschaften können festgelegt werden, um Farben ändern, ausblenden oder die Elementheader ändern, ändern Sie die Ausrichtung von vertikal in horizontal und vieles mehr. Weitere Informationen finden Sie unter [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md), [Gewusst wie: Anzeigen von Elementheadern in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md), und [Gewusst wie: Ändern des Layouts eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md).  
  
 Beachten Sie, dass einige Eigenschaften, die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>selbst steuern können, während andere nur für den <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> gelten gelten</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Stellen Sie sicher, dass der richtige Bereich des Steuerelements ausgewählt werden, bevor Sie Eigenschaften festlegen. Weitere Informationen finden Sie unter [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Weitere Anpassungsoptionen umfassen steuern, ob hinzufügen oder Löschen von Datensätzen, Hinzufügen von Suchfunktionen und Anzeigen von verknüpften Daten in einem Master- und Format. Weitere Informationen finden Sie unter [wie: Deaktivieren hinzufügen und Löschen von DataRepeater-Elementen](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md), [Gewusst wie: Suchen von Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md), und [Gewusst wie: Erstellen eines Master/Detail-Formulars durch mit zwei DataRepeater-Steuerelementen (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/datarepeater-control-visual-studio.md)   
 [Exemplarische Vorgehensweise: Anzeigen von Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio.md)   
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
