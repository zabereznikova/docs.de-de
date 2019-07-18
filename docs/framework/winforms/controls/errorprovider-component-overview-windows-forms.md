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
ms.openlocfilehash: f2a97ab80cde00a47bbdf6830bdba325e1c9f3ef
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880960"
---
# <a name="errorprovider-component-overview-windows-forms"></a>Übersicht über die ErrorProvider-Komponente (Windows Forms)
Die Windows-Formulare [ErrorProvider](errorprovider-component-windows-forms.md) Komponente dient zum Überprüfen von Benutzereingaben in einem Formular oder Steuerelement. Es wird in der Regel in Verbindung mit der Überprüfung von Benutzereingaben in einem Formular oder Anzeigen von Fehlern in einem Dataset verwendet. Ein Fehleranbieter ist eine bessere Alternative als die folgende Fehlermeldung in einem Meldungsfeld angezeigt, da nach der ein Meldungsfeld geschlossen, wird die Fehlermeldung nicht mehr sichtbar ist. Die <xref:System.Windows.Forms.ErrorProvider> Komponente zeigt ein Fehlersymbol (![einem weißen Ausrufezeichen in einem roten Kreis.](./media/errorprovider-component-overview-windows-forms/vb-error-provider-icon.gif)) neben dem entsprechenden Steuerelement, z. B. ein Textfeld, wenn der Benutzer den Mauszeiger über dem Fehlersymbol für positioniert eine QuickInfo angezeigt wird, die Zeichenfolge der Fehlermeldung wird angezeigt.  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Die <xref:System.Windows.Forms.ErrorProvider> wichtigsten Eigenschaften der Komponente sind <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, und <xref:System.Windows.Forms.ErrorProvider.Icon%2A>. Bei Verwendung <xref:System.Windows.Forms.ErrorProvider> Komponente mit dem von datengebundenen Steuerelementen, die <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> Eigenschaft muss auf den entsprechenden Container (in der Regel die Form "Windows") festgelegt werden, in der Reihenfolge für die Komponente auf dem Formular ein Fehlersymbol angezeigt. Wenn die Komponente im Designer hinzugefügt wird die <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> Eigenschaft auf das enthaltende Formular festgelegt, wenn Sie das Steuerelement im Code hinzufügen, müssen Sie es selbst festlegen.  
  
 Die <xref:System.Windows.Forms.ErrorProvider.Icon%2A> Eigenschaft kann festgelegt werden, um ein benutzerdefiniertes Fehlersymbol anstelle des Standardwerts. Wenn die <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> Eigenschaft festgelegt ist, die <xref:System.Windows.Forms.ErrorProvider> Komponente kann Fehlermeldungen für ein Dataset angezeigt. Die wichtigste Methode der der <xref:System.Windows.Forms.ErrorProvider> Komponente ist die <xref:System.Windows.Forms.ErrorProvider.SetError%2A> -Methode, die angibt, dass der fehlermeldungs-Zeichenfolge und, in dem das Symbol "Fehler" sollte angezeigt werden.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.ErrorProvider> Komponente bietet keine integrierten Unterstützung für Eingabehilfen-Clients. Um die Anwendung zugreifen können, wenn Sie diese Komponente verwenden, müssen Sie einen zusätzliche, gut erreichbaren Feedbackmechanismus angeben.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ErrorProvider>
- [Vorgehensweise: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [Vorgehensweise: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms](display-error-icons-for-form-validation-with-wf-errorprovider.md)
