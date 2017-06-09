---
title: "Gewusst wie: &#196;ndern der Verz&#246;gerung der ToolTip-Komponente in Windows&#160;Forms | Microsoft Docs"
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
  - "Beispiele [Windows Forms], QuickInfo"
  - "ToolTip-Komponente [Windows Forms], Verzögerungswerte"
  - "QuickInfo [Windows Forms], Verzögerungswerte"
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: &#196;ndern der Verz&#246;gerung der ToolTip-Komponente in Windows&#160;Forms
Sie können für eine <xref:System.Windows.Forms.ToolTip>\-Komponente in Windows Forms mehrere Verzögerungswerte festlegen.  Die Maßeinheit für alle diese Eigenschaften ist Millisekunden.  Die <xref:System.Windows.Forms.ToolTip.InitialDelay%2A>\-Eigenschaft bestimmt, wie lange der Benutzer auf das zugeordnete Steuerelement zeigen muss, damit die QuickInfo\-Zeichenfolge angezeigt wird.  Die <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A>\-Eigenschaft legt die Anzahl der Millisekunden fest, die vergehen, bis die nächsten QuickInfo\-Zeichenfolgen angezeigt werden, während der Mauszeiger von einem mit einer QuickInfo verbundenen Steuerelement zum nächsten bewegt wird.  Die <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>\-Eigenschaft legt fest, wie lange die QuickInfo\-Zeichenfolge angezeigt wird.  Sie können diese Werte einzeln oder über den Wert der <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>\-Eigenschaft festlegen. Die übrigen Verzögerungseigenschaften werden auf der Basis des Werts festgelegt, der der <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>\-Eigenschaft zugeordnet wurde.  Wenn für <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> beispielsweise der Wert N festgelegt wird, wird für <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> der Wert N, für <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> der Wert von <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> dividiert durch Fünf \(oder N\/5\) und für <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> ein Wert festgelegt, der dem fünffachen Wert der <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>\-Eigenschaft \(oder 5N\) entspricht.  
  
### So legen Sie die Verzögerung fest  
  
1.  Legen Sie die folgenden Eigenschaften fest, wie in diesem Beispiel gezeigt.  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## Siehe auch  
 [Übersicht über die ToolTip\-Komponente](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)   
 [Gewusst wie: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)   
 [ToolTip\-Komponente](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)