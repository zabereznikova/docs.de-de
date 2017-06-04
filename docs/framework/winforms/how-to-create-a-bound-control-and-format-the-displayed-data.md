---
title: "Gewusst wie: Erstellen eines gebundenen Steuerelements und Formatieren der angezeigten Daten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Gebundene Steuerelemente [Windows Forms], Erstellen"
  - "Gebundene Steuerelemente [Windows Forms], Formatieren von Daten"
  - "Daten [Windows Forms], Formatierung"
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Erstellen eines gebundenen Steuerelements und Formatieren der angezeigten Daten
Mit der Windows Forms\-Datenbindung können Sie die Daten formatieren, die in einem datengebundenen Steuerelement angezeigt werden, indem Sie das Dialogfeld **Formatierung und erweiterte Bindung** verwenden.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren**, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So binden Sie ein Steuerelement und Formatieren der angezeigten Daten  
  
1.  Stellen Sie die Verbindung zu einer Datenquelle her.  
  
     Weitere Informationen finden Sie unter [Aufbauen der Verbindung zu einer Datenquelle](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).  
  
2.  Wählen Sie im Formular das Steuerelement aus, und öffnen Sie dann das Eigenschaftenfenster.  
  
3.  Erweitern Sie die Eigenschaft **\(Datenbindungen\)**, und klicken Sie dann im Feld **\(Erweitert\)** auf die Schaltfläche mit den Auslassungspunkten ![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton"), um das Dialogfeld **Formatierung und erweiterte Bindung** anzuzeigen, in dem sich eine vollständige Liste der Eigenschaften dieses Steuerelements befindet.  
  
4.  Wählen Sie die Eigenschaft aus, die Sie binden möchten, und klicken Sie dann auf den Pfeil **Bindung**.  
  
     Nun wird eine Liste verfügbarer Datenquellen angezeigt.  
  
5.  Erweitern Sie die Datenquelle, die Sie für die Bindung verwenden möchten, bis Sie das gewünschte einzelne Datenelement finden.  
  
     Wenn die Bindung beispielsweise an einen Spaltenwert in einer Dataset\-Tabelle erfolgen soll, erweitern Sie den Namen des Datasets, und erweitern sie dann den Tabellennamen, um die Spaltennamen anzuzeigen.  
  
6.  Klicken Sie auf den Namen des Elements, das gebunden werden soll.  
  
7.  Klicken Sie im Feld **Formattyp** auf das Format, das Sie auf die im Steuerelement angezeigten Daten anwenden möchten.  
  
     In jedem Fall können Sie den Wert festlegen, der im Steuerelement angezeigt wird, wenn die Datenquelle <xref:System.DBNull> enthält.  Andernfalls sind die Optionen je nach ausgewähltem Formattyp leicht abweichend.  In der folgenden Tabelle werden die Formattypen und Optionen angezeigt.  
  
    |Formattyp|Formatierungsoption|  
    |---------------|-------------------------|  
    |Keine Formatierung|Keine Optionen.|  
    |Numerisch|Geben Sie die Anzahl der Dezimalstellen mithilfe des Optionssteuerelements **Dezimalstellen** an.|  
    |Währung|Geben Sie die Anzahl der Dezimalstellen mithilfe des Optionssteuerelements **Dezimalstellen** an.|  
    |Datum\/Zeit|Wählen Sie aus, wie Datum und Uhrzeit angezeigt werden sollen, indem Sie eines der Elemente im Auswahlfeld **Typ** auswählen.|  
    |Wissenschaftlich|Geben Sie die Anzahl der Dezimalstellen mithilfe des Optionssteuerelements **Dezimalstellen** an.|  
    |Benutzerdefiniert|Geben Sie eine benutzerdefinierte Formatzeichenfolge ein.<br /><br /> Weitere Informationen finden Sie unter [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md). **Note:**  Bei benutzerdefinierten Formatzeichenfolgen kann ein erfolgreicher Roundtrip zwischen Datenquelle und gebundenem Steuerelement nicht garantiert werden   Behandeln Sie stattdessen das <xref:System.Windows.Forms.Binding.Parse>\- oder <xref:System.Windows.Forms.Binding.Format>\-Ereignis für die Bindung, und wenden Sie im Ereignisbehandlungscode eine benutzerdefinierte Formatierung an.|  
  
8.  Klicken Sie auf **OK**, um das Dialogfeld **Formatierung und erweiterte Bindung** zu schließen und zum Eigenschaftenfenster zurückzukehren.  
  
## Siehe auch  
 [Gewusst wie: Erstellen eines einfach gebundenen Steuerelements in einem Windows Form](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)   
 [Validierung von Benutzereingaben in Windows Forms](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)   
 [Datenbindung in Web Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)