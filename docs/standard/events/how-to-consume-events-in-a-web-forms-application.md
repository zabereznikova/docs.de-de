---
title: 'Gewusst wie: Verarbeiten von Ereignissen in einer Web Forms-Anwendung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [.NET Framework], Web Forms
- Web Forms controls, and events
- event handlers [.NET Framework], Web Forms
- events [.NET Framework], consuming
- Web Forms, event handling
ms.assetid: 73bf8638-c4ec-4069-b0bb-a1dc79b92e32
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bdb0a6be309f27348ba13bf93fd5aedd3c66a792
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-consume-events-in-a-web-forms-application"></a>Gewusst wie: Verarbeiten von Ereignissen in einer Web Forms-Anwendung
Ein häufiges Szenario in ASP.NET Web Forms-Anwendungen werden von einer Webseite mit Steuerelementen füllen, und führen Sie dann eine bestimmte Aktion, die steuern, dass der Benutzer klickt auf Grundlage ab. Angenommen, ein <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> Steuerelement löst ein Ereignis aus, wenn der Benutzer er auf der Webseite klickt. Die Anwendung kann die zugehörige Anwendungslogik klicken auf die Schaltfläche ausführen, indem Sie die Behandlung des Ereignisses.  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a>So behandeln Sie ein Click-Ereignis auf einer Webseite  
  
1.  Erstellen eine ASP.NET Web Forms-Seite (Webseite), wurde eine <xref:System.Web.UI.WebControls.Button> steuern, mit der `OnClick` Wert festgelegt wird, um den Namen der Methode, die Sie im nächsten Schritt definieren.  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2.  Definieren Sie einen Ereignishandler, entspricht die <xref:System.Web.UI.WebControls.Button.Click> Ereignis Delegatsignatur und, trägt den Namen, die Sie definiert, für die `OnClick` Wert.  
  
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
  
     Die <xref:System.Web.UI.WebControls.Button.Click> Ereignis verwendet die <xref:System.EventHandler> Klasse für den Delegattyp und die <xref:System.EventArgs> Klasse für die Ereignisdaten. Das ASP.NET-Seitenframework generiert automatisch Code, der eine Instanz erstellt <xref:System.EventHandler> und fügt diese Delegatinstanz mit der <xref:System.Web.UI.WebControls.Button.Click> -Ereignis für die <xref:System.Web.UI.WebControls.Button> Instanz.  
  
3.  Fügen Sie im Ereignistext Ereignishandlermethode, die Sie in Schritt 2, definiert Code erforderliche Aktionen auszuführen, die erforderlich sind, wenn das Ereignis auftritt.  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisse](../../../docs/standard/events/index.md)
