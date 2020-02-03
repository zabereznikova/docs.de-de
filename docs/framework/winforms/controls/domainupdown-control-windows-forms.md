---
title: DomainUpDown-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: b538350a84e341d6b2759a7db28f8799f3777a86
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745826"
---
# <a name="domainupdown-control-windows-forms"></a>DomainUpDown-Steuerelement (Windows Forms)
Das Windows Forms <xref:System.Windows.Forms.DomainUpDown>-Steuerelement sieht wie eine Kombination aus einem Textfeld und einem Paar von Schaltflächen aus, um eine Liste nach oben oder unten zu verschieben. Das-Steuerelement zeigt eine Text Zeichenfolge aus einer Auswahlliste an und legt diese fest. Der Benutzer kann die Zeichenfolge auswählen, indem er auf die Schaltflächen nach oben und unten klickt, um durch eine Liste zu navigieren, indem er die nach-oben-und nach-unten-Taste drückt oder eine Zeichenfolge eingibt, die mit einem Element Ein möglicher Verwendungsmöglichkeiten für dieses Steuerelement ist das Auswählen von Elementen aus einer alphabetisch sortierten Liste von Namen. (Um die Liste zu sortieren, legen Sie die <xref:System.Windows.Forms.DomainUpDown.Sorted%2A>-Eigenschaft auf `true`fest.) Die-Funktion dieses Steuer Elements ähnelt dem Listenfeld oder Kombinations Feld, aber es nimmt nur wenig Platz in die Nähe.  
  
 Die Schlüsseleigenschaften des-Steuer Elements sind <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>und <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. Die <xref:System.Windows.Forms.DomainUpDown.Items%2A>-Eigenschaft enthält die Liste der-Objekte, deren Textwerte im-Steuerelement angezeigt werden. Wenn <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> auf `false`festgelegt ist, vervollständigt das Steuerelement automatisch Text, den der Benutzer eingibt und mit einem Wert in der Liste übereinstimmt. Wenn <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> auf `true`festgelegt ist, führt der Bildlauf hinter das letzte Element zum ersten Element in der Liste und umgekehrt. Die Schlüsselmethoden des Steuer Elements sind <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> und <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Dieses Steuerelement zeigt nur Text Zeichenfolgen an. Wenn Sie ein Steuerelement wünschen, das numerische Werte anzeigt, verwenden Sie das <xref:System.Windows.Forms.NumericUpDown>-Steuerelement. Weitere Informationen finden Sie unter [NumericUpDown-Steuer](numericupdown-control-windows-forms.md) Element.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über das DomainUpDown-Steuerelement](domainupdown-control-overview-windows-forms.md)  
 Führt die allgemeinen Konzepte des <xref:System.Windows.Forms.DomainUpDown> Steuer Elements ein, das Benutzern das Durchsuchen und Auswählen einer Liste von Text Zeichenfolgen ermöglicht.  
  
 [Gewusst wie: Programmgesteuertes Hinzufügen von Elementen zu DomainUpDown-Steuerelementen in Windows Forms](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Beschreibt, wie die Text Zeichenfolgen angegeben werden, die das <xref:System.Windows.Forms.DomainUpDown> Steuerelement anzeigen soll.  
  
 [Gewusst wie: Entfernen von Elementen aus DomainUpDown-Steuerelementen in Windows Forms](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Beschreibt, wie Elemente aus dem <xref:System.Windows.Forms.DomainUpDown>-Steuerelement im Code gelöscht werden.  
  
## <a name="reference"></a>Verweis  
 <xref:System.Windows.Forms.DomainUpDown>  
 Beschreibt diese Klasse und enthält Links zu allen deren Membern.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Beschreibt diese Klasse und enthält Links zu allen zugehörigen Membern.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Steuerelemente, die in Windows Forms verwendet werden können](controls-to-use-on-windows-forms.md)  
 Enthält eine vollständige Liste der Windows Forms-Steuerelemente mit Links zu Informationen zur jeweiligen Verwendung.
