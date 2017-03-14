---
title: "Gewusst wie: Drucken von Client- und Nicht-Client-Bereichen eines Formulars (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Titelleiste, Drucken"
  - "Drucken"
  - "Rahmen, Drucken"
  - "Gesamtes Formular"
  - "Nicht-Clientbereich, Drucken"
ms.assetid: 856bb0e4-dbc3-47e2-81cd-4b376cf07757
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Gewusst wie: Drucken von Client- und Nicht-Client-Bereichen eines Formulars (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Mithilfe der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>\-Komponente können Sie schnell ein Bild eines Formulars genau so drucken, wie es auf dem Bildschirm angezeigt wird, ohne eine <xref:System.Drawing.Printing.PrintDocument>\-Komponente zu verwenden. Die folgende Vorgehensweise zeigt das Drucken eines Formulars, einschließlich des Clientbereichs und des Nicht\-Clientbereichs. Der Nicht\-Clientbereich beinhaltet die Titelleiste, Rahmen und Scrollleisten.  
  
 Die PowerPack\-Steuerelemente sind nicht mehr in Visual Studio enthalten, Sie können sie jedoch aus dem [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169) herunterladen.  
  
### So drucken Sie sowohl den Client\- als auch den Nicht\-Clientbereich eines Formulars  
  
1.  Klicken Sie in der **Toolbox** auf die Registerkarte **Visual Basic PowerPacks**, und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>\-Komponente auf das Formular.  
  
     Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>\-Komponente wird der Komponentenleiste hinzugefügt.  
  
2.  Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction> fest.  
  
3.  Fügen Sie den folgenden Code in den passenden Ereignishandler ein \(z. B. in den `Click`\-Ereignishandler für eine Drucken\-`Button`\).  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.FullWindow)  
    ```  
  
    > [!NOTE]
    >  Unter einigen Betriebssystemen werden von den <xref:System.Drawing.Graphics>\-Methoden gezeichnete Text\- oder Grafikelemente möglicherweise nicht ordnungsgemäß gedruckt. Verwenden Sie in diesem Fall diese kompatible Druckmethode: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.CompatibleModeFullWindow`  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>   
 [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)   
 [Gewusst wie: Drucken eines bildlauffähigen Formulars](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)