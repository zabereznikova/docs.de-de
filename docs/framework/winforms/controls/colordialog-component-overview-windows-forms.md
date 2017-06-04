---
title: "&#220;bersicht &#252;ber die ColorDialog-Komponente (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ColorDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Farbe (Dialogfeld), Informationen über das Dialogfeld Farbe"
  - "ColorDialog-Komponente, Informationen über ColorDialog"
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;bersicht &#252;ber die ColorDialog-Komponente (Windows&#160;Forms)
Die <xref:System.Windows.Forms.ColorDialog>\-Komponente in Windows Forms ist ein vordefiniertes Dialogfeld, das es Benutzern ermöglicht, eine Farbe aus einer Palette auszuwählen und dieser Palette benutzerdefinierte Farben hinzuzufügen.  Es entspricht dem Dialogfeld, das in anderen Windows\-basierten Anwendungen zur Farbauswahl angezeigt wird.  Verwenden Sie es als einfache Lösung in Ihrer Windows\-basierten Anwendung, anstatt ein eigenes Dialogfeld zu konfigurieren.  
  
 Die im Dialogfeld ausgewählte Farbe wird durch die <xref:System.Windows.Forms.ColorDialog.Color%2A>\-Eigenschaft zurückgegeben.  Wenn die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>\-Eigenschaft auf `false` festgelegt ist, wird die Schaltfläche "Benutzerdefinierte Farben" deaktiviert, und es stehen nur die vordefinierten Farben in der Palette zur Verfügung.  Wenn für die <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>\-Eigenschaft `true` festgelegt ist, können keine Mischfarben ausgewählt werden.  Um das Dialogfeld anzuzeigen, müssen Sie seine <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>\-Methode aufrufen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ColorDialog>   
 [ColorDialog\-Komponente](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)   
 [Dialogfeld\-Steuerelemente und \-Komponenten](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)   
 [Gewusst wie: Ändern der Darstellung der ColorDialog\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)