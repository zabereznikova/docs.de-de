---
title: Problembehandlung beim DataRepeater-Steuerelement (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, troubleshooting
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
ms.openlocfilehash: 7b045e1c45221cbde82c88286da8e698a763d844
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580602"
---
# <a name="troubleshooting-the-datarepeater-control-visual-studio"></a>Problembehandlung beim DataRepeater-Steuerelement (Visual Studio)
Dieses Thema führt häufige Probleme, die auftreten können, bei der Arbeit mit der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
## <a name="datarepeater-keyboard-and-mouse-events-are-not-raised"></a>DataRepeater-Tastatur- und Mausereignisse werden nicht ausgelöst.  
 Einige <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelementereignisse, z. B. Tastatur und Maus-Ereignisse nicht ausgelöst. Dieser Fehler ist entwurfsbedingt. Die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement selbst ist ein Container für <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> Objekte und kann nicht zur Laufzeit zugegriffen werden. Die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> keine Ereignisse zur Entwurfszeit bereit. Aus diesem Grund wird durch Klicken auf ein Element oder eine Taste drücken, wenn das Element den Fokus besitzt ein Ereignis nicht ausgelöst.  
  
 Die Ausnahme ist, wenn die <xref:System.Windows.Forms.Control.Padding%2A> -Eigenschaftensatz auf eine große genügend Wert, der die Rändern des verfügbar zu machen die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. In diesem Fall wird Sie auf den verfügbar gemachten Rand Mausereignisse ausgelöst werden.  
  
 Um dieses Problem zu beheben, fügen einen <xref:System.Windows.Forms.Panel> die Steuerung an die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> Teil der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement, und fügen Sie den Rest der Steuerelemente auf der <xref:System.Windows.Forms.Panel>. Anschließend können Sie Code zum Hinzufügen der <xref:System.Windows.Forms.Panel> Ereignishandler für Tastatur und Maus-Ereignisse des Steuerelements.  
  
## <a name="the-datarepeater-is-partially-hidden-behind-the-binding-navigator"></a>DataRepeater wird teilweise durch den BindingNavigator ausgeblendet.  
 Beim ersten Hinzufügen einer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement zu einem Formular und fügen Sie datengebundene Steuerelemente aus der **Datenquellen** Fenster die <xref:System.Windows.Forms.BindingNavigator> Steuerelement angezeigt werden kann, auf der die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. Dies ist eine bekannte Einschränkung der **Datenquellen** Fenster und dem Verhalten anderer Steuerelemente, wie die <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
 Können Sie entweder die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> niedriger als die <xref:System.Windows.Forms.BindingNavigator> -Steuerelements zur Entwurfszeit aus, oder fügen Sie Code ähnlich die folgenden in das `Load` -Ereignishandler.  
  
```vb  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```csharp  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## <a name="controls-are-not-displayed-correctly-at-run-time"></a>Steuerelemente werden zur Laufzeit nicht ordnungsgemäß angezeigt.  
 Einige Steuerelemente in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement möglicherweise nicht wie erwartet zur Laufzeit angezeigt werden. Der Prozess zum Klonen von Steuerelementen aus der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> auf die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> kann nicht immer alle Eigenschaften aller Steuerelemente bestimmt. Wenn Sie ein ungebundenes hinzufügen, z. B. <xref:System.Windows.Forms.ListBox> die Steuerung an eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements zur Entwurfszeit aus, und füllen Sie die <xref:System.Windows.Forms.ListBox.Items%2A> Auflistung mit einer Liste von Zeichenfolgen, die <xref:System.Windows.Forms.ListBox> wird zur Laufzeit leer sein. Dies ist, da der Klonvorgang berücksichtigen kann nicht die <xref:System.Windows.Forms.ListBox.Items%2A> Eigenschaft.  
  
 Sie können Probleme wie diese beheben, indem das Wiederherstellen der fehlenden Eigenschaften in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> Ereignis, das auftritt, nachdem das Standard-Klonen abgeschlossen ist. Das folgende Beispiel zeigt die Vorgehensweise beim Reparieren der <xref:System.Windows.Forms.ListBox.Items%2A> Auflistung von einer <xref:System.Windows.Forms.ListBox> steuern, der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> -Ereignishandler.  
  
 [!code-csharp[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/troubleshooting-the-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/troubleshooting-the-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="the-selection-symbol-on-the-item-header-is-missing"></a>Das Auswahlsymbol "auf der Header fehlt.  
 Wenn Sie ändern die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> Eigenschaft des Elementheaders in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement einige Farben können dazu führen, dass das Auswahlsymbol "nicht mehr angezeigt. Ändern der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> Eigenschaft kann auch dazu führen, dass das Auswahlsymbol "nicht mehr angezeigt.  
  
 Die Farbe und Größe des Symbols Auswahl können nicht geändert werden.  
  
-   Setzen Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> zu <xref:System.Drawing.Color.White%2A>, das Auswahlsymbol ist nicht sichtbar, wenn ein Element zum ersten Mal ausgewählt wird.  
  
-   Setzen Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> zu <xref:System.Drawing.Color.Black%2A>, das Auswahlsymbol ist nicht sichtbar, wenn ein Steuerelement ausgewählt ist, und das Stiftsymbol nicht angezeigt werden, wenn ein Steuerelement im Bearbeitungsmodus befindet.  
  
-   Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> -Eigenschaftensatz auf ein Wert, der kleiner als 11 ist, die Indikatorsymbole im Elementheader können nicht angezeigt werden.  
  
 Sie können eigene Element Elementheader und Symbol angeben, mit einer <xref:System.Windows.Forms.PictureBox> Steuerung und Überwachung der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> Eigenschaft der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> in die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> Ereignis die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
## <a name="see-also"></a>Siehe auch
- [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Ändern des Layouts eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Anzeigen von Elementheadern in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Deaktivieren des Hinzufügens und Löschens von DataRepeater-Elementen](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)
- [Vorgehensweise: Suchen von Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Erstellen Sie eine Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
