---
title: "Gewusst wie: Drucken eines Formulars mithilfe der PrintForm-Komponente (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Formular, Drucken"
ms.assetid: df963bf6-3ee1-49f4-8b2e-1d95d1beb0be
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Gewusst wie: Drucken eines Formulars mithilfe der PrintForm-Komponente (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Mithilfe der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>\-Komponente können Sie schnell ein Bild eines Formulars genau so drucken, wie es auf dem Bildschirm angezeigt wird, ohne eine <xref:System.Drawing.Printing.PrintDocument>\-Komponente zu verwenden. Die folgenden Vorgehensweisen zeigen das Ausgeben eines Formulars auf einem Drucker, in einem Druckvorschaufenster und in einer Encapsulated PostScript\-Datei.  
  
 Die PowerPack\-Steuerelemente sind nicht mehr in Visual Studio enthalten, Sie können sie jedoch aus dem [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169) herunterladen.  
  
### So drucken Sie ein Formular auf dem Standarddrucker  
  
1.  Klicken Sie in der **Toolbox** auf die Registerkarte **Visual Basic PowerPacks**, und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>\-Komponente auf das Formular.  
  
     Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>\-Komponente wird der Komponentenleiste hinzugefügt.  
  
2.  Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction> fest.  
  
3.  Fügen Sie den folgenden Code in den passenden Ereignishandler ein \(z.B. in den `Click`\-Ereignishandler für eine **Drucken**\-`Button`\).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### So zeigen Sie ein Formular in einem Druckvorschaufenster an  
  
1.  Klicken Sie in der **Toolbox** auf die Registerkarte **Visual Basic PowerPacks**, und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>\-Komponente auf das Formular.  
  
     Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>\-Komponente wird der Komponentenleiste hinzugefügt.  
  
2.  Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction> fest.  
  
3.  Fügen Sie den folgenden Code in den passenden Ereignishandler ein \(z.B. in den `Click`\-Ereignishandler für eine **Drucken**\-`Button`\).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### So drucken Sie ein Formular in eine Datei  
  
1.  Klicken Sie in der **Toolbox** auf die Registerkarte **Visual Basic PowerPacks**, und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>\-Komponente auf das Formular.  
  
     Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>\-Komponente wird der Komponentenleiste hinzugefügt.  
  
2.  Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction> fest.  
  
3.  Wählen Sie optional die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>\-Eigenschaft aus, und geben Sie den vollständigen Pfad und Dateinamen für die Zieldatei an.  
  
     Wenn Sie diesen Schritt überspringen, wird der Benutzer zur Laufzeit zur Eingabe eines Dateinamens aufgefordert.  
  
4.  Fügen Sie den folgenden Code in den passenden Ereignishandler ein \(z.B. in den `Click`\-Ereignishandler für eine **Drucken**\-`Button`\).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>   
 [Gewusst wie: Drucken des Clientbereichs eines Formulars](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)   
 [Gewusst wie: Drucken von Client\- und Nicht\-Client\-Bereichen eines Formulars](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)   
 [Gewusst wie: Drucken eines bildlauffähigen Formulars](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)   
 [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)