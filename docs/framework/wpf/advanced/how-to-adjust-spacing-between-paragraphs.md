---
title: "Gewusst wie: Anpassen des Abstands zwischen Abs&#228;tzen | Microsoft Docs"
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
  - "Dokumente, Anpassen des Abstands zwischen Absätzen"
  - "Absätze, Abstand zwischen"
  - "Abstand zwischen Absätzen"
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Anpassen des Abstands zwischen Abs&#228;tzen
Dieses Beispiel zeigt, wie in einem fortlaufenden Inhalt der Abstand zwischen den Absätzen angepasst oder unterbunden wird.  
  
 In einem fortlaufenden Inhalt ergibt sich der zusätzliche Abstand, der zwischen Absätzen angezeigt wird, aus den in diesen Absätzen festgelegten Rändern. So kann der Abstand zwischen den Absätzen durch die Anpassung der Absatzränder gesteuert werden.  Um einen zusätzlichen Abstand zwischen zwei Absätzen ganz zu unterbinden, legen Sie die Ränder der Absätze auf **0** fest.  Wenn im gesamten <xref:System.Windows.Documents.FlowDocument> ein einheitlicher Abstand zwischen den Absätzen erreicht werden soll, müssen Sie anhand der Formatierung einen einheitlichen Rand für alle Absätze im <xref:System.Windows.Documents.FlowDocument> festlegen.  
  
 Beachten Sie, dass die Ränder von zwei angrenzenden Absätzen auf den größeren der beiden Ränder "zusammengelegt" und nicht verdoppelt werden.  Wenn also zwei angrenzende Absätze Ränder mit 20 Pixel bzw. 40 Pixel aufweisen, ergibt sich ein Abstand von 40 Pixel, d. h., der Abstand zwischen den Absätzen wird auf den größeren der beiden Randwerte festgelegt.  
  
## Beispiel  
 Im folgenden Beispiel wird die Formatierung verwendet, um den Rand für alle <xref:System.Windows.Documents.Paragraph>\-Elemente in einem <xref:System.Windows.Documents.FlowDocument> auf **0** festzulegen, wodurch zusätzliche Abstände zwischen den im <xref:System.Windows.Documents.FlowDocument> enthaltenen Absätzen effektiv unterbunden werden.  
  
 [!code-xml[BlockSnippets#_ParagraphSpacingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]