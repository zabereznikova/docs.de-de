---
title: "Gewusst wie: Programmgesteuertes &#196;ndern der FlowDirection des Inhalts | Microsoft Docs"
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
  - "Dokumente, Programmgesteuertes Ändern der FlowDirection-Eigenschaft"
  - "FlowDirection-Eigenschaft, Programmgesteuertes Ändern"
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Programmgesteuertes &#196;ndern der FlowDirection des Inhalts
In diesem Beispiel wird gezeigt, wie die <xref:System.Windows.FrameworkElement.FlowDirection%2A>\-Eigenschaft eines <xref:System.Windows.Controls.FlowDocumentReader> programmgesteuert geändert wird.  
  
## Beispiel  
 Zwei <xref:System.Windows.Controls.Button>\-Elemente werden erstellt, von denen jedes einen der möglichen Werte von <xref:System.Windows.FlowDirection> darstellt.  Durch das Anklicken einer Schaltfläche wird der zugeordnete Eigenschaftswert auf den Inhalt eines <xref:System.Windows.Controls.FlowDocumentReader> mit dem Namen `tf1` angewendet.  Der Eigenschaftswert wird auch in einen <xref:System.Windows.Controls.TextBlock> mit dem Namen `txt1` geschrieben.  
  
 [!code-xml[FlowDirectionSnippets#_FlowDirectionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## Beispiel  
 Die Ereignisse, die den oben definierten Klicks auf Schaltflächen zugeordnet sind, werden in einer [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]\-Code\-Behind\-Datei behandelt.  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]