---
title: "&#220;bersicht &#252;ber das Splitter-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Splitter"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Splitter-Steuerelement [Windows Forms], Informationen über das Splitter-Steuerelement"
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# &#220;bersicht &#252;ber das Splitter-Steuerelement (Windows&#160;Forms)
> [!IMPORTANT]
>  Obwohl <xref:System.Windows.Forms.SplitContainer> das <xref:System.Windows.Forms.Splitter>\-Steuerelement vorheriger Versionen ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.Splitter>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 <xref:System.Windows.Forms.Splitter>\-Steuerelemente werden in Windows Forms dazu verwendet, die Größe angedockter Steuerelemente zur Laufzeit anzupassen.  Das <xref:System.Windows.Forms.Splitter>\-Steuerelement wird häufig in Formularen mit Steuerelementen eingesetzt, in denen Daten variabler Länge dargestellt werden müssen. Beispielsweise enthalten die Fensterbereiche in Windows Explorer zu unterschiedlichen Zeiten Informationen unterschiedlicher Länge bzw. Breite.  
  
## Verwenden des Splitter\-Steuerelements  
 Wenn der Benutzer mit dem Mauszeiger auf den nicht angedockten Rahmen eines Steuerelements zeigt, dessen Größe durch ein Aufteilungssteuerelement geändert werden kann, ändert sich die Zeigerdarstellung, um zu signalisieren, dass das Steuerelement vergrößert bzw. verkleinert werden kann.  Mit dem Splitter\-Steuerelement kann der Benutzer die Größe des angedockten Steuerelements ändern, das direkt vor dem Splitter\-Steuerelement positioniert ist.  Daher müssen Sie, um die Größenanpassung bei angedockten Steuerelementen zur Laufzeit zu ermöglichen, zunächst das anzupassende Steuerelement am Rand eines Containers andocken und anschließend ein Aufteilungssteuerelement an derselben Seite des Containers andocken.  
  
## Siehe auch  
 <xref:System.Windows.Forms.SplitContainer>   
 [Gewusst wie: Andocken von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)