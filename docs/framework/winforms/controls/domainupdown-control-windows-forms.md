---
title: "DomainUpDown-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 485640dc320809e9be5550d380b4fc9a2326e027
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="domainupdown-control-windows-forms"></a>DomainUpDown-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.DomainUpDown> Steuerelement sieht wie eine Kombination aus einem Textfeld und ein Paar von Schaltflächen in einer Liste oben oder unten verschieben. Das Steuerelement zeigt an, und legt eine Zeichenfolge aus einer Liste von Optionen. Der Benutzer kann die Zeichenfolge auswählen, indem Sie auf nach oben oder unten Schaltflächen, um eine Liste durchlaufen, durch Drücken der nach-oben und nach unten-Taste oder durch Eingabe eine Zeichenfolge, die ein Element in der Liste entspricht. Eine Verwendungsmöglichkeit für dieses Steuerelement ist für das Auswählen von Elementen aus einer alphabetisch sortierte Liste der Namen. (Um die Liste zu sortieren, legen die <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> -Eigenschaft `true`.) Die Funktion dieses Steuerelements wird im Listenfeld oder Kombinationsfeld sehr ähnlich, aber es nur sehr wenig Speicherplatz beanspruchen.  
  
 Die wichtigsten Eigenschaften des Steuerelements sind <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, und <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. Die <xref:System.Windows.Forms.DomainUpDown.Items%2A> Eigenschaft enthält die Liste der Objekte, deren Text im Steuerelement angezeigt werden. Wenn <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> festgelegt ist, um `false`, das Steuerelement automatisch abgeschlossen wird, Text, dass der Benutzer eingibt, und es mit einem Wert in der Liste vergleicht. Wenn <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> festgelegt ist, um `true`, Durchführen eines Bildlaufs hinter dem letzten Element gelangen Sie auf das erste Element in der Liste und umgekehrt. Die wichtigsten Methoden des Steuerelements sind <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> und <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Dieses Steuerelement zeigt nur Textzeichenfolgen. Wenn Sie ein Steuerelement möchten, in dem numerische Werte angezeigt, verwenden die <xref:System.Windows.Forms.NumericUpDown> Steuerelement. Weitere Informationen finden Sie unter [NumericUpDown-Steuerelement](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md) .  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über das DomainUpDown-Steuerelement](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)  
 Stellt die allgemeinen Konzepte von der <xref:System.Windows.Forms.DomainUpDown> -Steuerelement, das ermöglicht Benutzern das Durchsuchen und auswählen aus einer Liste von Textzeichenfolgen.  
  
 [Gewusst wie: Programmgesteuertes Hinzufügen von Elementen zu DomainUpDown-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Beschreibt, wie die Textzeichenfolgen der <xref:System.Windows.Forms.DomainUpDown> Steuerelement sollte angezeigt werden.  
  
 [Gewusst wie: Entfernen von Elementen aus DomainUpDown-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Beschreibt das Löschen von Elementen aus der <xref:System.Windows.Forms.DomainUpDown> Steuerelement im Code.  
  
## <a name="reference"></a>Verweis  
 <xref:System.Windows.Forms.DomainUpDown>  
 Beschreibt diese Klasse und enthält Links zu allen zugehörigen Membern.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Beschreibt diese Klasse und enthält Links zu allen zugehörigen Membern...  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Steuerelemente, die in Windows Forms verwendet werden können](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 Enthält eine vollständige Liste der Windows Forms-Steuerelemente mit Links zu Informationen zur jeweiligen Verwendung.
