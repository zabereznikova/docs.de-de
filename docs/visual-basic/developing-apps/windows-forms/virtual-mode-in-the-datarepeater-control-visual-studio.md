---
title: Virtueller Modus im DataRepeater-Steuerelement (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- virtual data binding [Visual Basic]
- DataRepeater
- DataRepeater, virtual mode
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
ms.openlocfilehash: 3988c16746606de9f20f9a66b87539b6cea04758
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700805"
---
# <a name="virtual-mode-in-the-datarepeater-control-visual-studio"></a>Virtueller Modus im DataRepeater-Steuerelement (Visual Studio)
Wenn große Mengen an Tabellendaten in angezeigt werden soll eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement, können Sie die Leistung verbessern, indem Sie festlegen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> Eigenschaft `True` und die Interaktion des Steuerelements mit dessen Datenquelle explizit zu verwalten. Die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement bietet mehrere Ereignisse, die Sie behandeln können, um die Interaktion mit Ihrer Datenquelle, und die Daten anzuzeigen, wie zur Laufzeit benötigt.  
  
## <a name="how-virtual-mode-works"></a>Wie virtuelle Modus funktioniert  
 Das häufigste Szenario für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> ist das Steuerelement die untergeordneten Steuerelemente des binden die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> in einen Daten-Datenquelle zur Entwurfszeit aus, und ermöglichen die <xref:System.Windows.Forms.BindingSource> zum Übergeben von Daten hin und her, je nach Bedarf. Bei Verwendung des virtuellen Modus die Steuerelemente sind nicht an eine Datenquelle gebunden, und Daten werden an die zugrunde liegende Datenquelle zur Laufzeit hin und her übergeben.  
  
 Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> -Eigenschaftensatz auf `True`, erstellen Sie die Benutzeroberfläche durch Hinzufügen von Steuerelementen aus der **Toolbox** nicht gebundene Steuerelementen aus der **Datenquellen** Fenster.  
  
 Pro Steuerelement-Ereignisse ausgelöst werden, und Sie müssen den Code so ändern die Anzeige der Daten hinzufügen. Wenn ein neuer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> ein Bildlauf durchgeführt wird, in der Ansicht, die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> -Ereignis wird ausgelöst, einmal für jedes Steuerelement, und Sie müssen angeben, die Werte für jedes Steuerelement in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> -Ereignishandler.  
  
 Wenn Daten in eines der Steuerelemente, die vom Benutzer geändert werden die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> Ereignis wird ausgelöst, und müssen Sie überprüfen, die Daten und speichern Sie sie in der Datenquelle.  
  
 Wenn der Benutzer ein neues Element, fügt die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> Ereignis wird ausgelöst. Verwenden Sie den Ereignishandler, um einen neuen Datensatz in der Datenquelle zu erstellen. Um unbeabsichtigte Änderungen zu verhindern, müssen Sie auch überwachen, die <xref:System.Windows.Forms.Control.KeyDown> -Ereignis für jedes Steuerelement und jeder Aufruf <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> , wenn der Benutzer die ESC-Taste drückt.  
  
 Wenn Ihre ändert Datenquelle, können Sie aktualisieren die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement durch Aufrufen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> und <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> Methoden. Beide Methoden müssen in der Reihenfolge aufgerufen werden.  
  
 Abschließend müssen Sie Ereignishandler für implementieren die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> -Ereignis, das tritt auf, wenn ein Element gelöscht wird, und optional für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems> und <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems> Ereignisse, die auftreten, wenn ein Benutzer ein Objekt löscht, durch Drücken der ENTF-Taste.  
  
## <a name="implementing-virtual-mode"></a>Implementieren des virtuellen Modus  
 Es folgen die Schritte, die zum Implementieren des virtuellen Modus erforderlich sind.  
  
#### <a name="to-implement-virtual-mode"></a>Implementieren des virtuellen Modus  
  
1.  Ziehen Sie eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte die **Toolbox** in ein Formular oder Containersteuerelement. Legen Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> -Eigenschaft auf `True`fest.  
  
2.  Ziehen Sie Steuerelemente aus der **Toolbox** in den Elementvorlagenbereich (oberer Bereich), der die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. Sie benötigen ein Steuerelement für jedes Feld in der Datenquelle, die Sie anzeigen möchten.  
  
3.  Implementieren Sie einen Handler für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> Ereignis, um Werte für jedes Steuerelement angeben. Dieses Ereignis wird ausgelöst, wenn ein neuer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> ein Bildlauf durchgeführt wird, in der Ansicht. Der Code entspricht in etwa das folgende Beispiel handelt es sich für eine Datenquelle mit dem Namen `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_1.cs)]  
  
4.  Implementieren Sie einen Handler für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> Ereignis, um die Daten zu speichern. Dieses Ereignis wird ausgelöst, wenn der Benutzer Commit von Änderungen an ein untergeordnetes Steuerelement von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>. Der Code entspricht in etwa das folgende Beispiel handelt es sich für eine Datenquelle mit dem Namen `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_2.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_2.cs)]  
  
5.  Implementieren Sie einen Handler für jedes untergeordnete Steuerelement des <xref:System.Windows.Forms.Control.KeyDown> Ereignis- und überwachen Sie die ESC-Taste. Rufen Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> Methode, um zu verhindern, dass die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> Ereignis ausgelöst wird. Der Code wird im folgende Beispiel entsprechen.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_3.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_3.cs)]  
  
6.  Implementieren Sie einen Handler für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> Ereignis. Dieses Ereignis wird ausgelöst, wenn der Benutzer ein neues Element hinzufügt. die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. Der Code entspricht in etwa das folgende Beispiel handelt es sich für eine Datenquelle mit dem Namen `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_4.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_4.cs)]  
  
7.  Implementieren Sie einen Handler für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> Ereignis. Dieses Ereignis tritt auf, wenn ein Benutzer ein vorhandenes Element löscht. Der Code entspricht in etwa das folgende Beispiel handelt es sich für eine Datenquelle mit dem Namen `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_5.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_5.cs)]  
  
8.  Für die Überprüfung der Steuerungsebene, implementieren Sie optional Handler für die <xref:System.Windows.Forms.Control.Validating> Ereignisse der untergeordneten Steuerelemente. Der Code wird im folgende Beispiel entsprechen.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_6.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_6.cs)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>
- [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
