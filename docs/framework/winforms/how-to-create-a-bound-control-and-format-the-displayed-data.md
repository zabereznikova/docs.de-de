---
title: 'Gewusst wie: Erstellen eines gebundenen Steuerelements und Formatieren der angezeigten Daten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a8c2836d841215ed3ca8e04461b1298cd41287de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a>Gewusst wie: Erstellen eines gebundenen Steuerelements und Formatieren der angezeigten Daten
Mit Windows Forms-Datenbindung können Sie Daten formatieren, die in einem datengebundenen Steuerelement angezeigt wird, indem die **Formatierung und erweiterte Bindung** (Dialogfeld).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a>So binden Sie ein Steuerelement und Formatieren der angezeigten Daten  
  
1.  Stellen Sie die Verbindung zu einer Datenquelle her.  
  
     Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit einer Datenquelle](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).  
  
2.  Wählen Sie im Formular das Steuerelement aus, und öffnen Sie dann das Eigenschaftenfenster.  
  
3.  Erweitern Sie die **(DataBindings)** -Eigenschaft, und klicken Sie dann in der **(Erweitert)** klicken Sie auf die Schaltfläche mit den Auslassungspunkten (![von VisualStudioEllipsesButton] (../../../docs/framework/winforms/media/vbellipsesbutton.png " VbEllipsesButton")) zum Anzeigen der **Formatierung und erweiterte Bindung** (Dialogfeld), die eine vollständige Liste der Eigenschaften dieses Steuerelements befindet.  
  
4.  Wählen Sie die Eigenschaft zu binden, und klicken Sie dann auf die **binden** Pfeil.  
  
     Nun wird eine Liste verfügbarer Datenquellen angezeigt.  
  
5.  Erweitern Sie die Datenquelle, die Sie für die Bindung verwenden möchten, bis Sie das gewünschte einzelne Datenelement finden.  
  
     Wenn die Bindung beispielsweise an einen Spaltenwert in einer Dataset-Tabelle erfolgen soll, erweitern Sie den Namen des Datasets, und erweitern sie dann den Tabellennamen, um die Spaltennamen anzuzeigen.  
  
6.  Klicken Sie auf den Namen des Elements, das gebunden werden soll.  
  
7.  In der **Formattyp** klicken Sie auf das Format der im Steuerelement angezeigten Daten anwenden möchten.  
  
     In jedem Fall können Sie den Wert festlegen, der im Steuerelement angezeigt wird, wenn die Datenquelle <xref:System.DBNull> enthält. Andernfalls sind die Optionen je nach ausgewähltem Formattyp leicht abweichend. In der folgenden Tabelle werden die Formattypen und Optionen angezeigt.  
  
    |Formattyp|Formatierungsoption|  
    |-----------------|-----------------------|  
    |Keine Formatierung|Keine Optionen.|  
    |Numeric|Geben Sie die Anzahl der Dezimalstellen mithilfe **Dezimalstellen** auf-ab-Steuerelement.|  
    |Währung|Geben Sie die Anzahl der Dezimalstellen mithilfe **Dezimalstellen** auf-ab-Steuerelement.|  
    |Datum/Zeit|Wählen Sie, wie das Datum und die Uhrzeit angezeigt werden soll, durch Auswahl eines der Elemente in der **Typ** Auswahlfeld.|  
    |Wissenschaftlich|Geben Sie die Anzahl der Dezimalstellen mithilfe **Dezimalstellen** auf-ab-Steuerelement.|  
    |Benutzerdefiniert|Geben Sie eine benutzerdefinierte Formatzeichenfolge ein.<br /><br /> Weitere Informationen finden Sie unter [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md). **Hinweis:** benutzerdefinierte Formatzeichenfolgen erfolgreicher Roundtrip zwischen der Datenquelle und gebundenem Steuerelement nicht garantiert. Behandeln Sie stattdessen das <xref:System.Windows.Forms.Binding.Parse>- oder <xref:System.Windows.Forms.Binding.Format>-Ereignis für die Bindung, und wenden Sie im Ereignisbehandlungscode eine benutzerdefinierte Formatierung an.|  
  
8.  Klicken Sie auf **OK** schließen die **Formatierung und erweiterte Bindung** Dialogfeld und zum Eigenschaftenfenster zurückzukehren.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Erstellen eines einfach gebundenen Steuerelements in einem Windows Form](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [Validierung von Benutzereingaben in Windows Forms](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 [Windows Forms-Datenbindung](../../../docs/framework/winforms/windows-forms-data-binding.md)
