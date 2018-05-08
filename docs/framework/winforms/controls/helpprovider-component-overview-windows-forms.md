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
ms.openlocfilehash: 5ad74b862c09734f3490210cb6898945a3c787fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="helpprovider-component-overview-windows-forms"></a>Übersicht über die HelpProvider-Komponente (Windows Forms)
Windows Forms [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) Komponente wird verwendet, um eine HTML Help 1.x-Hilfedatei (entweder eine mit HTML Help Workshop erstellte CHM-Datei oder eine HTM-Datei) der Windows-Anwendung zuzuordnen. Sie können die Hilfe in verschiedene Arten angeben:  
  
-   Geben Sie kontextbezogene Hilfe für Steuerelemente in Windows Forms.  
  
-   Geben Sie kontextbezogene Hilfe auf einem bestimmten Dialogfeld oder für bestimmte Steuerelemente in einem Dialogfeld an.  
  
-   Öffnen Sie eine Hilfedatei, die bestimmten Bereichen, z. B. ein Inhaltsverzeichnis, den Index oder eine Suchfunktion die Hauptseite angezeigt.  
  
## <a name="using-the-help-provider"></a>Verwenden des Hilfeanbieters  
 Hinzufügen einer <xref:System.Windows.Forms.HelpProvider> Komponente zu einem Windows Form kann die anderen Steuerelemente im Formular an den Hilfe-Eigenschaften verfügbar machen die <xref:System.Windows.Forms.HelpProvider> Komponente. Dadurch können Sie die Steuerelemente auf dem Windows-Formular Hilfe bereit. Sie können eine Hilfedatei zuordnen der <xref:System.Windows.Forms.HelpProvider> Komponente mit der <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> Eigenschaft. Geben Sie die bereitgestellten, durch Aufrufen von Hilfe <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> und einen Wert aus der <xref:System.Windows.Forms.HelpNavigator> Enumeration für das angegebene Steuerelement. Sie geben das Schlüsselwort oder ein Thema Hilfestellung bei der durch Aufrufen der <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> Methode.  
  
 Um ein anderes Steuerelement eine bestimmte Hilfezeichenfolge zuzuordnen, verwenden Sie optional die <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> Methode. Die Zeichenfolge, die Sie Zuordnen eines Steuerelements, das mit dieser Methode wird in einem Popupfenster angezeigt, wenn der Benutzer die F1-Taste drückt, während das Steuerelement den Fokus besitzt.  
  
 Wenn <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> wurde nicht festgelegt ist, verwenden Sie <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> den Hilfetext bereitstellen. Wenn Sie beide festgelegt haben <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> und den Hilfetext Hilfe basierend auf <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> Vorrang.  
  
> [!NOTE]
>  Treten möglicherweise Probleme bei der Verwendung des relativen Pfads bei der Angabe den Pfad zur Hilfedatei in der <xref:System.Windows.Forms.Help.ShowHelp%2A> Methode oder <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> Eigenschaft von der <xref:System.Windows.Forms.HelpProvider> Steuerelement. Achten Sie daher darauf, den absoluten Dateipfad verwenden, um die Hilfe-Datei anzugeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Hilfesysteme in Windows Forms-Anwendungen](../../../../docs/framework/winforms/advanced/help-systems-in-windows-forms-applications.md)
