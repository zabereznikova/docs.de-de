---
title: Virtueller Modus im DataRepeater-Steuerelement (Visual Studio) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- virtual data binding
- DataRepeater
- DataRepeater, virtual mode
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 85f7e250c57a507e891eb30756c0550098cce9e0
ms.lasthandoff: 03/13/2017

---
# <a name="virtual-mode-in-the-datarepeater-control-visual-studio"></a>Virtueller Modus im DataRepeater-Steuerelement (Visual Studio)
Wenn Sie umfangreiche Tabellendaten in anzeigen möchten ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelement können Sie die Leistung verbessern, indem Sie festlegen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>-Eigenschaft `True` und die Interaktion des Steuerelements mit der Datenquelle explizit verwalten.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement bietet mehrere Ereignisse, die Sie behandeln können, um die Interaktion mit der Datenquelle und die Daten anzuzeigen, wie zur Laufzeit benötigt.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="how-virtual-mode-works"></a>Funktionsweise von virtuellen Modus funktioniert  
 Das häufigste Szenario für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>ist das Steuerelement binden die untergeordneten Steuerelemente des der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>an eine Datenquelle zur Entwurfszeit und ermöglichen die <xref:System.Windows.Forms.BindingSource>zum Übergeben von Daten vorwärts und rückwärts nach Bedarf.</xref:System.Windows.Forms.BindingSource> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Bei Verwendung des virtuellen Modus die Steuerelemente sind nicht an eine Datenquelle gebunden, und Daten werden an die zugrunde liegende Datenquelle zur Laufzeit hin und her übergeben.  
  
 Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>Eigenschaft auf festgelegt ist `True`, erstellen Sie die Benutzeroberfläche durch Hinzufügen von Steuerelementen aus der **Toolbox** anstatt gebundene Steuerelemente aus der **Datenquellen** Fenster.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>  
  
 Ereignisse auf Basis von Steuerelement ausgelöst werden, und müssen Sie Code, um die Anzeige der Daten hinzufügen. Beim Erstellen eines neuen <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>ist im Ansichtsfenster angezeigt, die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>-Ereignis wird ausgelöst, einmal für jedes Steuerelement, und Sie müssen die Werte für jedes Steuerelement im Angeben der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>-Ereignishandler.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>  
  
 Wenn Daten in einem Steuerelement, durch den Benutzer geändert werden der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>-Ereignis wird ausgelöst, und müssen Sie die Daten überprüfen und speichern Sie es in der Datenquelle.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>  
  
 Wenn der Benutzer ein neues Element hinzufügt der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>-Ereignis wird ausgelöst.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> Verwenden Sie den Ereignishandler, um einen neuen Datensatz in der Datenquelle zu erstellen. Sie müssen auch überwachen, um unbeabsichtigte Änderungen zu verhindern, die <xref:System.Windows.Forms.Control.KeyDown>-Ereignis für jedes Steuerelement auf und rufen <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A>, wenn der Benutzer die ESC-Taste drückt.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> </xref:System.Windows.Forms.Control.KeyDown>  
  
 Wenn Ihre ändert Datenquelle, können Sie aktualisieren die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>durch Aufrufen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>und <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>Methoden.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Beide Methoden müssen in der Reihenfolge aufgerufen werden.  
  
 Abschließend müssen Sie Ereignishandler für Implementieren der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>Ereignis, das auftritt, wenn ein Element gelöscht wird, und optional für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems>und <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems>Ereignisse, die auftreten, wenn ein Benutzer ein Element durch Drücken der ENTF-Taste löscht.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>  
  
## <a name="implementing-virtual-mode"></a>Implementieren des virtuellen Modus  
 Im folgenden werden die Schritte, die zum Implementieren des virtuellen Modus erforderlich sind.  
  
#### <a name="to-implement-virtual-mode"></a>Implementieren des virtuellen Modus  
  
1.  Ziehen Sie ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in ein Formular oder Containersteuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Legen Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>-Eigenschaft `True`.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>  
  
2.  Ziehen Sie Steuerelemente aus der **Toolbox** auf den Elementvorlagenbereich (der obere Bereich) von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Sie benötigen ein Steuerelement für jedes Feld in der Datenquelle, die Sie anzeigen möchten.  
  
3.  Implementieren Sie einen Handler für das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>Ereignis, um Werte für jedes Steuerelement bereitzustellen.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> Dieses Ereignis wird ausgelöst, wenn ein neuer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>ist Bildlauf sichtbar.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> Der Code entspricht in etwa das folgende Beispiel, das für eine Datenquelle mit dem Namen `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode&#1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_1.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode Nr.&1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_1.cs)]  
  
4.  Implementieren Sie einen Handler für das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>Ereignis, um die Daten zu speichern.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> Dieses Ereignis wird ausgelöst, wenn der Benutzer Änderungen an ein untergeordnetes Steuerelement des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> ausgeführt. Der Code entspricht in etwa das folgende Beispiel, das für eine Datenquelle mit dem Namen `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode&2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_2.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode Nr.&2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_2.cs)]  
  
5.  Implementieren Sie einen Handler für jedes untergeordnete Steuerelement <xref:System.Windows.Forms.Control.KeyDown>Ereignis und überwachen Sie die ESC-Taste.</xref:System.Windows.Forms.Control.KeyDown> Rufen Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A>Methode, um zu verhindern, dass die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>Ereignis ausgelöst wird.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> Der Code wird im folgende Beispiel entsprechen.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode&3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_3.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode Nr.&3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_3.cs)]  
  
6.  Implementieren Sie einen Handler für das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>Ereignis.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> Dieses Ereignis wird ausgelöst, wenn der Benutzer ein neues Element hinzufügt der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Der Code entspricht in etwa das folgende Beispiel, das für eine Datenquelle mit dem Namen `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode&4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_4.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode Nr.&4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_4.cs)]  
  
7.  Implementieren Sie einen Handler für das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>Ereignis.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> Dieses Ereignis tritt auf, wenn ein Benutzer ein vorhandenes Element löscht. Der Code entspricht in etwa das folgende Beispiel, das für eine Datenquelle mit dem Namen `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode&5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_5.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode&5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_5.cs)]  
  
8.  Implementieren Sie für die Validierung auf Steuerelementebene optional Handler für die <xref:System.Windows.Forms.Control.Validating>Ereignisse der untergeordneten Steuerelemente.</xref:System.Windows.Forms.Control.Validating> Der Code wird im folgende Beispiel entsprechen.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode&6;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_6.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode Nr.&6;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_6.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>   
 [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
