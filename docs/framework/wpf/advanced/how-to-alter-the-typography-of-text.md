---
title: "Gewusst wie: &#196;ndern der Typografie von Text | Microsoft Docs"
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
  - "Festlegen von Typografie-Attributen"
  - "Typografie-Attribut, Festlegen"
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# Gewusst wie: &#196;ndern der Typografie von Text
Im folgenden Beispiel wird anhand des Beispiels <xref:System.Windows.Documents.Paragraph> veranschaulicht, wie das <xref:System.Windows.Documents.TextElement.Typography%2A>\-Attribut festgelegt wird.  
  
## Beispiel  
 [!code-xml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 In der folgenden Abbildung wird gezeigt, wie dieses Beispiel gerendert wird.  
  
 ![Bildschirmabbildung: Text mit geänderter Typografie](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement\_Typog")  
  
 Im Gegensatz dazu wird in der folgenden Abbildung gezeigt, wie ein ähnliches Beispiel mit den Standardtypografieeigenschaften gerendert wird.  
  
 ![Bildschirmabbildung: Text mit geänderter Typografie](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement\_Typog\_Default")  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die <xref:System.Windows.Controls.TextBox.Typography%2A>\-Eigenschaft programmgesteuert festgelegt wird.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## Siehe auch  
 [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md)