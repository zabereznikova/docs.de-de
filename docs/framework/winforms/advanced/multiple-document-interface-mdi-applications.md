---
title: MDI-Anwendungen (Multiple Document Interface)
description: Erfahren Sie, wie Sie mit Windows Forms Multiple Document Interface (MDI)-Anwendungen mehrere Dokumente gleichzeitig anzeigen können, wobei jedes Dokument in einem eigenen Fenster angezeigt wird.
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0912a989ac1710d72c9db1cceb0e695f0ca85dee
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174652"
---
# <a name="multiple-document-interface-mdi-applications"></a>MDI-Anwendungen (Multiple Document Interface)
MDI-Anwendungen (Multiple Document Interface) ermöglichen es Ihnen, mehrere Dokumente gleichzeitig anzuzeigen, wobei jedes Dokument in einem eigenen Fenster angezeigt wird. MDI-Anwendungen haben häufig ein Fenstermenü Element mit Untermenüs zum Wechseln zwischen Fenstern oder Dokumenten.  
  
> [!NOTE]
> Es gibt einige Verhaltensunterschiede zwischen MDI-Formularen und SDI-Fenstern (Single-Document Interface) in Windows Forms. Die- `Opacity` Eigenschaft hat keine Auswirkung auf die Darstellung von untergeordneten MDI-Formularen. Außerdem hat die- <xref:System.Windows.Forms.Form.CenterToParent%2A> Methode keine Auswirkung auf das Verhalten von untergeordneten MDI-Formularen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Erstellen von übergeordneten MDI-Formularen](how-to-create-mdi-parent-forms.md)  
 Gibt Anweisungen zum Erstellen des Containers für mehrere Dokumente in einer MDI-Anwendung an.  
  
 [Vorgehensweise: Erstellen von untergeordneten MDI-Formularen](how-to-create-mdi-child-forms.md)  
 Hier finden Sie Anleitungen zum Erstellen eines oder mehrerer Fenster, die in einem übergeordneten MDI-Formular betrieben werden.  
  
 [Vorgehensweise: Bestimmen des aktiven untergeordneten MDI-Elements](how-to-determine-the-active-mdi-child.md)  
 Gibt Anweisungen zum Überprüfen des untergeordneten Fensters an, das den Fokus besitzt (und seinen Inhalt in die Zwischenablage sendet).  
  
 [Vorgehensweise: Senden von Daten an das aktive untergeordnete MDI-Element](how-to-send-data-to-the-active-mdi-child.md)  
 Gibt Anleitungen zum Transportieren von Informationen in das aktive untergeordnete Fenster an.  
  
 [Vorgehensweise: Anordnen von untergeordneten MDI-Formularen](how-to-arrange-mdi-child-forms.md)  
 Hier finden Sie Anleitungen zum Ticken, kaskadieren oder Anordnen der untergeordneten Fenster einer MDI-Anwendung.
