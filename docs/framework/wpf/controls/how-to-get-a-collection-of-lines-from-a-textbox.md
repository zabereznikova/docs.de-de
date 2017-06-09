---
title: "Gewusst wie: Abrufen einer Auflistung der Zeilen aus einem &quot;TextBox&quot;-Element | Microsoft Docs"
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
  - "Linien, Abrufen von Auflistung von"
  - "TextBox-Steuerelement, Abrufen von Zeilenauflistung"
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Abrufen einer Auflistung der Zeilen aus einem &quot;TextBox&quot;-Element
Dieses Beispiel zeigt, wie Sie eine Auflistung der Textzeilen aus einem <xref:System.Windows.Controls.TextBox>\-Element abrufen.  
  
## Beispiel  
 Das folgende Beispiel zeigt eine einfache Methode, die ein <xref:System.Windows.Controls.TextBox> als Argument verwendet und eine <xref:System.Collections.Specialized.StringCollection> mit den Textzeilen aus **TextBox** zurückgibt.  Die <xref:System.Windows.Controls.TextBox.LineCount%2A>\-Eigenschaft wird verwendet, um zu ermitteln, wie viele Zeilen sich momentan in **TextBox** befinden. Anschließend wird die <xref:System.Windows.Controls.TextBox.GetLineText%2A>\-Methode verwendet, um die einzelnen Zeilen zu extrahieren und der Auflistung der Zeilen hinzuzufügen.  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## Siehe auch  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)