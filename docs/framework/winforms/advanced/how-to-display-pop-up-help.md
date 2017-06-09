---
title: "Gewusst wie: Anzeigen der kontextbezogenen Hilfe | Microsoft Docs"
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
  - "F1-Hilfe, in Dialogfeldern"
  - "Formulare, Anzeigen der Hilfe"
  - "Hilfe, Hinzufügen zu Dialogfeldern"
  - "Hilfe, Kontextbezogene Hilfe"
  - "HelpProvider-Komponente [Windows Forms]"
  - "Modale Dialogfelder, Kontextbezogene Hilfe"
  - "Kontextbezogene Hilfe"
  - "Windows Forms, Anzeigen der Hilfe"
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Anzeigen der kontextbezogenen Hilfe
Eine Möglichkeit, Hilfeinformationen für Windows Forms aufzurufen, stellt die Schaltfläche **Hilfe** dar, die sich rechts in der Titelleiste befindet und über die <xref:System.Windows.Forms.Form.HelpButton%2A>\-Eigenschaft aufgerufen werden kann.  Diese Art, die Hilfe aufzurufen, eignet sich besonders für Dialogfelder.  In modal \(mit der <xref:System.Windows.Forms.Form.ShowDialog%2A>\-Methode\) angezeigten Dialogfeldern ist das Aufrufen externer Hilfesysteme problematisch, da modale Dialogfelder zuerst geschlossen werden müssen, ehe der Fokus auf ein anderes Fenster gerichtet werden kann.  Zudem darf sich bei Verwendung der Schaltfläche **Hilfe** weder die Schaltfläche **Minimieren** noch die Schaltfläche**Maximieren** in der Titelleiste befinden.  Während dies eine Standardkonvention für Dialogfelder ist, enthalten Formulare in der Regel jedoch die Schaltflächen **Minimieren** und **Maximieren**.  
  
 Denken Sie daran, dass Sie Steuerelemente auch mithilfe der <xref:System.Windows.Forms.HelpProvider>\-Komponente mit Dateien in einem  Hilfesystem verknüpfen können, selbst wenn Sie kontextbezogene Hilfe implementiert haben.  Weitere Informationen finden Sie unter [Bereitstellen von Hilfeinformationen in einer Windows\-Anwendung](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren**, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So zeigen Sie kontextbezogene Hilfe an  
  
1.  Ziehen Sie eine [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)\-Komponente aus der Toolbox in Ihr Formular.  
  
     Sie befindet sich in der Komponentenleiste im unteren Bereich des Windows Forms Designer.  
  
2.  Legen Sie im Fenster "Eigenschaften" die Eigenschaft <xref:System.Windows.Forms.Form.HelpButton%2A> auf `true` fest.  Dadurch wird in der Titelleiste des Formulars auf der rechten Seite eine Schaltfläche mit einem Fragezeichen angezeigt.  
  
3.  Damit die Hilfeschaltfläche <xref:System.Windows.Forms.Form.HelpButton%2A> angezeigt werden kann, müssen Sie die Eigenschaften <xref:System.Windows.Forms.Form.MinimizeBox%2A> und <xref:System.Windows.Forms.Form.MaximizeBox%2A> des Formulars auf `false`, die Eigenschaft <xref:System.Windows.Forms.Form.ControlBox%2A> auf `true` und die Eigenschaft <xref:System.Windows.Forms.Form.FormBorderStyle%2A> auf einen der folgenden Werte festlegen: <xref:System.Windows.Forms.FormBorderStyle>, <xref:System.Windows.Forms.FormBorderStyle>, <xref:System.Windows.Forms.FormBorderStyle> oder <xref:System.Windows.Forms.FormBorderStyle>.  
  
4.  Wählen Sie das Steuerelement aus, für das Sie Hilfeinformationen in Ihrem Formular anzeigen möchten, und legen Sie im Fenster "Eigenschaften" den Hilfetext fest.  Dieser Text wird ähnlich wie eine [QuickInfo](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md) in einem Fenster angezeigt .  
  
5.  Drücken Sie **F5**.  
  
6.  Drücken Sie in der Titelleiste die Schaltfläche **Hilfe**, und klicken Sie auf das Steuerelement, für das Sie den Hilfetext festgelegt haben.  
  
## Siehe auch  
 [Benutzerführung mithilfe von QuickInfos](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)   
 [Integrieren von Benutzerhilfe in Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)