---
title: "Gewusst wie: Implementieren der bidirektionalen Kommunikation zwischen DHTML-Code und Clientanwendungscode | Microsoft Docs"
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
  - "WebBrowser.ObjectForScripting"
  - "WebBrowser.Document"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Kommunikationen, DHTML- und Clientanwendungen"
  - "DHTML, Einbetten in Windows Forms"
  - "Beispiele [Windows Forms], WebBrowser-Steuerelement"
  - "WebBrowser-Steuerelement [Windows Forms], Kommunikation zwischen der DHTML- und der Clientanwendung"
  - "WebBrowser-Steuerelement [Windows Forms], Beispiele"
ms.assetid: 55353a32-b09e-4479-a521-ff3a5ff9a708
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Implementieren der bidirektionalen Kommunikation zwischen DHTML-Code und Clientanwendungscode
Das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement können Sie verwenden, um Ihren Windows Forms\-Clientanwendungen vorhandenen DHTML\-Webanwendungscode \(dynamisches HTML\) hinzuzufügen.  Dies ist hilfreich, wenn Sie viel Zeit in die Erstellung DHTML\-basierter Steuerelemente investiert haben und von den Möglichkeiten der Windows Forms\-Benutzeroberfläche profitieren möchten, ohne vorhandenen Code umschreiben zu müssen.  
  
 Das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement ermöglicht es Ihnen, mithilfe der <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>\- und der <xref:System.Windows.Forms.WebBrowser.Document%2A>\-Eigenschaft bidirektionale Kommunikation zwischen Ihrem Clientanwendungscode und Ihrem Webseitenskriptcode zu implementieren.  Darüber hinaus können Sie das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement so konfigurieren, dass die Websteuerelemente sich nahtlos mit anderen Steuerelementen auf Ihrem Anwendungsformular einfügen, wodurch deren DHTML\-Implementierung ausgeblendet wird.  Damit sich die Steuerelemente nahtlos einfügen, formatieren Sie die angezeigte Seite so, dass die Hintergrundfarbe und der visuelle Stil mit dem restlichen Formular übereinstimmen, und verwenden Sie die <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>\-, die <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>\- und die <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A>\-Eigenschaft, um die Standardbrowserfeatures zu deaktivieren.  
  
### So betten Sie DHTML in Ihre Windows Forms\-Anwendung ein  
  
1.  Legen Sie die <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>\-Eigenschaft des <xref:System.Windows.Forms.WebBrowser>\-Steuerelements auf `false` fest, um zu verhindern, dass das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement Dateien öffnet, die auf ihm abgelegt werden.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#1)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#1)]  
  
2.  Legen Sie die <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>\-Eigenschaft auf `false` fest, um zu verhindern, dass das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement sein Kontextmenü anzeigt, wenn der Benutzer mit der rechten Maustaste auf das Steuerelement klickt.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#2)]  
  
3.  Legen Sie die <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A>\-Eigenschaft des Steuerelements auf `false` fest, um zu verhindern, dass das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement auf Tastenkombinationen reagiert.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#3)]  
  
4.  Legen Sie die <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>\-Eigenschaft im Konstruktor des Formulars oder in einem <xref:System.Windows.Forms.Form.Load>\-Ereignishandler fest.  
  
     Im folgenden Code wird die Formularklasse selbst für das Skriptobjekt verwendet.  
  
    > [!NOTE]
    >  Das COM \(Component Object Model\) muss auf das Skriptobjekt zugreifen können.  Um das Formular für COM sichtbar zu machen, fügen Sie Ihrer Formularklasse das <xref:System.Runtime.InteropServices.ComVisibleAttribute>\-Attribut hinzu.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#4)]  
  
5.  Implementieren Sie öffentliche Eigenschaften oder Methoden in Ihrem Anwendungscode, den Ihr Skriptcode verwendet.  
  
     Wenn Sie beispielsweise die Formularklasse für das Skriptobjekt verwenden, fügen Sie der Formularklasse folgenden Code hinzu.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#5)]  
  
6.  Verwenden Sie das `window.external`\-Objekt in Ihrem Skriptcode, um auf öffentliche Eigenschaften und Methoden des angegebenen Objekts zuzugreifen.  
  
     Der folgende HTML\-Code veranschaulicht, wie eine Methode des Skriptobjekts über Klicken auf eine Schaltfläche aufgerufen wird.  Kopieren Sie diesen Code in das BODY\-Element eines HTML\-Dokuments, das Sie mithilfe der <xref:System.Windows.Forms.WebBrowser.Navigate%2A>\-Methode des Steuerelements laden oder das Sie der <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>\-Eigenschaft des Steuerelements zuweisen .  
  
    ```  
    <button onclick="window.external.Test('called from script code')">  
        call client code from script code  
    </button>  
    ```  
  
7.  Implementieren Sie Funktionen in Ihrem Skriptcode, den Ihr Anwendungscode verwendet.  
  
     Das folgende HTML\-SCRIPT\-Element stellt eine Beispielfunktion bereit.  Kopieren Sie diesen Code in das HEAD\-Element eines HTML\-Dokuments, das Sie mithilfe der <xref:System.Windows.Forms.WebBrowser.Navigate%2A>\-Methode des Steuerelements laden oder das Sie der <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>\-Eigenschaft des Steuerelements zuweisen .  
  
    ```  
    <script>  
    function test(message) {   
        alert(message);   
    }  
    </script>  
    ```  
  
8.  Verwenden Sie die <xref:System.Windows.Forms.WebBrowser.Document%2A>\-Eigenschaft, um aus Ihrem Clientanwendungscode auf den Skriptcode zuzugreifen.  
  
     Fügen Sie beispielsweise den folgenden Code dem <xref:System.Windows.Forms.Control.Click>\-Ereignishandler einer Schaltfläche hinzu.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#8)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#8)]  
  
9. Nachdem Sie das Debuggen des DHTML\-Codes abgeschlossen haben, legen Sie die <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A>\-Eigenschaft des Steuerelements auf `true` fest, um zu verhindern, dass das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement Fehlermeldungen für Skriptcodeprobleme angezeigt.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#9)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#9)]  
  
## Beispiel  
 Mit dem folgenden Codebeispiel steht Ihnen eine vollständige Beispielanwendung zur Verfügung, die Ihnen dabei hilft, sich mit diesem Feature vertraut zu machen.  Der HTML\-Code wird nicht aus einer separaten HTML\-Datei, sondern über die <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>\-Eigenschaft in das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement geladen.  
  
 [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#0)]  
  
## Kompilieren des Codes  
 Dieser Code erfordert:  
  
-   Verweise auf die Assemblys "System" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.WebBrowser>   
 <xref:System.Windows.Forms.WebBrowser.Document%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A?displayProperty=fullName>   
 [WebBrowser\-Steuerelement](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)