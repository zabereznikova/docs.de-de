---
title: "Gewusst wie: Verarbeiten von Ereignissen in einer Web Forms-Anwendung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Ereignisse [.NET Framework], Web Forms"
  - "Web Forms-Steuerelemente, und Ereignisse"
  - "Ereignishandler [.NET Framework], Web Forms"
  - "Ereignisse [.NET Framework], Verarbeiten"
  - "Web Forms, Ereignisbehandlung"
ms.assetid: 73bf8638-c4ec-4069-b0bb-a1dc79b92e32
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# Gewusst wie: Verarbeiten von Ereignissen in einer Web Forms-Anwendung
Ein häufiges Szenario in ASP.NET Web Forms\-Anwendungen ist, eine Webseite mit Steuerelementen gefüllt und dann eine bestimmte Aktion aus, je nach Steuerelement der Benutzer klickt.  Beispielsweise löst ein <xref:System.Web.UI.WebControls.Button?displayProperty=fullName>\-Steuerelement ein Ereignis aus, wenn der Benutzer in der Webseite darauf klickt.  Indem sie das Ereignis behandelt, kann die Anwendung die dem Klicken auf die Schaltfläche entsprechende Anwendungslogik ausführen.  
  
### So behandeln Sie ein Click\-Ereignis auf einer Webseite  
  
1.  Erstellen Sie eine ASP.NET Web Forms\-Seite \(Webseite\) mit einem <xref:System.Web.UI.WebControls.Button>\-Steuerelement mit dem `OnClick`\-Wert verfügt, der auf den Namen der Methode festgelegt wird, den Sie im nächsten Schritt definieren.  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2.  Definieren Sie einen Ereignishandler, der der <xref:System.Web.UI.WebControls.Button.Click>\-Ereignisdelegatunterzeichnung entspricht und den Namen, den Sie für `OnClick` definierter Wert.  
  
    ```csharp  
    protected void Button1_Click(object sender, EventArgs e)  
    {  
        // perform action  
    }  
    ```  
  
    ```vb  
    Protected Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' perform action  
    End Sub  
    ```  
  
     Das <xref:System.Web.UI.WebControls.Button.Click>\-Ereignis verwendet die <xref:System.EventHandler>\-Klasse für den Delegattyp und die <xref:System.EventArgs>\-Klasse für die Ereignisdaten.  Das ASP.NET\-Seitenframework generiert automatisch Code, der eine Instanz von <xref:System.EventHandler> erstellt Diese Delegatinstanz wird dem <xref:System.Web.UI.WebControls.Button.Click>\-Ereignis der <xref:System.Web.UI.WebControls.Button>\-Instanz hinzugefügt.  
  
3.  Im Fall fügen Handlermethode, die Sie in Schritt 2 definierten, Code hinzu, um alle Aktionen auszuführen, die erforderlich sind, wenn das Ereignis auftritt.  
  
## Siehe auch  
 [Ereignisse](../../../docs/standard/events/index.md)