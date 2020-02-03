---
title: Übersicht über das DomainUpDown-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 86703a96d4845414d043161e0efa67bfde9278db
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745859"
---
# <a name="domainupdown-control-overview-windows-forms"></a>Übersicht über das DomainUpDown-Steuerelement (Windows Forms)
Das Windows Forms <xref:System.Windows.Forms.DomainUpDown>-Steuerelement ist im Wesentlichen eine Kombination aus einem Textfeld und einem Paar von Schaltflächen, um eine Liste nach oben oder unten zu verschieben. Das-Steuerelement zeigt eine Text Zeichenfolge aus einer Auswahlliste an und legt diese fest. Der Benutzer kann die Zeichenfolge auswählen, indem er auf die Schaltflächen nach oben und unten klickt, um durch eine Liste zu navigieren, indem er die nach-oben-und nach-unten-Taste drückt oder eine Zeichenfolge eingibt, die mit einem Element Ein möglicher Verwendungsmöglichkeiten für dieses Steuerelement ist das Auswählen von Elementen aus einer alphabetisch sortierten Liste von Namen.  
  
> [!NOTE]
> Um die Liste zu sortieren, legen Sie die <xref:System.Windows.Forms.DomainUpDown.Sorted%2A>-Eigenschaft auf `true`fest.  
  
 Die-Funktion dieses Steuer Elements ähnelt dem Listenfeld oder Kombinations Feld, aber es nimmt nur wenig Platz in die Nähe.  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Die Schlüsseleigenschaften des-Steuer Elements sind <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>und <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. Die <xref:System.Windows.Forms.DomainUpDown.Items%2A>-Eigenschaft enthält die Liste der-Objekte, deren Textwerte im-Steuerelement angezeigt werden. Wenn <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> auf `false`festgelegt ist, vervollständigt das Steuerelement automatisch Text, den der Benutzer eingibt und mit einem Wert in der Liste übereinstimmt. Wenn <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> auf `true`festgelegt ist, führt der Bildlauf hinter das letzte Element zum ersten Element in der Liste und umgekehrt. Die Schlüsselmethoden des Steuer Elements sind <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> und <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Dieses Steuerelement zeigt nur Text Zeichenfolgen an. Wenn Sie ein Steuerelement wünschen, das numerische Werte anzeigt, verwenden Sie das <xref:System.Windows.Forms.NumericUpDown>-Steuerelement. Weitere Informationen finden Sie unter [Übersicht über das NumericUpDown-Steuer](numericupdown-control-overview-windows-forms.md)Element.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DomainUpDown>
- [DomainUpDown-Steuerelement](domainupdown-control-windows-forms.md)
