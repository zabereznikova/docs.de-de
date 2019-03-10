---
title: Übersicht über das LinkLabel-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 81edab0d44ae0bb9dcabe77ad568f281e6f5fffb
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722358"
---
# <a name="linklabel-control-overview-windows-forms"></a>Übersicht über das LinkLabel-Steuerelement (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.LinkLabel> Steuerelement ermöglicht es Ihnen Weblinks, Windows Forms-Anwendungen hinzuzufügen. Können Sie die <xref:System.Windows.Forms.LinkLabel> -Steuerelement für alle Elemente, die Sie verwenden können, die <xref:System.Windows.Forms.Label> für steuern; Sie können auch Teile des Texts als einen Link zu einer Datei, Ordner oder Website festlegen.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>Was können Sie mit dem LinkLabel-Steuerelement tun.  
 Zusätzlich zu allen Eigenschaften, Methoden und Ereignisse der <xref:System.Windows.Forms.Label> -Steuerelement, das <xref:System.Windows.Forms.LinkLabel> Steuerelement verfügt über Eigenschaften für Links und Linkfarben. Die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Eigenschaft legt fest, den Bereich des Texts, der der Link aktiviert wird. Die <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, und <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> Eigenschaften legen die Farben des Links. Die <xref:System.Windows.Forms.LinkLabel.LinkClicked> Ereignis bestimmt, was passiert, wenn der Text des Links ausgewählt ist.  
  
 Den einfachsten Gebrauch von der <xref:System.Windows.Forms.LinkLabel> Steuerelement ist zum Anzeigen einer einzelnen Link mit der <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> -Eigenschaft, aber Sie können auch anzeigen, mehrere Links, die mit der <xref:System.Windows.Forms.LinkLabel.Links%2A> Eigenschaft. Die <xref:System.Windows.Forms.LinkLabel.Links%2A> Eigenschaft ermöglicht den Zugriff auf eine Auflistung von Links. Sie können auch angeben, Daten in die <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> -Eigenschaft jedes einzelnen <xref:System.Windows.Forms.LinkLabel.Link> Objekt. Der Wert des der <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> Eigenschaft kann verwendet werden, um den Speicherort einer Datei, die Anzeige oder die Adresse einer Website zu speichern.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.LinkLabel>
- [Übersicht über das Label-Steuerelement](label-control-overview-windows-forms.md)
- [Vorgehensweise: Link zu einem Objekt oder Webseite mit dem LinkLabel-Steuerelement in Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Vorgehensweise: Ändern der Darstellung des LinkLabel-Steuerelement von Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
