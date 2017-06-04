---
title: "Gewusst wie: Erstellen einer einfachen Bindung | Microsoft Docs"
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
  - "Binden von Daten, Erstellen"
  - "Datenbindung, Erstellen von einfachen Bindungen"
  - "Einfache Bindung, Erstellen"
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Erstellen einer einfachen Bindung
Dieses Beispiel zeigt, wie Sie eine einfache Bindung mithilfe von <xref:System.Windows.Data.Binding> erstellen können.  
  
## Beispiel  
 In diesem Beispiel wird ein `Person`\-Objekt mit einer Zeichenfolgeneigenschaft mit dem Namen `PersonName` verwendet.  Das `Person`\-Objekt wird im Namespace mit dem Namen `SDKSample` definiert.  
  
 Im folgenden Beispiel wird das `Person`\-Objekt mit dem `PersonName`\-Eigenschaftswert `Joe` instanziiert.  Dies geschieht im Abschnitt `Resources` und weist einen `x:Key` zu.  
  
 [!code-xml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
[!code-xml[SimpleBinding#EndWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#endwindow)]  
  
 Um eine Bindung zur `PersonName`\-Eigenschaft vorzunehmen, gehen Sie wie folgt vor:  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 Als Ergebnis wird der <xref:System.Windows.Controls.TextBlock> mit dem Wert "Joe" angezeigt.  
  
## Siehe auch  
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)