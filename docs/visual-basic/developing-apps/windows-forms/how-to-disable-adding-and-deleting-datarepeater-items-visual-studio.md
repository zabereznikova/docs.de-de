---
title: 'Gewusst wie: Deaktivieren des Hinzufügens und Löschens von DataRepeater-Elementen (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, disabling delete
- DataRepeater, disabling add
ms.assetid: 298d8f60-ddfe-4361-ab66-cf76d0df5220
ms.openlocfilehash: e3d0d2a8d422054e269ee92df1fdfcb5acb96eac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590799"
---
# <a name="how-to-disable-adding-and-deleting-datarepeater-items-visual-studio"></a>Gewusst wie: Deaktivieren des Hinzufügens und Löschens von DataRepeater-Elementen (Visual Studio)
Standardmäßig können Benutzer hinzufügen und Löschen von Elementen in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. Benutzer können ein neues Element hinzufügen, indem Sie die Tastenkombination STRG + N beim eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> den Fokus hat, oder durch Klicken auf die **AddNewItem** Schaltfläche auf der <xref:System.Windows.Forms.BindingNavigator> Steuerelement. Benutzer können ein Element löschen, durch Drücken von löschen, wenn eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> den Fokus hat, oder durch Klicken auf die **DeleteItem** auf die Schaltfläche der <xref:System.Windows.Forms.BindingNavigator> Steuerelement.  
  
 Sie können die hinzufügen und/oder löschen zur Entwurfszeit oder zur Laufzeit deaktivieren.  
  
### <a name="to-disable-adding-and-deleting-at-design-time"></a>Zum Deaktivieren des Hinzufügens und zur Entwurfszeit löschen  
  
1.  Wählen Sie in der Windows Forms-Designer die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
    > [!NOTE]
    >  Sie müssen den unteren Bereich des Steuerelements auswählen. Wenn Sie den Abschnitt "Element" Vorlage auswählen, wird eine andere Gruppe von Eigenschaften angezeigt.  
  
2.  Legen Sie im Fenster Eigenschaften die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> Eigenschaft **"false"**.  
  
3.  Legen Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> Eigenschaft **"false"**.  
  
4.  Wählen Sie in der Windows Forms-Designer die <xref:System.Windows.Forms.BindingNavigator> steuern, und klicken Sie dann auf die **AddNewItem** Schaltfläche (die Schaltfläche mit dem Pluszeichen).  
  
5.  Legen Sie im Fenster Eigenschaften die <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> Eigenschaft **"false"**.  
  
6.  Wählen Sie in der Windows Forms-Designer die <xref:System.Windows.Forms.BindingNavigator> steuern, und klicken Sie dann auf die **DeleteItem** Schaltfläche (die Schaltfläche mit einem roten X darauf).  
  
7.  Legen Sie im Fenster Eigenschaften die <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> Eigenschaft **"false"**.  
  
8.  Wählen Sie auf der Komponentenleiste, die <xref:System.Windows.Forms.BindingSource> , der die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> gebunden ist.  
  
9. Legen Sie im Fenster Eigenschaften die <xref:System.Windows.Forms.BindingSource.AllowNew%2A> Eigenschaft **"false"**.  
  
10. Doppelklicken Sie in Windows Forms-Designer auf die **DeleteItem** Schaltfläche, um den Code-Editor zu öffnen.  
  
11. Wählen Sie in der Dropdownliste aus der Ereignisliste die `BindingNavigatorDeleteItem_EnabledChanged` Ereignis.  
  
12. Fügen Sie dem `BindingNavigatorDeleteItem_EnabledChanged` -Ereignishandler folgenden Code hinzu:  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  Dieser Schritt ist erforderlich, da die <xref:System.Windows.Forms.BindingSource> die **DeleteItem** -Schaltfläche bei jeder Änderung des aktuellen Datensatzes aktiviert.  
  
### <a name="to-disable-adding-and-deleting-at-run-time"></a>So deaktivieren Sie hinzufügen und Löschen von zur Laufzeit  
  
1.  Doppelklicken Sie im Windows Forms-Designer auf das Formular, um den Code-Editor zu öffnen.  
  
2.  Fügen Sie dem `Form_Load` -Ereignis folgenden Code hinzu:  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.vb)]  
  
3.  Fügen Sie dem `BindingNavigatorDeleteItem_EnabledChanged` -Ereignishandler folgenden Code hinzu:  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  Dieser Schritt ist erforderlich, da die <xref:System.Windows.Forms.BindingSource> die **DeleteItem** -Schaltfläche bei jeder Änderung des aktuellen Datensatzes aktiviert.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
