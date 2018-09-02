---
title: 'Gewusst wie: Drucken eines Formulars mithilfe der PrintForm-Komponente (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Form [Visual Basic], printing
ms.assetid: df963bf6-3ee1-49f4-8b2e-1d95d1beb0be
ms.openlocfilehash: 723524c7c9876d353624ad47d504ea2528a31cfe
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43422726"
---
# <a name="how-to-print-a-form-by-using-the-printform-component-visual-basic"></a>Gewusst wie: Drucken eines Formulars mithilfe der PrintForm-Komponente (Visual Basic)
Mithilfe der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente können Sie schnell ein Bild eines Formulars genau so drucken, wie es auf dem Bildschirm angezeigt wird, ohne eine <xref:System.Drawing.Printing.PrintDocument> -Komponente zu verwenden. Die folgenden Vorgehensweisen zeigen das Ausgeben eines Formulars auf einem Drucker, in einem Druckvorschaufenster und in einer Encapsulated PostScript-Datei.  
  
 Die PowerPack-Steuerelemente sind nicht mehr in Visual Studio enthalten, aber Sie können sie aus der [Downloadcenter](https://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
### <a name="to-print-a-form-to-the-default-printer"></a>So drucken Sie ein Formular auf dem Standarddrucker  
  
1.  Klicken Sie in der **Toolbox**auf die Registerkarte **Visual Basic PowerPacks** , und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente auf das Formular.  
  
     Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente wird der Komponentenleiste hinzugefügt.  
  
2.  Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>fest.  
  
3.  Fügen Sie den folgenden Code in die entsprechenden Ereignishandler (z. B. in der `Click` -Ereignishandler für ein **Drucken**`Button`).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-display-a-form-in-a-print-preview-window"></a>So zeigen Sie ein Formular in einem Druckvorschaufenster an  
  
1.  Klicken Sie in der **Toolbox**auf die Registerkarte **Visual Basic PowerPacks** , und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente auf das Formular.  
  
     Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente wird der Komponentenleiste hinzugefügt.  
  
2.  Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction.PrintToPreview>fest.  
  
3.  Fügen Sie den folgenden Code in die entsprechenden Ereignishandler (z. B. in der `Click` -Ereignishandler für ein **Drucken**`Button`).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-print-a-form-to-a-file"></a>So drucken Sie ein Formular in eine Datei  
  
1.  Klicken Sie in der **Toolbox**auf die Registerkarte **Visual Basic PowerPacks** , und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente auf das Formular.  
  
     Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente wird der Komponentenleiste hinzugefügt.  
  
2.  Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction.PrintToFile>fest.  
  
3.  Wählen Sie optional die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> -Eigenschaft aus, und geben Sie den vollständigen Pfad und Dateinamen für die Zieldatei an.  
  
     Wenn Sie diesen Schritt überspringen, wird der Benutzer zur Laufzeit zur Eingabe eines Dateinamens aufgefordert.  
  
4.  Fügen Sie den folgenden Code in die entsprechenden Ereignishandler (z. B. in der `Click` -Ereignishandler für ein **Drucken**`Button`).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>  
 [Gewusst wie: Drucken des Clientbereichs eines Formulars](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)  
 [Gewusst wie: Drucken von Client- und Nicht-Client-Bereichen eines Formulars](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)  
 [Gewusst wie: Drucken eines bildlauffähigen Formulars](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)  
 [PrintForm-Komponente](../../../visual-basic/developing-apps/printing/printform-component.md)
