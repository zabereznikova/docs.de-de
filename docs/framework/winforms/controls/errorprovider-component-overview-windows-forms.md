---
title: Übersicht über die ErrorProvider-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: 2272220917f2d5adf15f1ba84a5d4c3d0ec07165
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="errorprovider-component-overview-windows-forms"></a>Übersicht über die ErrorProvider-Komponente (Windows Forms)
Windows Forms [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) Komponente dient zum Überprüfen von Benutzereingaben in einem Formular oder Steuerelement. Es wird in der Regel in Verbindung mit Validieren von Benutzereingaben in einem Formular oder die Anzeige von Fehlern innerhalb eines Datasets verwendet. Ein ErrorProvider-Symbol ist eine bessere Alternative als eine Fehlermeldung in einem Meldungsfeld angezeigt, da sobald ein Meldungsfeld geschlossen wird, die Fehlermeldung nicht mehr sichtbar ist. Die <xref:System.Windows.Forms.ErrorProvider> Komponente zeigt ein Fehlersymbol (![Symbol "ErrorProvider"](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "VbErrorProviderIcon")) neben dem betreffenden Steuerelement, z. B. ein Textfeld; Wenn der Benutzer den Mauszeiger über positioniert das Symbol für Zertifikatfehler, wird eine QuickInfo, die Zeichenfolge der Fehlermeldung angezeigt.  
  
## <a name="key-properties"></a>Wichtige Eigenschaften  
 Die <xref:System.Windows.Forms.ErrorProvider> sind wichtige Komponenteneigenschaften <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, und <xref:System.Windows.Forms.ErrorProvider.Icon%2A>. Bei Verwendung <xref:System.Windows.Forms.ErrorProvider> Komponente mit dem von datengebundenen Steuerelementen, die <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> Eigenschaft muss auf den entsprechenden Container (in der Regel das Windows Form) festgelegt werden, in der Reihenfolge für die Komponente auf dem Formular ein Fehlersymbol angezeigt. Wenn die Komponente im Designer hinzugefügt wird die <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> Eigenschaft das zugehörige Formular festgelegt wird; Wenn Sie das Steuerelement im Code hinzufügen, müssen Sie es selbst festlegen.  
  
 Die <xref:System.Windows.Forms.ErrorProvider.Icon%2A> Eigenschaft kann auf ein benutzerdefiniertes Fehlersymbol anstelle des standardmäßigen festgelegt werden. Wenn die <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> Eigenschaft festgelegt ist, die <xref:System.Windows.Forms.ErrorProvider> Komponente kann Fehlermeldungen für ein Dataset angezeigt. Die wichtigste Methode der der <xref:System.Windows.Forms.ErrorProvider> Komponente ist die <xref:System.Windows.Forms.ErrorProvider.SetError%2A> -Methode, die angibt, dass die Zeichenfolge der Fehlermeldung und, in dem das Symbol "Fehler" angezeigt werden soll.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.ErrorProvider> Komponente leistet keine integrierten Unterstützung für Eingabehilfen-Clients. Um die Anwendung zugreifen können, wenn diese Komponente verwenden, müssen Sie einen zusätzliche zugänglichen Feedbackmechanismus bereitstellen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ErrorProvider>  
 [Gewusst wie: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)  
 [Gewusst wie: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
