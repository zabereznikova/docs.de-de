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
ms.openlocfilehash: 854f54454c0c88f965d9ac8240c11f6821f0c64b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594563"
---
# <a name="fontdialog-component-overview-windows-forms"></a>Übersicht über die FontDialog-Komponente (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.FontDialog> Komponente ist ein vorkonfiguriertes Dialogfeld, wird die standardmäßige Windows **Schriftart** Dialogfeld verwendet, um die Schriftarten verfügbar zu machen, die derzeit auf dem System installiert sind. Verwenden Sie es in Ihrer Windows-basierten Anwendung als einfache Lösung für die Schriftartauswahl, anstatt ein eigenes Dialogfeld zu konfigurieren.  
  
 Standardmäßig zeigt das Dialogfeld Listenfelder für Schriftart, Schriftschnitt und Größe Aktivieren Sie die Kontrollkästchen für die Effekte wie durchgestrichen und unterstrichen; ein Dropdown-Liste für Skripts; und ein Beispiel, wie die Schriftart angezeigt wird. (Skript bezieht sich auf verschiedene Zeichensätze-Skripts, die für eine angegebene Schriftart, verfügbar sind z. B. Hebräisch oder Japanisch.) Um das Dialogfeld "Schriftart" anzuzeigen, rufen die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.  
  
## <a name="key-properties"></a>Wichtige Eigenschaften  
 Die Komponente muss es sich um eine Reihe von Eigenschaften, die die Darstellung zu konfigurieren. Die Eigenschaften, die im Dialogfeld Optionen festgelegt, werden <xref:System.Windows.Forms.FontDialog.Font%2A> und <xref:System.Windows.Forms.FontDialog.Color%2A>. Die <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft legt fest, die Schriftart, Stil, Größe, Skripts und Effekte; z. B. `Arial, 10pt, style=Italic, Strikeout`.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.FontDialog>
- [FontDialog-Komponente](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
