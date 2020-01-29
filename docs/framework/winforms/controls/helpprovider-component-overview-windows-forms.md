---
title: Übersicht über die HelpProvider-Komponente
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
ms.openlocfilehash: 74d35dfa39a605cb1e1e85cc3aeda834e1c60669
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738725"
---
# <a name="helpprovider-component-overview-windows-forms"></a>Übersicht über die HelpProvider-Komponente (Windows Forms)
Mit der Windows Forms [HelpProvider](helpprovider-component-windows-forms.md) -Komponente wird der Windows-Anwendung eine Hilfedatei der HTML-Hilfe 1. x (entweder mit dem HTML-Hilfe Workshop oder mit einer HTM-Datei erstellt) zugeordnet. Ihnen stehen verschiedene Möglichkeiten zur Verfügung:  
  
- Bereitstellen kontextbezogener Hilfe für Steuerelemente auf Windows Forms.  
  
- Bereitstellen kontextbezogener Hilfe für ein bestimmtes Dialogfeld oder bestimmte Steuerelemente in einem Dialogfeld.  
  
- Öffnen Sie eine Hilfedatei für bestimmte Bereiche, z. b. die Hauptseite eines Inhaltsverzeichnisses, den Index oder eine Suchfunktion.  
  
## <a name="using-the-help-provider"></a>Verwenden des Hilfe Anbieters  
 Durch das Hinzufügen einer <xref:System.Windows.Forms.HelpProvider> Komponente zu Windows Form können die anderen Steuerelemente auf dem Formular die Hilfe Eigenschaften der <xref:System.Windows.Forms.HelpProvider> Komponente verfügbar machen. Dies ermöglicht Ihnen die Bereitstellung von Hilfe für die Steuerelemente in Ihrem Windows Form. Sie können der <xref:System.Windows.Forms.HelpProvider> Komponente mithilfe der <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>-Eigenschaft eine Hilfedatei zuordnen. Sie geben den Typ der Hilfe an, die durch Aufrufen von <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> bereitgestellt wird, und geben einen Wert aus der <xref:System.Windows.Forms.HelpNavigator> Enumeration für das angegebene Steuerelement an. Sie geben das Schlüsselwort oder Thema für die Hilfe an, indem Sie die <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>-Methode aufrufen.  
  
 Verwenden Sie optional die <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>-Methode, um eine bestimmte Hilfe Zeichenfolge einem anderen Steuerelement zuzuordnen. Die Zeichenfolge, die Sie mithilfe dieser Methode einem Steuerelement zuordnen, wird in einem Popup Fenster angezeigt, wenn der Benutzer die F1-Taste drückt, während das Steuerelement den Fokus besitzt.  
  
 Wenn <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> nicht festgelegt wurde, müssen Sie <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> verwenden, um den Hilfetext bereitzustellen. Wenn Sie sowohl <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> als auch die Hilfe Zeichenfolge festgelegt haben, hat die Hilfe, die auf <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> basiert, Vorrang.  
  
> [!NOTE]
> Es können Probleme auftreten, wenn Sie den relativen Pfad verwenden, wenn Sie den Pfad zur Hilfedatei in der <xref:System.Windows.Forms.Help.ShowHelp%2A>-Methode oder <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>-Eigenschaft des <xref:System.Windows.Forms.HelpProvider>-Steuer Elements angeben. Stellen Sie daher sicher, dass Sie den absoluten Dateipfad verwenden, um die Hilfedatei anzugeben.  
  
## <a name="see-also"></a>Siehe auch

- [Hilfesysteme in Windows Forms-Anwendungen](../advanced/help-systems-in-windows-forms-applications.md)
