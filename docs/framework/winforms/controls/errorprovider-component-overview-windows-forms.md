---
title: "&#220;bersicht &#252;ber die ErrorProvider-Komponente (Windows&#160;Forms) | Microsoft Docs"
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
  - "ErrorProvider"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Fehlermeldungen, Anzeigen"
  - "ErrorProvider-Komponente [Windows Forms], Informationen über die ErrorProvider-Komponente"
  - "Fehler [Windows Forms], Anzeigen für Benutzer"
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# &#220;bersicht &#252;ber die ErrorProvider-Komponente (Windows&#160;Forms)
Mit der [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md)\-Komponente von Windows Forms wird die Benutzereingabe in einem Formular oder für ein Steuerelement überprüft.  Diese wird üblicherweise bei der Validierung der Benutzereingabe in einem Formular oder beim Anzeigen von Fehlern innerhalb eines Datasets verwendet.  Ein **ErrorProvider**\-Steuerelement ist im Vergleich zu einer Fehlermeldung in einem Meldungsfeld die bessere Alternative, da die Fehlermeldung nach dem Schließen des Meldungsfelds nicht mehr angezeigt wird.  Die <xref:System.Windows.Forms.ErrorProvider>\-Komponente zeigt neben dem betreffenden Steuerelement, z. B. einem Textfeld, ein Fehlersymbol \(![Symbol "ErrorProvider"](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.png "vbErrorProviderIcon")\) an. Wenn der Benutzer den Mauszeiger über das Fehlersymbol bewegt, wird eine QuickInfo mit der Fehlermeldung angezeigt.  
  
## Haupteigenschaften  
 Die Haupteigenschaften der <xref:System.Windows.Forms.ErrorProvider>\-Komponente sind die Eigenschaften <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> und <xref:System.Windows.Forms.ErrorProvider.Icon%2A>.  Bei der Verwendung der <xref:System.Windows.Forms.ErrorProvider>\-Komponente mit datengebundenen Steuerelementen muss für die <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>\-Eigenschaft der entsprechende Container \(üblicherweise Windows Form\) festgelegt werden, damit die Komponente ein Fehlersymbol auf dem Formular anzeigt.  Wenn die Komponente im Designer hinzugefügt wird, wird für die <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>\-Eigenschaft das zugehörige Formular festgelegt. Wenn Sie das Steuerelement in Code hinzufügen, müssen Sie es selbst festlegen.  
  
 Für die <xref:System.Windows.Forms.ErrorProvider.Icon%2A>\-Eigenschaft kann anstelle des Standardfehlersymbols ein benutzerdefiniertes Fehlersymbol festgelegt werden.  Nachdem die <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>\-Eigenschaft festgelegt wurde, kann die <xref:System.Windows.Forms.ErrorProvider>\-Komponente Fehlermeldungen für ein Dataset anzeigen.  Die Hauptmethode der <xref:System.Windows.Forms.ErrorProvider>\-Komponente ist die <xref:System.Windows.Forms.ErrorProvider.SetError%2A>\-Methode, die die Fehlermeldungszeichenfolge und die Anzeigeposition des Fehlersymbols angibt.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.ErrorProvider>\-Komponente bietet keine integrierte Unterstützung für Clients für die Barrierefreiheit.  Wenn Ihre Anwendung bei der Verwendung dieser Komponente barrierefrei sein soll, müssen Sie einen zusätzlichen barrierefreien Feedbackmechanismus bereitstellen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ErrorProvider>   
 [Gewusst wie: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)   
 [Gewusst wie: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)