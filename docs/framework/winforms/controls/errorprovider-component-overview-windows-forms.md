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
ms.openlocfilehash: 3cfd3f306d4a18ce8a194b5197060fbca1d157d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965290"
---
# <a name="errorprovider-component-overview-windows-forms"></a>Übersicht über die ErrorProvider-Komponente (Windows Forms)
Die Windows Forms [ErrorProvider](errorprovider-component-windows-forms.md) -Komponente wird verwendet, um Benutzereingaben in einem Formular oder Steuerelement zu validieren. Sie wird in der Regel in Verbindung mit dem Validieren von Benutzereingaben in einem Formular oder dem Anzeigen von Fehlern in einem DataSet verwendet. Ein Fehler Anbieter ist eine bessere Alternative als das Anzeigen einer Fehlermeldung in einem Meldungs Feld, da die Fehlermeldung nach dem verwerfen eines Meldungs Felds nicht mehr sichtbar ist. Die <xref:System.Windows.Forms.ErrorProvider> Komponente zeigt ein Fehler Symbol an![(ein weißes Ausrufezeichen innerhalb eines roten Kreises](./media/errorprovider-component-overview-windows-forms/vb-error-provider-icon.gif)) neben dem entsprechenden Steuerelement, z. b. einem Textfeld. wenn der Benutzer den Mauszeiger auf das Fehler Symbol positioniert, wird eine QuickInfo angezeigt. die Zeichenfolge der Fehlermeldung wird angezeigt.  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Die <xref:System.Windows.Forms.ErrorProvider> Schlüsseleigenschaften der Komponente sind <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>und <xref:System.Windows.Forms.ErrorProvider.Icon%2A>. Wenn Sie <xref:System.Windows.Forms.ErrorProvider> die-Komponente mit Daten gebundenen Steuerelementen <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> verwenden, muss die-Eigenschaft auf den entsprechenden Container festgelegt werden (normalerweise das Windows Form), damit die Komponente ein Fehler Symbol im Formular anzeigt. Wenn die Komponente im-Designer hinzugefügt wird, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> wird die-Eigenschaft auf das enthaltende Formular festgelegt. Wenn Sie das Steuerelement im Code hinzufügen, müssen Sie es selbst festlegen.  
  
 Die <xref:System.Windows.Forms.ErrorProvider.Icon%2A> -Eigenschaft kann auf ein benutzerdefiniertes Fehler Symbol anstatt auf den Standardwert festgelegt werden. Wenn die <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> -Eigenschaft festgelegt ist <xref:System.Windows.Forms.ErrorProvider> , kann die Komponente Fehlermeldungen für ein Dataset anzeigen. Die Schlüsselmethode der <xref:System.Windows.Forms.ErrorProvider> -Komponente ist die <xref:System.Windows.Forms.ErrorProvider.SetError%2A> -Methode, die die Fehlermeldungs Zeichenfolge angibt und in der das Fehler Symbol angezeigt werden soll.  
  
> [!NOTE]
> Die <xref:System.Windows.Forms.ErrorProvider> Komponente bietet keine integrierte Unterstützung für Barrierefreiheits Clients. Um auf die Anwendung zugreifen zu können, wenn Sie diese Komponente verwenden, müssen Sie einen zusätzlichen, zugänglichen Feedback Mechanismus bereitstellen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ErrorProvider>
- [Vorgehensweise: Anzeigen von Fehlern in einem DataSet mit der Windows Forms ErrorProvider-Komponente](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [Vorgehensweise: Anzeigen von Fehler Symbolen für die Formular Validierung mit der Windows Forms ErrorProvider-Komponente](display-error-icons-for-form-validation-with-wf-errorprovider.md)
