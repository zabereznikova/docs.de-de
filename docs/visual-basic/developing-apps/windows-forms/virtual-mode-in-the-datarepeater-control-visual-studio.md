---
title: "Virtual Mode in the DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "virtual data binding"
  - "DataRepeater"
  - "DataRepeater, virtual mode"
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Virtual Mode in the DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Wenn Sie sehr umfangreiche Tabellendaten in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement anzeigen möchten, können Sie die Leistung verbessern, indem Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>\-Eigenschaft auf `True` festlegen und die Interaktion des Steuerelements mit der Datenquelle explizit verwalten.  Das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement stellt mehrere Ereignisse bereit, die Sie für die Interaktion mit der Datenquelle und für die benötigte Datenanzeige zur Laufzeit verarbeiten können.  
  
## Funktionsweise des virtuellen Modus  
 Das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement wird am häufigsten verwendet, um untergeordnete Steuerelemente von <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> zur Entwurfszeit an eine Datenquelle zu binden und um zu ermöglichen, dass <xref:System.Windows.Forms.BindingSource> Daten in beide Richtungen überträgt.  Im virtuellen Modus sind die Steuerelemente nicht an eine Datenquelle gebunden. Die Daten werden zur Laufzeit von der zugrunde liegenden Datenquelle abgerufen und an diese übertragen.  
  
 Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>\-Eigenschaft auf `True` festgelegt wurde, erstellen Sie die Benutzeroberfläche, indem Sie Steuerelemente aus der **Toolbox** hinzufügen, anstatt gebundene Steuerelemente aus dem Fenster **Datenquellen** hinzuzufügen.  
  
 Ereignisse werden für jedes Steuerelement einzeln ausgelöst, und Sie müssen Code hinzufügen, um die Datenanzeige zu verwalten.  Wenn die Ansicht zu einem neuen <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> blättert, wird für jedes Steuerelement einmal das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>\-Ereignis ausgelöst. Sie müssen dann die Werte für jedes Steuerelement im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>\-Ereignishandler angeben.  
  
 Wenn der Benutzer Daten in einem der Steuerelemente ändert, wird das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>\-Ereignis ausgelöst. Sie müssen die Daten anschließend validieren und in der Datenquelle speichern.  
  
 Wenn der Benutzer ein neues Element hinzufügt, wird das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>\-Ereignis ausgelöst.  Verwenden Sie den Ereignishandler, um einen neuen Datensatz in der Datenquelle zu erstellen.  Um unbeabsichtigte Änderungen zu vermeiden, müssen Sie zudem das <xref:System.Windows.Forms.Control.KeyDown>\-Ereignis für jedes Steuerelement überwachen und <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> aufrufen, wenn der Benutzer die ESC\-TASTE drückt.  
  
 Wenn sich die Datenquelle ändert, können Sie das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement aktualisieren, indem Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetTemplateItem%2A>\-Methode und die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetTemplateItem%2A>\-Methode aufrufen.  Beide Methoden müssen der Reihenfolge nach aufgerufen werden.  
  
 Zudem müssen Sie Ereignishandler für das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>\-Ereignis, das beim Löschen eines Elements ausgelöst wird, und optional für die Ereignisse <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems> und <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems> implementieren. Letztere werden ausgelöst, wenn ein Benutzer ein Element über die ENTF\-TASTE löscht.  
  
## Implementieren des virtuellen Modus  
 Im Folgenden werden die Schritte zum Implementieren des virtuellen Modus erläutert.  
  
#### So implementieren Sie den virtuellen Modus  
  
1.  Ziehen Sie ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement von der Registerkarte **Visual Basic PowerPacks** in der **Toolbox** in ein Formular\- oder Containersteuerelement.  Legen Sie für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>\-Eigenschaft `True` fest.  
  
2.  Ziehen Sie Steuerelemente aus der **Toolbox** in den Elementvorlagenbereich \(der obere Bereich\) des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements.  Sie benötigen ein Steuerelement für jedes Feld in der Datenquelle, das angezeigt werden soll.  
  
3.  Implementieren Sie einen Handler für das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>\-Ereignis, um Werte für jedes Steuerelement bereitzustellen.  Dieses Ereignis wird ausgelöst, wenn beim Bildlauf ein neues <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> angezeigt wird.  Der Code entspricht in etwa folgendem Beispiel für eine Datenquelle mit dem Namen `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_1.vb)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_1.cs)]  
  
4.  Implementieren Sie einen Handler für das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>\-Ereignis, um die Daten zu speichern.  Dieses Ereignis wird ausgelöst, wenn ein Benutzer Änderungen an einem untergeordneten Steuerelement von <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> übergibt.  Der Code entspricht in etwa folgendem Beispiel für eine Datenquelle mit dem Namen `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_2.vb)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_2.cs)]  
  
5.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.Control.KeyDown>\-Ereignis jedes untergeordneten Steuerelements, und überwachen Sie die ESC\-TASTE.  Rufen Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A>\-Methode auf, um zu verhindern, dass das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>\-Ereignis ausgelöst wird.  Der Code entspricht in etwa dem folgenden Beispiel.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_3.vb)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_3.cs)]  
  
6.  Implementieren Sie einen Handler für das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>\-Ereignis.  Dieses Ereignis wird ausgelöst, wenn der Benutzer ein neues Element zum <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement hinzufügt.  Der Code entspricht in etwa folgendem Beispiel für eine Datenquelle mit dem Namen `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_4.vb)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_4.cs)]  
  
7.  Implementieren Sie einen Handler für das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>\-Ereignis.  Dieses Ereignis wird ausgelöst, wenn ein Benutzer ein vorhandenes Element löscht.  Der Code entspricht in etwa folgendem Beispiel für eine Datenquelle mit dem Namen `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_5.vb)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_5.cs)]  
  
8.  Implementieren Sie zur Validierung auf Steuerelementebene optional Handler für die <xref:System.Windows.Forms.Control.Validating>\-Ereignisse der untergeordneten Steuerelemente.  Der Code entspricht in etwa dem folgenden Beispiel.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_6.vb)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_6.cs)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)