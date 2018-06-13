---
title: Übersicht über die FontDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 3a4707ffe471161988d0526ce0908b37299f3e07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526877"
---
# <a name="fontdialog-component-overview-windows-forms"></a>Übersicht über die FontDialog-Komponente (Windows Forms)
Windows Forms <xref:System.Windows.Forms.FontDialog> Komponente ist ein vorkonfiguriertes Dialogfeld, das Windows-Standarddialogfeld also **Schriftart** Dialogfeld verwendet, um die Schriftarten verfügbar machen, die zurzeit auf dem System installiert sind. Verwenden Sie es in Ihrer Windows basierenden Anwendung als einfache Lösung für eine Schriftartauswahl anstatt ein eigenes Dialogfeld zu konfigurieren.  
  
 Standardmäßig zeigt das Dialogfeld Listenfelder für Schriftart, Schriftschnitt und-Grad; Kontrollkästchen für Effekte wie durchgestrichen und unterstrichen; eine Dropdown-Liste für Skripts; und ein Beispiel für die Anzeige der Schriftartformats. (Skript bezieht sich auf verschiedene Zeichenskripts, die für eine angegebene Schriftart verfügbar sind z. B. Hebräisch oder Japanisch.) Um das Dialogfeld "Schriftart" anzuzeigen, rufen die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.  
  
## <a name="key-properties"></a>Wichtige Eigenschaften  
 Die Komponente muss es sich um eine Reihe von Eigenschaften, die ihre Darstellung zu konfigurieren. Die Eigenschaften, die im Dialogfeld Optionen festgelegt, werden <xref:System.Windows.Forms.FontDialog.Font%2A> und <xref:System.Windows.Forms.FontDialog.Color%2A>. Die <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft legt fest, die Schriftart, Stil, Größe, Skript und Effekte; z. B. `Arial, 10pt, style=Italic, Strikeout`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.FontDialog>  
 [FontDialog-Komponente](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
