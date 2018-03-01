---
title: "Gewusst wie: Ändern von Formaten eines Elements im verwalteten HTML-Dokumentobjektmodell"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3726ccdebf310d831fb0d7ea21fab011293f6d99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a>Gewusst wie: Ändern von Formaten eines Elements im verwalteten HTML-Dokumentobjektmodell
Formate können im HTML-Format Sie um die Darstellung eines Dokuments und seiner Elemente zu steuern. <xref:System.Windows.Forms.HtmlDocument>und <xref:System.Windows.Forms.HtmlElement> unterstützen <xref:System.Windows.Forms.HtmlElement.Style%2A> Eigenschaften, die Formatzeichenfolgen Folgendes Format verwenden:  
  
 `name1:value1;...;nameN:valueN;`  
  
 Hier ist ein `DIV` mit einer Formatzeichenfolge, die die Schriftart Arial und den Text fett festgelegt:  
  
 `<DIV style="font-face:arial;font-weight:bold;">`  
  
 `Hello, world!`  
  
 `</DIV>`  
  
 Das Problem mit dem Bearbeiten von Stilen mithilfe der <xref:System.Windows.Forms.HtmlElement.Style%2A> Eigenschaft ist, dass es bei Personen ausweisen kann mühsam hinzu, und entfernen einzelne formateinstellungen aus der Zeichenfolge. Beispielsweise würde es einer komplexen Prozedur zum Rendern von vorangegangenen Texts kursiv, sobald der Benutzer über den Cursor positioniert werden die `DIV`, und ergreifen Sie kursiv deaktiviert, wenn der Cursor bleibt die `DIV`. Wenn Sie eine große Anzahl von Formaten auf diese Weise bearbeiten müssen würde ein Problem dar.  
  
 Das folgende Verfahren enthält Code, mit denen Sie problemlos Formate für HTML-Dokumente und Elemente bearbeiten können. Die Prozedur erfordert, dass Sie wissen, wie grundlegende Aufgaben in Windows Forms, z. B. Erstellen eines neuen Projekts und Hinzufügen eines Steuerelements zu einem Formular.  
  
### <a name="to-process-style-changes-in-a-windows-forms-application"></a>Verarbeiten von Änderungen an Formatvorlagen in einer Windows Forms-Anwendung  
  
1.  Erstellen Sie ein neues Windows Forms-Projekt.  
  
2.  Erstellen Sie eine neue Klassendatei mit der Erweiterung, die für Ihre Programmiersprache geeignet.  
  
3.  Kopieren der `StyleGenerator` Klasse von Code im Abschnitt "Beispiel" dieses Themas in die Klassendatei, und speichern Sie den Code.  
  
4.  Speichern Sie den folgenden HTML-Code in eine Datei mit dem Namen Test.htm.  
  
    ```  
    <HTML>  
        <BODY>  
  
            <DIV style="font-face:arial;font-weight:bold;">  
                Hello, world!  
            </DIV><P>  
  
            <DIV>  
                Hello again, world!  
            </DIV><P>  
  
        </BODY>  
    </HTML>  
    ```  
  
5.  Hinzufügen einer <xref:System.Windows.Forms.WebBrowser> Steuerelement namens `webBrowser1` zum Hauptformular des Projekts.  
  
6.  Fügen Sie den folgenden Code Codedatei des Projekts.  
  
    > [!IMPORTANT]
    >  Sicherstellen, dass die `webBrowser1_DocumentCompleted` Ereignishandler als konfiguriert ist, einen Listener für die <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> Ereignis. In [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], doppelklicken Sie auf die <xref:System.Windows.Forms.WebBrowser> steuern; in einem Text-Editor, konfigurieren Sie den Listener programmgesteuert.  
  
     [!code-csharp[ManagedDOMStyles#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7.  Führen Sie das Projekt aus. Führen Sie den Cursor über die erste `DIV` ermöglicht, die Auswirkungen des Codes zu beobachten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt den vollständigen Code für die `StyleGenerator` -Klasse, die eine vorhandene Formatwert analysiert, unterstützt das Hinzufügen, ändern und Entfernen von Formatvorlagen und einen neuen Style-Wert mit der angeforderten Änderungen zurückgibt.  
  
 [!code-csharp[ManagedDOMStyles#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.HtmlElement>
