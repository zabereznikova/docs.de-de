---
title: "Troubleshooting the DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, troubleshooting"
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Troubleshooting the DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

In diesem Thema sind allgemeine Probleme aufgelistet, die bei der Arbeit mit dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement auftreten können.  
  
## DataRepeater\-Tastaturereignisse und \-Mausereignisse werden nicht ausgelöst  
 Einige <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelementereignisse, z. B. Tastatur\- und Mausereignisse, werden nicht ausgelöst.  Dieser Fehler ist entwurfsbedingt.  Das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement selbst ist ein Container für <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>\-Objekte und es kann zur Laufzeit nicht darauf zugegriffen werden.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> zeigt zur Entwurfszeit keine Ereignisse an.  Daher wird kein Ereignis ausgelöst, wenn Sie auf ein Element klicken oder eine Taste drücken, während auf dem Element der Fokus liegt.  
  
 Eine Ausnahme hierzu besteht, wenn die <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft auf einen hohen Wert festgelegt ist, sodass die Ränder des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements verfügbar sind.  Wenn Sie in diesem Fall auf den verfügbaren Rand klicken, wird ein Mausereignis ausgelöst.  
  
 Sie beheben dieses Problem, indem Sie ein <xref:System.Windows.Forms.Panel>\-Steuerelement dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>\-Bereich des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements und anschließend den Rest des Steuerelement zu <xref:System.Windows.Forms.Panel> hinzufügen.  Danach können Sie Code den Ereignishandlern des <xref:System.Windows.Forms.Panel>\-Steuerelements für Tastatur\- und Mausereignisse hinzufügen.  
  
## Der DataRepeater wird teilweise durch den BindingNavigator verdeckt  
 Wenn Sie zum ersten Mal ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement einem Formular hinzufügen und dann datengebundene Steuerelemente aus dem Fenster **Datenquellen** einfügen, wird das <xref:System.Windows.Forms.BindingNavigator>\-Steuerelement möglicherweise über dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement angezeigt.  Dies ist eine Einschränkung des Fensters **Datenquellen** und entspricht dem Verhalten anderer Steuerelemente, z. B. <xref:System.Windows.Forms.DataGridView>.  
  
 Sie können entweder zur Entwurfszeit das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement unter das <xref:System.Windows.Forms.BindingNavigator>\-Steuerelement verschieben, oder Sie fügen im `Load`\-Ereignishandler ähnlichen Code wie den Folgenden hinzu.  
  
```vb#  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```c#  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## Steuerelemente werden zur Laufzeit nicht ordnungsgemäß angezeigt  
 Einige Steuerelemente in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement werden zur Laufzeit möglicherweise nicht wie erwartet angezeigt.  Beim Klonen von Steuerelementen aus <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> in <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> können nicht immer alle Eigenschaften der einzelnen Steuerelemente ermittelt werden.  Wenn Sie beispielsweise zur Entwurfszeit ein ungebundenes <xref:System.Windows.Forms.ListBox>\-Steuerelement einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement hinzufügen und die zugehörige <xref:System.Windows.Forms.ListBox.Items%2A>\-Auflistung mit einer Liste von Zeichenfolgen füllen, ist <xref:System.Windows.Forms.ListBox> zur Laufzeit leer.  Dies ist darauf zurückzuführen, dass der Klonvorgang die <xref:System.Windows.Forms.ListBox.Items%2A>\-Eigenschaft nicht berücksichtigen kann.  
  
 Sie beheben Probleme wie dieses, indem Sie die fehlenden Eigenschaften im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned>\-Ereignis wiederherstellen, das nach dem standardmäßigen Klonvorgang ausgelöst wird.  Das folgende Beispiel veranschaulicht, wie Sie die <xref:System.Windows.Forms.ListBox.Items%2A>\-Auflistung eines <xref:System.Windows.Forms.ListBox>\-Steuerelements im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned>\-Ereignishandler reparieren.  
  
 [!code-cs[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/troubleshooting-the-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/troubleshooting-the-datarepeater-control-visual-studio_1.vb)]  
  
## Das Auswahlsymbol auf dem Elementheader fehlt  
 Wenn Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>\-Eigenschaft des Elementheaders in ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement ändern, wird das Auswahlsymbol je nach Farbauswahl möglicherweise ausgeblendet.  Auch eine Änderung der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>\-Eigenschaft kann zur Folge haben, dass das Auswahlsymbol nicht mehr sichtbar ist.  
  
 Die Farbe und die Größe des Auswahlsymbols können nicht geändert werden.  
  
-   Wenn Sie <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> auf <xref:System.Drawing.Color.White%2A> festlegen, wird das Auswahlsymbol bei der ersten Auswahl eines Elements nicht angezeigt.  
  
-   Wenn Sie <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> auf <xref:System.Drawing.Color.Black%2A> festlegen, ist das Auswahlsymbol bei Auswahl eines Steuerelements nicht sichtbar. Wenn sich ein Steuerelement im Bearbeitungsmodus befindet, ist das Stiftsymbol ebenfalls nicht zu sehen.  
  
-   Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>\-Eigenschaft auf einen Wert unter 11 festgelegt ist, werden die Indikatorsymbole im Elementheader nicht angezeigt.  
  
 Sie können auch einen eigenen Elementheader und ein eigenes Auswahlsymbol angeben, indem Sie ein <xref:System.Windows.Forms.PictureBox>\-Steuerelement verwenden und die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>\-Eigenschaft von <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>\-Ereignis des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements überwachen.  Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
## Siehe auch  
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [How to: Change the Layout of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)   
 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [How to: Display Item Headers in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)   
 [How to: Disable Adding and Deleting DataRepeater Items](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)   
 [How to: Search Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)   
 [How to: Create a Master\/Detail Form by Using Two DataRepeater Controls](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)