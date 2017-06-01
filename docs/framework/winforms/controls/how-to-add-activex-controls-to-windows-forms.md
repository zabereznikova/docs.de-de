---
title: "Gewusst wie: Hinzuf&#252;gen von ActiveX-Steuerelementen zu Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [Windows Forms], Hinzufügen"
  - "Formulare, Hinzufügen von ActiveX-Steuerelementen"
  - "Windows Forms-Steuerelemente, ActiveX-Steuerelemente"
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Hinzuf&#252;gen von ActiveX-Steuerelementen zu Windows&#160;Forms
Obwohl Steuerelemente für Windows Forms vom Windows Forms\-Designer optimal unterstützt werden, besteht zusätzlich die Möglichkeit, ActiveX\-Steuerelemente in Windows Forms zu integrieren.  
  
> [!CAUTION]
>  Windows Forms, denen ActiveX\-Steuerelemente hinzugefügt wurden, unterliegen Leistungseinschränkungen.  
  
 Bevor Sie einem Formular ein ActiveX\-Steuerelement hinzufügen können, müssen Sie es der Toolbox hinzufügen.  Weitere Informationen erhalten Sie unter [COM\-Komponenten, Dialogfeld "Toolbox anpassen"](http://msdn.microsoft.com/de-de/171333f3-f207-4e02-bbdc-17862556212c).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren**, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So fügen Sie Windows Forms ein ActiveX\-Steuerelement hinzu  
  
-   Doppelklicken Sie in der Toolbox auf das Steuerelement.  
  
     Sämtliche projektinternen Verweise auf das Steuerelement werden von [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] hinzugefügt.  Weitere Informationen darüber, was bei der Verwendung von ActiveX\-Steuerelementen in Windows Forms zu berücksichtigen ist, finden Sie unter [Überlegungen zum Integrieren eines ActiveX\-Steuerelements in ein Windows Form](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).  
  
    > [!NOTE]
    >  Der Windows Forms ActiveX Control Importer \(AxImp.exe\) erstellt Ereignisargumente eines anderen Typs als dem, der beim Import von ActiveX\-DLLs \(Dynamic Link Libraries\) erwartet wird.  Die von AxImp.exe erstellen Argumente sind ähnlich dem Folgenden: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, wenn `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` erwartet wird.  Der Code funktioniert trotz dieser Unregelmäßigkeit ordnungsgemäß.  Weitere Informationen finden Sie unter [Windows Forms ActiveX Control Importer\-Tool \(Aximp.exe\)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).  
  
## Siehe auch  
 [Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)   
 [Controls and Programmable Objects Compared in Various Languages and Libraries](http://msdn.microsoft.com/de-de/021f2a1b-8247-4348-a5ad-e1d9ab23004b)   
 [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)   
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Windows Forms\-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)