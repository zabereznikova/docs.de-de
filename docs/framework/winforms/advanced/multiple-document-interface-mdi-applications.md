---
title: MDI-Anwendungen (Multiple Document Interface)
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 23e0275d5e6b081ec02d669a78e8695453360637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956560"
---
# <a name="multiple-document-interface-mdi-applications"></a>MDI-Anwendungen (Multiple Document Interface)
MDI-Anwendungen (Multiple Document Interface) ermöglichen es Ihnen, mehrere Dokumente gleichzeitig anzuzeigen, wobei jedes Dokument in einem eigenen Fenster angezeigt wird. MDI-Anwendungen haben häufig ein Fenstermenü Element mit Untermenüs zum Wechseln zwischen Fenstern oder Dokumenten.  
  
> [!NOTE]
> Es gibt einige Verhaltensunterschiede zwischen MDI-Formularen und SDI-Fenstern (Single-Document Interface) in Windows Forms. Die `Opacity` -Eigenschaft hat keine Auswirkung auf die Darstellung von untergeordneten MDI-Formularen. Außerdem hat die <xref:System.Windows.Forms.Form.CenterToParent%2A> -Methode keine Auswirkung auf das Verhalten von untergeordneten MDI-Formularen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Übergeordnete MDI-Formulare erstellen](how-to-create-mdi-parent-forms.md)  
 Gibt Anweisungen zum Erstellen des Containers für mehrere Dokumente in einer MDI-Anwendung an.  
  
 [Vorgehensweise: Erstellen von untergeordneten MDI-Formularen](how-to-create-mdi-child-forms.md)  
 Hier finden Sie Anleitungen zum Erstellen eines oder mehrerer Fenster, die in einem übergeordneten MDI-Formular betrieben werden.  
  
 [Vorgehensweise: Festlegen des aktiven untergeordneten MDI-Elements](how-to-determine-the-active-mdi-child.md)  
 Gibt Anweisungen zum Überprüfen des untergeordneten Fensters an, das den Fokus besitzt (und seinen Inhalt in die Zwischenablage sendet).  
  
 [Vorgehensweise: Senden von Daten an das aktive untergeordnete MDI-Element](how-to-send-data-to-the-active-mdi-child.md)  
 Gibt Anleitungen zum Transportieren von Informationen in das aktive untergeordnete Fenster an.  
  
 [Vorgehensweise: Untergeordnete MDI-Formulare anordnen](how-to-arrange-mdi-child-forms.md)  
 Hier finden Sie Anleitungen zum Ticken, kaskadieren oder Anordnen der untergeordneten Fenster einer MDI-Anwendung.
