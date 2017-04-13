---
title: "Gewusst wie: Drucken eines Windows Form | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Drucken [Windows Forms], Drucken eines Formulars"
  - "Drucken [Windows Forms]"
  - "Drucken eines Formulars"
  - "Windows Forms, Drucken"
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Drucken eines Windows Form
Im Verlauf der Entwicklung entsteht häufig der Wunsch, ein Windows Form zu drucken.  Im folgenden Codebeispiel wird veranschaulicht, wie das aktuelle Formular mithilfe der <xref:System.Drawing.Graphics.CopyFromScreen%2A>\-Methode gedruckt wird.  
  
## Beispiel  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## Kompilieren des Codes  
 Dies ist ein vollständiges Codebeispiel mit einer `Main`\-Methode.  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Sie verfügen nicht über die entsprechende Berechtigung für den Zugriff auf den Drucker.  
  
-   Es ist kein Drucker installiert.  
  
## .NET Framework-Sicherheit  
 Zum Ausführen dieses Codebeispiels müssen Sie über Zugriffsberechtigungen für den Drucker verfügen, der an den Computer angeschlossen ist.  
  
## Siehe auch  
 <xref:System.Drawing.Printing.PrintDocument>   
 [Gewusst wie: Darstellen von Bildern mit GDI\+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)   
 [Gewusst wie: Drucken von Grafiken in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)