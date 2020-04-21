---
title: Übersicht über das LinkLabel-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 3e8607644c858ae804e384c974b5e81c1786c6a1
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739522"
---
# <a name="linklabel-control-overview-windows-forms"></a>Übersicht über das LinkLabel-Steuerelement (Windows Forms)
Mit dem <xref:System.Windows.Forms.LinkLabel> Windows Forms-Steuerelement können Sie Links im Webstil zu Windows Forms-Anwendungen hinzufügen. Sie können <xref:System.Windows.Forms.LinkLabel> das Steuerelement für alles <xref:System.Windows.Forms.Label> verwenden, wofür Sie das Steuerelement verwenden können. Sie können einen Teil des Textes auch als Link zu einer Datei, einem Ordner oder einer Webseite festlegen.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>Was Sie mit dem LinkLabel Control tun können  
 Zusätzlich zu allen Eigenschaften, Methoden und <xref:System.Windows.Forms.Label> Ereignissen des <xref:System.Windows.Forms.LinkLabel> Steuerelements verfügt das Steuerelement über Eigenschaften für Hyperlinks und Verknüpfungsfarben. Die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Eigenschaft legt den Bereich des Textes fest, der den Link aktiviert. Die <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> und Eigenschaften legen die Farben der Verknüpfung fest. Das <xref:System.Windows.Forms.LinkLabel.LinkClicked> Ereignis bestimmt, was geschieht, wenn der Linktext ausgewählt wird.  
  
 Die einfachste Verwendung <xref:System.Windows.Forms.LinkLabel> des Steuerelements besteht darin, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> einen einzelnen Link mithilfe der Eigenschaft <xref:System.Windows.Forms.LinkLabel.Links%2A> anzuzeigen, aber Sie können auch mehrere Hyperlinks mithilfe der Eigenschaft anzeigen. Mit <xref:System.Windows.Forms.LinkLabel.Links%2A> der Eigenschaft können Sie auf eine Sammlung von Links zugreifen. Sie können auch Daten <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> in der <xref:System.Windows.Forms.LinkLabel.Link> Eigenschaft jedes einzelnen Objekts angeben. Der Wert <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> der Eigenschaft kann verwendet werden, um den Speicherort einer anzuzeigenden Datei oder die Adresse einer Website zu speichern.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.LinkLabel>
- [Übersicht über das Label-Steuerelement](label-control-overview-windows-forms.md)
- [Vorgehensweise: Verknüpfen eines Objekts oder einer Webseite mit dem LinkLabel-Steuerelement in Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Vorgehensweise: Ändern der Darstellung des LinkLabel-Steuerelements in Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
