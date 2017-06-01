---
title: "Gewusst wie: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente | Microsoft Docs"
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
  - "BindingSource-Komponente [Windows Forms], Beispiele"
  - "BindingSource, Verwenden mehrerer Formulare"
  - "Datenbindung, Formularübergreifende Freigabe von Daten"
  - "Beispiele [Windows Forms], BindingSource-Komponente"
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente
Sie können Daten einfach in mehreren Formularen gemeinsam nutzen \(freigeben\), indem Sie die <xref:System.Windows.Forms.BindingSource>\-Komponente verwenden.  Beispielsweise könnte es sein, dass Sie ein schreibgeschütztes Formular, in dem die Datenquellendaten zusammengefasst werden, sowie ein bearbeitbares Formular anzeigen möchten, das detaillierte Informationen über das Element enthält, das momentan in der Datenquelle ausgewählt ist.  In diesem Beispiel wird dieses Szenario veranschaulicht.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine <xref:System.Windows.Forms.BindingSource> und die an sie gebundenen Daten in mehreren Formularen gemeinsam genutzt werden können.  In diesem Beispiel wird die gemeinsam genutzte <xref:System.Windows.Forms.BindingSource> an den Konstruktor des untergeordneten Formulars übergeben.  Das untergeordnete Formular ermöglicht es dem Benutzer, die Daten für das aktuell ausgewählte Element im Hauptformular zu bearbeiten.  
  
> [!NOTE]
>  Das <xref:System.Windows.Forms.BindingSource.BindingComplete>\-Ereignis für die <xref:System.Windows.Forms.BindingSource>\-Komponente wird in diesem Beispiel, um sicherzustellen, dass die beiden Formulare synchronisiert bleiben.  Weitere Informationen dazu, warum dies geschieht, finden Sie unter [Gewusst wie: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Windows.Forms", "System.Drawing", "System.Data" und "System.Xml".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 [BindingSource\-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Datenbindung in Web Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Gewusst wie: Behandeln von Fehlern und Ausnahmen in Zusammenhang mit der Datenbindung](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)