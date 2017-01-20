---
title: "How to: Show Available Serial Ports in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "serial ports, availability"
  - "My.Computer.Ports.SerialPortNames property"
  - "My.Computer.Ports object"
  - "ports, serial port availability"
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Show Available Serial Ports in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

In diesem Thema wird beschrieben, wie mithilfe von `My.Computer.Ports` die verfügbaren seriellen Anschlüsse des Computers in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] angezeigt werden können.  
  
 Um eine Benutzerauswahl des verwendeten Anschlusses zu ermöglichen, werden die Namen der seriellen Anschlüsse in einem <xref:System.Windows.Forms.ListBox>\-Steuerelement angezeigt.  
  
## Beispiel  
 In diesem Beispiel werden alle Zeichenfolgen durchlaufen, die von der `My.Computer.Ports.SerialPortNames`\-Eigenschaft zurückgegeben werden.  Diese Zeichenfolgen sind die Namen der verfügbaren seriellen Anschlüsse am Computer.  
  
 Normalerweise wählt der Benutzer aus der Liste der verfügbaren Anschlüsse den seriellen Anschluss aus, den die Anwendung verwenden soll.  In diesem Beispiel werden die Namen der seriellen Anschlüsse in einem <xref:System.Windows.Forms.ListBox>\-Steuerelement gespeichert.  Weitere Informationen finden Sie unter [ListBox\-Steuerelement](../Topic/ListBox%20Control%20\(Windows%20Forms\).md).  
  
 [!code-vb[VbVbalrMyComputer#45](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/VbVbalrMyComputer/Class2.vb#45)]  
  
 Dieses Codebeispiel ist auch als IntelliSense\-Codeausschnitt verfügbar.  Sie finden das Element in der Codeausschnittauswahl unter **Connectivity and Networking**.  Weitere Informationen finden Sie unter [Codeausschnitte](/visual-studio/ide/code-snippets).  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein Projektverweis auf System.Windows.Forms.dll.  
  
-   Zugriff auf die Member des <xref:System.Windows.Forms>\-Namespaces.  Fügen Sie eine `Imports`\-Anweisung hinzu, wenn der Code keine vollqualifizierten Membernamen enthält.  Weitere Informationen finden Sie unter [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
-   Das Formular muss über das <xref:System.Windows.Forms.ListBox>\-Steuerelement `ListBox1` verfügen.  
  
## Robuste Programmierung  
 Sie müssen nicht unbedingt das <xref:System.Windows.Forms.ListBox>\-Steuerelement zum Anzeigen der verfügbaren seriellen Anschlüsse verwenden.  Sie können auch ein <xref:System.Windows.Forms.ComboBox> oder ein anderes Steuerelement verwenden.  Wenn in der Anwendung keine Benutzereingabe erforderlich ist, können Sie die Informationen in einem <xref:System.Windows.Forms.TextBox>\-Steuerelement anzeigen.  
  
> [!NOTE]
>  Die von `My.Computer.Ports.SerialPortNames` zurückgegebenen Anschlussnamen sind bei Ausführung unter Windows 98 möglicherweise nicht korrekt.  Um Anwendungsfehler zu verhindern, verwenden Sie Ausnahmebehandlung, z. B. die `Try...Catch...Finally`\-Anweisung oder die `Using`\-Anweisung, wenn Sie die Anschlüsse unter Verwendung von Anschlussnamen öffnen.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 [How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)