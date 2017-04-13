---
title: "Gewusst wie: Behandeln von Fehlern und Ausnahmen in Zusammenhang mit der Datenbindung | Microsoft Docs"
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
  - "BindingSource-Komponente [Windows Forms], Behandlung von Fehlern und Ausnahmen"
  - "Datenbindung, Fehlerbehandlung"
  - "Datenbindung, Beispiele"
  - "Fehlerbehandlung, Datenbindung"
  - "Fehlerbehandlung, Beispiele"
  - "Beispiele [Windows Forms], Fehlerbehandlung"
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Behandeln von Fehlern und Ausnahmen in Zusammenhang mit der Datenbindung
Häufig treten Ausnahmen und Fehler bei den zugrunde liegenden Geschäftsobjekten auf, wenn Sie diese an Steuerelemente binden.  Sie können diese Fehler und Ausnahmen abfangen und dann wiederherstellen oder die Fehlerinformationen an den Benutzer übergeben, indem Sie das <xref:System.Windows.Forms.Binding.BindingComplete>\-Ereignis für eine bestimmte <xref:System.Windows.Forms.Binding>\-, <xref:System.Windows.Forms.BindingSource>\- oder <xref:System.Windows.Forms.CurrencyManager>\-Komponente behandeln.  
  
## Beispiel  
 In diesem Codebeispiel wird das Behandeln von Fehlern und Ausnahmen veranschaulicht, die während der Datenbindung auftreten.  Es zeigt das Abfangen von Fehlern, indem das <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=fullName>\-Ereignis der <xref:System.Windows.Forms.Binding>Objekte behandelt wird.  Um Fehler und Ausnahmen durch die Behandlung dieses Ereignisses abfangen zu können, müssen Sie die Formatierung für die Bindung aktivieren.  Sie können die Formatierung beim Erstellen der Bindung oder beim Hinzufügen zur Bindungsauflistung oder beim Festlegen der <xref:System.Windows.Forms.Binding.FormattingEnabled%2A>\-Eigenschaft auf `true` aktivieren.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 Wenn der Code ausgeführt und eine leere Zeichenfolge für den Namen des Teils oder ein Wert für die Teilenummer eingegeben wird, der kleiner als 100 ist, wird ein Meldungsfeld angezeigt.  Dies ist ein Ergebnis der Behandlung des <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=fullName>\-Ereignisses für diese Textfeldbindungen.  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=fullName>   
 <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=fullName>   
 [BindingSource\-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md)