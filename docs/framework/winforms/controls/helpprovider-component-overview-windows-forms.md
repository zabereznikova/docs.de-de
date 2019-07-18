---
title: Übersicht über die HelpProvider-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
ms.openlocfilehash: 9e8dc2ee2773b26a7bfef1da209399a8b49de9ad
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624122"
---
# <a name="helpprovider-component-overview-windows-forms"></a>Übersicht über die HelpProvider-Komponente (Windows Forms)
Die Windows-Formulare [HelpProvider](helpprovider-component-windows-forms.md) Komponente verwendet, um eine HTML Help 1.x-Hilfedatei (entweder eine mit HTML Help Workshop erstellte CHM-Datei oder eine HTM-Datei) mit der Windows-Anwendung zuzuordnen. Sie können die Hilfe in einer Vielzahl von Methoden angeben:  
  
- Geben Sie kontextbezogene Hilfe für in Windows Forms-Steuerelemente.  
  
- Bereitstellen Sie kontextbezogener Hilfe auf einem bestimmten Dialogfeld oder für bestimmte Steuerelemente in einem Dialogfeld an.  
  
- Öffnen Sie eine Hilfe zu bestimmten Bereichen, z. B. die Hauptseite der Inhaltsverzeichnis, den Index oder eine Suchfunktion.  
  
## <a name="using-the-help-provider"></a>Verwenden des Hilfeanbieters  
 Hinzufügen einer <xref:System.Windows.Forms.HelpProvider> Komponente zu Ihrem Windows-Formular können Sie die anderen Steuerelemente im Formular aus, um die Hilfeeigenschaften verfügbar zu machen die <xref:System.Windows.Forms.HelpProvider> Komponente. Dadurch können Sie die Steuerelemente auf dem Windows-Formular Hilfe bereit. Sie können eine Textdatei mit Zuordnen der <xref:System.Windows.Forms.HelpProvider> -Komponente mithilfe der <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> Eigenschaft. Sie geben den Typ der bereitgestellten durch Aufrufen von Hilfe <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> und einen Wert aus der <xref:System.Windows.Forms.HelpNavigator> Enumeration für das angegebene Steuerelement. Sie bieten das Schlüsselwort oder ein Thema Hilfe durch Aufrufen der <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> Methode.  
  
 Um eine bestimmte Hilfezeichenfolge mit einem anderen Steuerelement zuzuordnen, verwenden Sie optional die <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> Methode. Die Zeichenfolge, die Sie zuordnen, dass ein Steuerelement, das mit dieser Methode wird in einem Popupfenster angezeigt, wenn der Benutzer die F1-Taste drückt, während das Steuerelement den Fokus besitzt.  
  
 Wenn <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> wurde nicht festgelegt ist, verwenden Sie <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> den Hilfetext bereitstellen. Wenn Sie beide festgelegt haben <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> und die Hilfezeichenfolge Hilfe auf Grundlage <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> Vorrang.  
  
> [!NOTE]
>  Treten möglicherweise Probleme, die den relativen Pfad verwenden, beim Angeben des Pfads zu der Hilfedatei, in der <xref:System.Windows.Forms.Help.ShowHelp%2A> Methode oder <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> Eigenschaft der <xref:System.Windows.Forms.HelpProvider> Steuerelement. Daher werden Sie sicher, dass den absolute Dateipfad zu verwenden, um die Hilfedatei anzugeben.  
  
## <a name="see-also"></a>Siehe auch

- [Hilfesysteme in Windows Forms-Anwendungen](../advanced/help-systems-in-windows-forms-applications.md)
