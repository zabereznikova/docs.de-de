---
title: "Gewusst wie: Implementieren der INotifyPropertyChanged-Schnittstelle | Microsoft Docs"
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
  - "INotifyPropertyChanged-Schnittstelle, Implementieren"
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Implementieren der INotifyPropertyChanged-Schnittstelle
Im folgenden Codebeispiel wird die Implementierung der <xref:System.ComponentModel.INotifyPropertyChanged>\-Schnittstelle veranschaulicht.  Implementieren Sie diese Schnittstelle für Geschäftsobjekte, die für die Windows Forms\-Datenbindung verwendet werden.  Wenn diese Schnittstelle implementiert ist, übermittelt sie die Änderungen einer Geschäftsobjekteigenschaft an ein gebundenes Steuerelement.  
  
## Beispiel  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## Siehe auch  
 [Gewusst wie: Anwenden des PropertyNameChanged\-Musters](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)   
 [Datenbindung in Web Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Gewusst wie: Auslösen von Änderungsbenachrichtigungen mithilfe von "BindingSource" und der "INotifyPropertyChanged"\-Schnittstelle](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)   
 [Änderungsbenachrichtigung in der Windows Forms\-Datenbindung](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)