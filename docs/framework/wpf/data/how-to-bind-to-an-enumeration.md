---
title: "Gewusst wie: Binden an eine Enumeration | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Binden von Daten, Enumeration"
  - "Datenbindung, Enumeration"
  - "Enumeration"
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Binden an eine Enumeration
Dieses Beispiel zeigt, wie durch eine Bindung an die GetValues\-Methode einer Enumeration eine Bindung an die Enumeration durchgeführt wird.  
  
## Beispiel  
 Im folgenden Beispiel zeigt das <xref:System.Windows.Controls.ListBox>\-Element die Liste der <xref:System.Windows.HorizontalAlignment>\-Enumerationswerte durch Datenbindung an.  Das <xref:System.Windows.Controls.ListBox>\-Element und das <xref:System.Windows.Controls.Button>\-Element sind so gebunden, dass Sie den Wert der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>\-Eigenschaft des <xref:System.Windows.Controls.Button>\-Elements durch Auswählen eines Werts im <xref:System.Windows.Controls.ListBox>\-Element ändern können.  
  
 [!code-xml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## Siehe auch  
 [Binden an eine Methode](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)