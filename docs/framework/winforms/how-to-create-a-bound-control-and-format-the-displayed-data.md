---
title: 'Gewusst wie: Erstellen eines gebundenen Steuerelements und Formatieren der angezeigten Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: 8f4d3c4c738e31ab83d506dc7afb4e49b142765b
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44276759"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a>Gewusst wie: Erstellen eines gebundenen Steuerelements und Formatieren der angezeigten Daten
Mit Windows Forms-Datenbindung können Sie die Daten formatieren, in einem datengebundenen Steuerelement angezeigt wird, indem die **Formatierung und erweiterte Bindung** Dialogfeld.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a>So binden Sie ein Steuerelement und Formatieren der angezeigten Daten  
  
1.  Stellen Sie die Verbindung zu einer Datenquelle her.  
  
     Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit einer Datenquelle](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).  
  
2.  Wählen Sie im Formular das Steuerelement aus, und öffnen Sie dann das Eigenschaftenfenster.  
  
3.  Erweitern Sie die **(DataBindings)** -Eigenschaft, und klicken Sie dann in der **(Erweitert)** klicken Sie auf die Schaltfläche mit den Auslassungspunkten (![VisualStudioEllipsesButton-bildschirmabbildung](../../../docs/framework/winforms/media/vbellipsesbutton.png " VbEllipsesButton")) zum Anzeigen der **Formatierung und erweiterte Bindung** dieses Dialogfeld wird eine vollständige Liste der Eigenschaften dieses Steuerelements ist.  
  
4.  Wählen Sie die Eigenschaft, die Sie binden möchten, und klicken Sie dann auf die **Bindung** Pfeil.  
  
     Nun wird eine Liste verfügbarer Datenquellen angezeigt.  
  
5.  Erweitern Sie die Datenquelle, die Sie für die Bindung verwenden möchten, bis Sie das gewünschte einzelne Datenelement finden.  
  
     Wenn die Bindung beispielsweise an einen Spaltenwert in einer Dataset-Tabelle erfolgen soll, erweitern Sie den Namen des Datasets, und erweitern sie dann den Tabellennamen, um die Spaltennamen anzuzeigen.  
  
6.  Klicken Sie auf den Namen des Elements, das gebunden werden soll.  
  
7.  In der **Formattypen** klicken Sie auf das Format, die Sie auf die im Steuerelement angezeigten Daten anwenden möchten.  
  
     In jedem Fall können Sie den Wert festlegen, der im Steuerelement angezeigt wird, wenn die Datenquelle <xref:System.DBNull> enthält. Andernfalls sind die Optionen je nach ausgewähltem Formattyp leicht abweichend. In der folgenden Tabelle werden die Formattypen und Optionen angezeigt.  
  
    |Formattyp|Formatierungsoption|  
    |-----------------|-----------------------|  
    |Keine Formatierung|Keine Optionen.|  
    |Numerisch|Geben Sie die Anzahl der Dezimalstellen mithilfe **Dezimalstellen** auf-ab-Steuerelement.|  
    |Währung|Geben Sie die Anzahl der Dezimalstellen mithilfe **Dezimalstellen** auf-ab-Steuerelement.|  
    |Datum/Zeit|Wählen Sie, wie das Datum und die Uhrzeit angezeigt werden soll, wählen Sie eines der Elemente in der **Typ** Auswahlfeld.|  
    |Wissenschaftlich|Geben Sie die Anzahl der Dezimalstellen mithilfe **Dezimalstellen** auf-ab-Steuerelement.|  
    |Benutzerdefiniert|Geben Sie eine benutzerdefinierte Formatzeichenfolge ein.<br /><br /> Weitere Informationen finden Sie unter [Formatieren von Typen in .NET](../../../docs/standard/base-types/formatting-types.md). **Hinweis:** benutzerdefinierte Formatzeichenfolgen erfolgreicher Roundtrip zwischen Datenquelle und gebundenen Steuerelement nicht garantiert. Behandeln Sie stattdessen das <xref:System.Windows.Forms.Binding.Parse>- oder <xref:System.Windows.Forms.Binding.Format>-Ereignis für die Bindung, und wenden Sie im Ereignisbehandlungscode eine benutzerdefinierte Formatierung an.|  
  
8.  Klicken Sie auf **OK** schließen die **Formatierung und erweiterte Bindung** Dialogfeld und zum Eigenschaftenfenster zurückzukehren.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Erstellen eines einfach gebundenen Steuerelements in einem Windows Form](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [Validierung von Benutzereingaben in Windows Forms](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 [Windows Forms-Datenbindung](../../../docs/framework/winforms/windows-forms-data-binding.md)
