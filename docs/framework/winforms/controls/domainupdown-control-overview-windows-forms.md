---
title: "&#220;bersicht &#252;ber das DomainUpDown-Steuerelement (Windows Forms) | Microsoft Docs"
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
  - "DomainUpDown"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DomainUpDown-Steuerelement [Windows Forms], Informationen über das DomainUpDown-Steuerelement"
  - "Drehfeld-Steuerelement, Informationen über Drehfelder"
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;bersicht &#252;ber das DomainUpDown-Steuerelement (Windows Forms)
Das <xref:System.Windows.Forms.DomainUpDown>\-Steuerelement in Windows Forms ist im Wesentlichen eine Kombination aus einem Textfeld und einem Paar von Schaltflächen, mit denen in einer Liste vor\- oder zurückgeblättert werden kann.  Das Steuerelement zeigt eine Textzeichenfolge aus einer Liste mit Auswahlmöglichkeiten an und legt diese Zeichenfolge fest.  Die Benutzer können die Zeichenfolge auswählen, indem sie zum Bildlauf durch die Liste auf die Schaltflächen **Nach oben** bzw. **Nach unten** klicken, die **NACH\-OBEN\-** bzw. die **NACH\-UNTEN\-TASTE** drücken oder eine Zeichenfolge eingeben, die mit einem Eintrag in der Liste übereinstimmt.  Dieses Steuerelement könnte z. B. dazu verwendet werden, Einträge aus einer alphabetisch sortierten Namensliste auszuwählen.  
  
> [!NOTE]
>  Zum Sortieren der Liste legen Sie für die <xref:System.Windows.Forms.DomainUpDown.Sorted%2A>\-Eigenschaft `true` fest.  
  
 Die Funktion dieses Steuerelements ist der eines Listenfeldes oder Kombinationsfeldes sehr ähnlich, es nimmt jedoch sehr wenig Platz in Anspruch.  
  
## Haupteigenschaften  
 Die wichtigsten Eigenschaften des Steuerelements sind <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> und <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.  Die <xref:System.Windows.Forms.DomainUpDown.Items%2A>\-Eigenschaft enthält die Liste der Objekte, deren Textwerte im Steuerelement angezeigt werden.  Wenn <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> auf `false` festgelegt wurde, vervollständigt das Steuerelement automatisch den vom Benutzer eingegebenen Text und vergleicht ihn mit einem Wert in der Liste.  Wenn <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> auf `true` festgelegt wurde, wird wieder der erste Eintrag in der Liste angezeigt, wenn Sie den Bildlauf über den letzten Eintrag hinaus durchführen, und umgekehrt.  Die wichtigsten Methoden des Steuerelements sind <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> und <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Dieses Steuerelement zeigt nur Textzeichenfolgen an.  Wenn Sie möchten, dass ein Steuerelement numerische Werte anzeigt, müssen Sie das <xref:System.Windows.Forms.NumericUpDown>\-Steuerelement verwenden.  Weitere Informationen finden Sie unter [Übersicht über das NumericUpDown\-Steuerelement](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DomainUpDown>   
 [DomainUpDown\-Steuerelement](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)