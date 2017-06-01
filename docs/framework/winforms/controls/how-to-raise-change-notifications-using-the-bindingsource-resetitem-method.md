---
title: "Gewusst wie: Ausl&#246;sen von &#196;nderungsbenachrichtigungen mithilfe der ResetItem-Methode einer BindingSource | Microsoft Docs"
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
  - "BindingSource-Komponente [Windows Forms], Auslösen von Änderungsbenachrichtigungen mit"
  - "Änderungsbenachrichtigungen"
  - "Änderungsbenachrichtigungen, Auslösen"
  - "Datenbindung, Änderungsbenachrichtigungen"
  - "Datenquellen, Erkennen von Änderungen"
ms.assetid: ab8b4096-37ff-4e30-aabc-de79a2f2e972
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Ausl&#246;sen von &#196;nderungsbenachrichtigungen mithilfe der ResetItem-Methode einer BindingSource
Einige Datenquellen für Ihre Steuerelemente lösen keine Änderungsbenachrichtigungen aus, wenn Elemente geändert, hinzugefügt oder gelöscht werden  Mit der <xref:System.Windows.Forms.BindingSource>\-Komponente können Sie Bindungen zu solchen Datenquellen herstellen und Änderungsbenachrichtigungen in Ihrem Code auslösen.  
  
## Beispiel  
 Anhand dieses Formular wird gezeigt, wie Sie mit einer <xref:System.Windows.Forms.BindingSource>\-Komponente eine Liste an ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement binden können.  Diese Liste löst keine Änderungsbenachrichtigungen aus, weshalb die <xref:System.Windows.Forms.BindingSource.ResetItem%2A>\-Methode für die <xref:System.Windows.Forms.BindingSource> aufgerufen wird, wenn ein Element in der Liste ändert wurde.  .  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/VB/form1.vb#1)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.BindingNavigator>   
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [BindingSource\-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Gewusst wie: Binden eines Windows Forms\-Steuerelements an einen Typ](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)