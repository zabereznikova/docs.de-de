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
ms.openlocfilehash: 9837902bf56a402d623adbcf41558dcc568b7105
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745220"
---
# <a name="linklabel-control-overview-windows-forms"></a>Übersicht über das LinkLabel-Steuerelement (Windows Forms)
Mit dem Windows Forms <xref:System.Windows.Forms.LinkLabel>-Steuerelement können Sie Windows Forms Anwendungen Links im Webstil hinzufügen. Sie können das <xref:System.Windows.Forms.LinkLabel>-Steuerelement für alle Elemente verwenden, für die Sie das <xref:System.Windows.Forms.Label>-Steuerelement verwenden können. Sie können einen Textabschnitt auch als Link zu einer Datei, einem Ordner oder einer Webseite festlegen.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>Was Sie mit dem LinkLabel-Steuerelement tun können  
 Zusätzlich zu allen Eigenschaften, Methoden und Ereignissen des <xref:System.Windows.Forms.Label> Steuer Elements verfügt das <xref:System.Windows.Forms.LinkLabel> Steuerelement über Eigenschaften für Hyperlinks und Verknüpfungs Farben. Die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>-Eigenschaft legt den Bereich des Texts fest, mit dem der Link aktiviert wird. Die Eigenschaften <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>und <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> legen die Farben des Links fest. Das <xref:System.Windows.Forms.LinkLabel.LinkClicked>-Ereignis bestimmt, was geschieht, wenn der Linktext ausgewählt wird.  
  
 Die einfachste Verwendung des <xref:System.Windows.Forms.LinkLabel>-Steuer Elements ist das Anzeigen eines einzelnen Links mit der <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>-Eigenschaft, Sie können jedoch auch mehrere Hyperlinks mithilfe der <xref:System.Windows.Forms.LinkLabel.Links%2A>-Eigenschaft anzeigen. Die <xref:System.Windows.Forms.LinkLabel.Links%2A>-Eigenschaft ermöglicht den Zugriff auf eine Auflistung von Links. Sie können auch Daten in der <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A>-Eigenschaft jedes einzelnen <xref:System.Windows.Forms.LinkLabel.Link> Objekts angeben. Der Wert der <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A>-Eigenschaft kann verwendet werden, um den Speicherort einer Datei zu speichern, die angezeigt werden soll, oder die Adresse einer Website.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.LinkLabel>
- [Übersicht über das Label-Steuerelement](label-control-overview-windows-forms.md)
- [Gewusst wie: Verknüpfen eines Objekts oder einer Webseite mit dem LinkLabel-Steuerelement in Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Gewusst wie: Ändern der Darstellung des LinkLabel-Steuerelements in Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
