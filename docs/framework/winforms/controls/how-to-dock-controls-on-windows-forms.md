---
title: 'Vorgehensweise: Andocken von Steuerelementen in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 58b61af306385a245bedf16e370e6830c370a622
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987490"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Vorgehensweise: Steuerelemente auf Windows Forms Andocken

Sie können Steuerelemente an die Ränder Ihres Formulars andocken, oder Sie können den Container des Steuer Elements ausfüllen (entweder ein Formular oder ein Container Steuerelement). Windows-Explorer dockt <xref:System.Windows.Forms.TreeView> das Steuerelement beispielsweise an die linke Seite des Fensters und dessen <xref:System.Windows.Forms.ListView> Steuerelement auf der rechten Seite des Fensters an. Verwenden Sie <xref:System.Windows.Forms.Control.Dock%2A> die-Eigenschaft für alle sichtbaren Windows Forms Steuerelemente, um den Docking Modus zu definieren.

> [!NOTE]
> Steuerelemente werden in umgekehrter z-Reihenfolge angedockt.

Die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft interagiert mit <xref:System.Windows.Forms.Control.AutoSize%2A> der-Eigenschaft. Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md).

## <a name="to-dock-a-control"></a>Zum Andocken eines Steuer Elements

1. Wählen Sie in Visual Studio das Steuerelement aus, das Sie andocken möchten.

2. Klicken Sie im **Eigenschaften** Fenster auf den Pfeil rechts neben der <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft.

   Es wird ein Editor angezeigt, der eine Reihe von Feldern anzeigt, die die Ränder und den Mittelpunkt des Formulars darstellen.

3. Klicken Sie auf die Schaltfläche, die den Rand des Formulars darstellt, in dem Sie das Steuerelement andocken möchten. Um den Inhalt des Formular-oder Container Steuer Elements des Steuer Elements auszufüllen, klicken Sie auf das Feld Center. Klicken Sie zum Deaktivieren des Andock auf **(keine)** .

   Die Größe des Steuer Elements wird automatisch an die Grenzen des angedockten Rands angepasst.

   > [!NOTE]
   > Geerbte Steuerelemente `Protected` müssen in der Lage sein, angedockt zu werden. Um die Zugriffsebene eines Steuer Elements zu ändern, legen Sie seine **modifizierereigenschaft** im Fenster **Eigenschaften** fest.

## <a name="see-also"></a>Siehe auch

- [Windows Forms-Steuerelemente](index.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
- [Windows Forms-Steuerelemente nach Funktion](windows-forms-controls-by-function.md)
- [Vorgehensweise: Verankern und Andocken untergeordneter Steuerelemente in einem FlowLayoutPanel-Steuerelement](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Vorgehensweise: Verankern und Andocken untergeordneter Steuerelemente in einem TableLayoutPanel-Steuerelement](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md)
- [Vorgehensweise: Verankern von Steuerelementen auf Windows Forms](how-to-anchor-controls-on-windows-forms.md)
