---
title: "DomainUpDown-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DomainUpDown-Steuerelement [Windows Forms]"
  - "Drehfeld-Steuerelement"
  - "Drehfeld-Steuerelement, Auf-Ab-Steuerelemente"
  - "Auf-Ab-Steuerelemente"
  - "Auf-Ab-Steuerelemente, Drehfeld-Steuerelemente"
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# DomainUpDown-Steuerelement (Windows&#160;Forms)
Das <xref:System.Windows.Forms.DomainUpDown>\-Steuerelement in Windows Forms sieht wie eine Kombination aus einem Textfeld und einem Paar Schaltflächen aus, mit denen in einer Liste vor\- oder zurückgeblättert werden kann.  Das Steuerelement zeigt eine Textzeichenfolge aus einer Liste mit Auswahlmöglichkeiten an und legt diese Zeichenfolge fest.  Die Benutzer können die Zeichenfolge auswählen, indem sie zum Bildlauf durch die Liste auf die Schaltflächen **Nach oben** bzw. **Nach unten** klicken, die **NACH\-OBEN\-** bzw. die **NACH\-UNTEN\-TASTE** drücken oder eine Zeichenfolge eingeben, die mit einem Eintrag in der Liste übereinstimmt.  Dieses Steuerelement könnte z. B. dazu verwendet werden, Einträge aus einer alphabetisch sortierten Namensliste auszuwählen.  \(Zum Sortieren der Liste legen Sie für die <xref:System.Windows.Forms.DomainUpDown.Sorted%2A>\-Eigenschaft `true` fest.\) Die Funktion dieses Steuerelements ist der eines Listenfeldes oder Kombinationsfeldes sehr ähnlich, es nimmt jedoch sehr wenig Platz in Anspruch.  
  
 Die wichtigsten Eigenschaften des Steuerelements sind <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> und <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.  Die <xref:System.Windows.Forms.DomainUpDown.Items%2A>\-Eigenschaft enthält die Liste der Objekte, deren Textwerte im Steuerelement angezeigt werden.  Wenn <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> auf `false` festgelegt wurde, vervollständigt das Steuerelement automatisch den vom Benutzer eingegebenen Text und vergleicht ihn mit einem Wert in der Liste.  Wenn <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> auf `true` festgelegt wurde, wird wieder der erste Eintrag in der Liste angezeigt, wenn Sie den Bildlauf über den letzten Eintrag hinaus durchführen, und umgekehrt.  Die wichtigsten Methoden des Steuerelements sind <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> und <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Dieses Steuerelement zeigt nur Textzeichenfolgen an.  Wenn Sie möchten, dass ein Steuerelement numerische Werte anzeigt, müssen Sie das <xref:System.Windows.Forms.NumericUpDown>\-Steuerelement verwenden.  Weitere Informationen finden Sie unter [NumericUpDown\-Steuerelement](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md).  
  
## In diesem Abschnitt  
 [Übersicht über das DomainUpDown\-Steuerelement](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)  
 Stellt die allgemeinen Konzepte des <xref:System.Windows.Forms.DomainUpDown>\-Steuerelements vor, das Benutzern das Durchsuchen und Auswählen aus einer Liste von Textzeichenfolgen ermöglicht.  
  
 [Gewusst wie: Programmgesteuertes Hinzufügen von Elementen zu DomainUpDown\-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Beschreibt die Textzeichenfolgen, die das <xref:System.Windows.Forms.DomainUpDown>\-Steuerelement anzeigen soll.  
  
 [Gewusst wie: Entfernen von Elementen aus DomainUpDown\-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Beschreibt das Löschen von Elementen aus dem <xref:System.Windows.Forms.DomainUpDown>\-Steuerelement mittels Code.  
  
## Referenz  
 <xref:System.Windows.Forms.DomainUpDown>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
## Verwandte Abschnitte  
 [Steuerelemente, die in Windows Forms verwendet werden können](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 Enthält eine vollständige Liste der Windows Forms\-Steuerelemente sowie Links zu Informationen über ihre Funktion.