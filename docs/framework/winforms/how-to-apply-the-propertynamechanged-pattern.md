---
title: "Gewusst wie: Anwenden des PropertyNameChanged-Musters | Microsoft Docs"
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
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Eigenschaftenänderungen (mit Code)"
  - "Datenbindung, Benutzerdefinierte Steuerelemente"
  - "PropertyNameChanged-Muster, Übernehmen"
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Anwenden des PropertyNameChanged-Musters
Im folgenden Codebeispiel wird veranschaulicht, wie das *PropertyName*Changed\-Muster auf ein benutzerdefiniertes Steuerelement angewendet wird.  Wenden Sie dieses Muster an, wenn Sie benutzerdefinierte Steuerelemente implementieren, die mit dem Windows Forms\-Datenbindungsmodul verwendet werden.  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## Kompilieren des Codes  
 So kompilieren Sie das vorherige Codebeispiel:  
  
-   Fügen Sie den Code in eine leere Codedatei ein.  Sie müssen das benutzerdefinierte Steuerelement in einem Windows Form verwenden, das eine `Main`\-Methode enthält.  
  
## Siehe auch  
 [Gewusst wie: Implementieren der INotifyPropertyChanged\-Schnittstelle](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)   
 [Änderungsbenachrichtigung in der Windows Forms\-Datenbindung](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [Datenbindung in Web Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)