---
title: "Gewusst wie: Hinzuf&#252;gen von Webbrowserfunktionen zu einer Windows Forms-Anwendung | Microsoft Docs"
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
  - "Beispiele [Windows Forms], WebBrowser-Steuerelement"
  - "Webbrowser [.NET Framework], Hinzufügen zu Windows Forms"
  - "WebBrowser-Steuerelement [Windows Forms], Hinzufügen von Webbrowser-Funktionen zur Anwendung"
  - "WebBrowser-Steuerelement [Windows Forms], Beispiele"
  - "Windows Forms, Hinzufügen von Webbrowser-Funktionen"
ms.assetid: 3871f072-b57a-435b-9976-e5da28df04a7
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Hinzuf&#252;gen von Webbrowserfunktionen zu einer Windows Forms-Anwendung
Mit dem <xref:System.Windows.Forms.WebBrowser>\-Steuerelement können Sie Webbrowserfunktionalität in Ihre Anwendung einbinden.  Das Steuerelement verhält sich standardmäßig wie ein Webbrowser.  Nach dem Laden einer Anfangs\-URL durch Festlegen der <xref:System.Windows.Forms.WebBrowser.Url%2A>\-Eigenschaft können Sie auf Hyperlinks klicken oder mit den entsprechenden Tastenkombinationen vorwärts oder rückwärts durch den Navigationsverlauf navigieren.  Über das Kontextmenü, das durch Klicken mit der rechten Maustaste angezeigt wird, können standardmäßig zusätzliche Browserfunktionen aufgerufen werden.  Sie können auch neue Dokumente öffnen, indem Sie sie auf dem Steuerelement ablegen.  Das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement verfügt über verschiedene Eigenschaften, Methoden und Ereignisse, mit denen Sie ähnliche Benutzeroberflächenfeatures wie in Internet Explorer implementieren können.  
  
 Im folgenden Beispielcode werden eine Adressleiste, typische Browserschaltflächen, ein Menü **Datei**, eine Statusleiste und eine Titelleiste mit dem Titel der aktuellen Seite implementiert.  
  
## Beispiel  
 [!code-cpp[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys `System,`, `System.Drawing` und `System.Windows.Forms`.  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.WebBrowser>   
 [WebBrowser\-Steuerelement](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)