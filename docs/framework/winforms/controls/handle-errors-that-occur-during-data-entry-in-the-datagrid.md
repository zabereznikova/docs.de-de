---
title: "Gewusst wie: Behandeln von Fehlern, die w&#228;hrend der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten | Microsoft Docs"
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
  - "Dateneingabe, Fehlerbehandlung"
  - "Datenblätter, Fehlerbehandlung"
  - "DataGridView-Steuerelement [Windows Forms], Fehlerbehandlung"
  - "Fehlerbehandlung, Dateneingabe"
  - "Fehlerbehandlung, DataGridView-Steuerelement"
ms.assetid: 9004e72f-fdec-4264-a37d-2c99764efc13
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Behandeln von Fehlern, die w&#228;hrend der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten
Im folgenden Codebeispiel wird veranschaulicht, wie das <xref:System.Windows.Forms.DataGridView>\-Steuerelement verwendet wird, um dem Benutzer Dateneingabefehler zu melden.  
  
 Eine vollständige Erläuterung dieses Codebeispiels finden Sie unter [Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView\-Steuerelement in Windows Forms auftreten](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridView.DataError#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.DataError#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#00)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Data", "System.Windows.Forms" und "System.XML".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## .NET Framework-Sicherheit  
 Das Speichern vertraulicher Informationen \(z. B. eines Kennworts\) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.  Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows\-Authentifizierung \(wird auch als integrierte Sicherheit bezeichnet\) sicherer steuern.  Weitere Informationen finden Sie unter [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView\-Steuerelement in Windows Forms auftreten](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)   
 [Dateneingabe im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Exemplarische Vorgehensweise: Validieren von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)   
 [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md)