---
title: DomainUpDown-Steuerelement (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: 83d674e3fb7ff7e715b75c635b891cd4e9703a21
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704533"
---
# <a name="domainupdown-control-windows-forms"></a>DomainUpDown-Steuerelement (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.DomainUpDown> Steuerelement sieht wie eine Kombination aus einem Textfeld und zwei Schaltflächen oben oder unten verschieben, Durchlaufen einer Liste. Das Steuerelement zeigt an, und legt eine Zeichenfolge aus einer Liste von Optionen. Der Benutzer kann die Zeichenfolge auswählen, indem Sie auf nach oben oder unten Schaltflächen zum Navigieren durch eine Liste, durch Drücken der nach-oben und nach-unten-Pfeiltasten oder durch Eingabe einer Zeichenfolge, die ein Element in der Liste entspricht. Eine Verwendungsmöglichkeit für dieses Steuerelement ist für das Auswählen von Elementen aus eine alphabetisch sortierte Liste von Namen. (Um die Liste zu sortieren, legen Sie die <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> Eigenschaft `true`.) Die Funktion dieses Steuerelements ist das Listenfeld oder Kombinationsfeld sehr ähnlich, aber es dauert bis sehr wenig Speicherplatz.  
  
 Die wichtigsten Eigenschaften des Steuerelements sind <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, und <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. Die <xref:System.Windows.Forms.DomainUpDown.Items%2A> Eigenschaft enthält die Liste der Objekte, deren Textwerte im Steuerelement angezeigt werden. Wenn <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> nastaven NA hodnotu `false`, vervollständigt das Steuerelement automatisch den Text an, dass der Benutzer eingibt, und ihn mit einem Wert in der Liste vergleicht. Wenn <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> nastaven NA hodnotu `true`, Durchführen eines Bildlaufs hinter das letzte Element gelangen Sie auf das erste Element in der Liste und umgekehrt. Die wichtigsten Methoden des Steuerelements sind <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> und <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Dieses Steuerelement zeigt nur Textzeichenfolgen. Wenn Sie verwenden möchten, in dem numerische Werte angezeigt, verwenden Sie die <xref:System.Windows.Forms.NumericUpDown> Steuerelement. Weitere Informationen finden Sie unter [NumericUpDown-Steuerelement](numericupdown-control-windows-forms.md) .  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über das DomainUpDown-Steuerelement](domainupdown-control-overview-windows-forms.md)  
 Stellt die allgemeinen Konzepte des der <xref:System.Windows.Forms.DomainUpDown> -Steuerelement, das ermöglicht das Durchsuchen und auswählen aus einer Liste von Textzeichenfolgen.  
  
 [Vorgehensweise: Programmgesteuertes Hinzufügen von Elementen zu DomainUpDown-Steuerelementen für Windows Forms](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Beschreibt, wie die Zeichenfolgen der <xref:System.Windows.Forms.DomainUpDown> Steuerelement sollte angezeigt werden.  
  
 [Vorgehensweise: Entfernen von Elementen aus DomainUpDown-Steuerelementen für Windows Forms](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Beschreibt das Löschen von Elementen aus der <xref:System.Windows.Forms.DomainUpDown> Steuerelement im Code.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Windows.Forms.DomainUpDown>  
 Beschreibt diese Klasse und enthält Links zu allen deren Membern.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Beschreibt diese Klasse und enthält Links zu allen zugehörigen Membern...  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Steuerelemente, die in Windows Forms verwendet werden können](controls-to-use-on-windows-forms.md)  
 Enthält eine vollständige Liste der Windows Forms-Steuerelemente mit Links zu Informationen zur jeweiligen Verwendung.
