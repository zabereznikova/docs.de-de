---
title: Übersicht über das DomainUpDown-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 851c02747a2414e34a5e9d35bdc7d1df916efce0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718895"
---
# <a name="domainupdown-control-overview-windows-forms"></a>Übersicht über das DomainUpDown-Steuerelement (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.DomainUpDown> Steuerelement ist im Wesentlichen eine Kombination aus einem Textfeld und einem Paar von Schaltflächen für das Durchlaufen einer Liste oben oder unten verschieben. Das Steuerelement zeigt an, und legt eine Zeichenfolge aus einer Liste von Optionen. Der Benutzer kann die Zeichenfolge auswählen, indem Sie auf nach oben oder unten Schaltflächen zum Navigieren durch eine Liste, durch Drücken der nach-oben und nach-unten-Pfeiltasten oder durch Eingabe einer Zeichenfolge, die ein Element in der Liste entspricht. Eine Verwendungsmöglichkeit für dieses Steuerelement ist für das Auswählen von Elementen aus eine alphabetisch sortierte Liste von Namen.  
  
> [!NOTE]
>  Um die Liste zu sortieren, legen Sie die <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> Eigenschaft `true`.  
  
 Die Funktion dieses Steuerelements ist das Listenfeld oder Kombinationsfeld sehr ähnlich, aber es dauert bis sehr wenig Speicherplatz.  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Die wichtigsten Eigenschaften des Steuerelements sind <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, und <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. Die <xref:System.Windows.Forms.DomainUpDown.Items%2A> Eigenschaft enthält die Liste der Objekte, deren Textwerte im Steuerelement angezeigt werden. Wenn <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> nastaven NA hodnotu `false`, vervollständigt das Steuerelement automatisch den Text an, dass der Benutzer eingibt, und ihn mit einem Wert in der Liste vergleicht. Wenn <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> nastaven NA hodnotu `true`, Durchführen eines Bildlaufs hinter das letzte Element gelangen Sie auf das erste Element in der Liste und umgekehrt. Die wichtigsten Methoden des Steuerelements sind <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> und <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Dieses Steuerelement zeigt nur Textzeichenfolgen. Wenn Sie verwenden möchten, in dem numerische Werte angezeigt, verwenden Sie die <xref:System.Windows.Forms.NumericUpDown> Steuerelement. Weitere Informationen finden Sie unter [Übersicht über das NumericUpDown-Steuerelement](numericupdown-control-overview-windows-forms.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DomainUpDown>
- [DomainUpDown-Steuerelement](domainupdown-control-windows-forms.md)
