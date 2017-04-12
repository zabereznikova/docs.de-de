---
title: PrintForm-Komponente (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- PrintForm component [Visual Basic]
ms.assetid: 03de98b8-b54c-4764-91d7-83c64e974750
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f0c51ef0131c874ed33af7a19f9145a790d14ade
ms.lasthandoff: 03/13/2017

---
# <a name="printform-component-visual-basic"></a>PrintForm-Komponente (Visual Basic)
Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>für die Komponente [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ermöglicht es Ihnen, ein Bild eines Windows Form zur Laufzeit gedruckt.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Ihr Verhalten ersetzt das der Methode `PrintForm` in früheren Visual Basic-Versionen.  
  
 Die PowerPack-Steuerelemente sind nicht mehr in Visual Studio enthalten, Sie können sie jedoch aus dem [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169)herunterladen.  
  
## <a name="printform-component-overview"></a>PrintForm-Komponente – Übersicht  
 Ein häufiges Szenario bei Windows Forms bildet die Erstellung eines Formulars, das einem Papierformular oder einem Bericht ähnelt, von dem dann ein Bild gedruckt werden soll. Sie können zwar eine <xref:System.Drawing.Printing.PrintDocument>Komponente dazu wäre es viel Code erforderlich.</xref:System.Drawing.Printing.PrintDocument> Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>-Komponente ermöglicht es Ihnen, drucken Sie ein Bild eines Formulars an einen Drucker, in eine Seitenansicht oder in eine Datei ohne Verwendung einer <xref:System.Drawing.Printing.PrintDocument>Komponente.</xref:System.Drawing.Printing.PrintDocument> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente befindet sich auf der **Visual Basic PowerPacks** auf der Registerkarte der **Toolbox**.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Wenn sie auf ein Formular gezogen wird, wird sie in der Komponentenleiste angezeigt, dem kleinen Bereich unter dem unteren Rand des Formulars. Wenn die Komponente ausgewählt wird, können Eigenschaften zum Definieren ihres Verhaltens im Fenster **Eigenschaften** festgelegt werden. Alle diese Eigenschaften können auch im Code festgelegt werden. Sie können auch eine Instanz von erstellen die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>-Komponente im Code ohne die Komponente zur Entwurfszeit hinzuzufügen.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 Wenn Sie ein Formular drucken, wird alles im Clientbereich des Formulars gedruckt. Dies schließt alle Steuerelemente und alle von den Grafikmethoden auf dem Formular gezeichneten Text- oder Grafikelemente ein. Standardmäßig werden die Titelleiste, die Scrollleisten und der Rahmen eines Formulars nicht gedruckt. Ebenfalls standardmäßig die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente wird nur den sichtbaren Teil des Formulars gedruckt.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Wenn der Benutzer beispielsweise die Größe des Formulars zur Laufzeit ändert, werden nur die Steuer- und Grafikelemente gedruckt, die aktuell sichtbar sind.  
  
 Wird als Standarddrucker der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente wird durch das Betriebssystem Systemsteuerung Einstellungen bestimmt.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 Nachdem der Druckauftrag gestartet wurde, ein Standard <xref:System.Drawing.Printing.PrintDocument>Drucken-Dialogfeld wird angezeigt.</xref:System.Drawing.Printing.PrintDocument> In diesem Dialogfeld können Benutzer den Druckauftrag abbrechen.  
  
### <a name="key-methods-properties-and-events"></a>Wichtige Methoden, Eigenschaften und Ereignisse  
 Die wichtigste Methode der der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente ist die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>-Methode, die ein Bild des Formulars an einen Drucker, eine Druckvorschaufenster oder eine Datei ausgegeben wird.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Es gibt zwei Versionen der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>Methode:</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
  
-   Eine Basisversion ohne Parameter:`Print()`  
  
-   Eine überladene Version mit Parametern, die Drucken Verhalten festlegen:`Print(printForm As Form, printFormOption As PrintOption)`  
  
     Der `PrintOption` -Parameter der überladenen Methode legt die zugrundeliegende Implementierung fest, die zum Drucken des Formulars verwendet wird, ob die Titelleiste, die Scrollleisten und der Rahmen und ob scrollbare Teile des Formulars gedruckt werden sollen.  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>-Eigenschaft ist eine wichtige Eigenschaft von der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> Diese Eigenschaft legt fest, ob die Ausgabe an einen Drucker gesendet , in einem Druckvorschaufenster angezeigt oder als Encapsulated PostScript-Datei gespeichert wird. Wenn die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>Eigenschaft auf festgelegt ist <xref:System.Drawing.Printing.PrintAction>, die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>-Eigenschaft gibt den Pfad und Dateinamen ein.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> </xref:System.Drawing.Printing.PrintAction> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrinterSettings%2A>Eigenschaft ermöglicht den Zugriff auf ein zugrunde liegendes <xref:System.Drawing.Printing.PrintDocument.PrinterSettings%2A>Objekt, mit der Sie Einstellungen wie den zu verwendenden Drucker und die Anzahl der Kopien zum Drucken angeben</xref:System.Drawing.Printing.PrintDocument.PrinterSettings%2A> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrinterSettings%2A> Sie können auch die Leistungsmerkmale des Druckers abfragen, etwa die Unterstützung für Farbe oder Duplexdruck. Diese Eigenschaft wird nicht im Fenster **Eigenschaften** angezeigt; der Zugriff auf sie ist nur über den Code möglich.  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Form%2A>Eigenschaft wird verwendet, an das Formular gedruckt, rufen Sie die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente programmgesteuert.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Form%2A> Wenn die Komponente zur Laufzeit einem Formular hinzugefügt wird, stellt dieses Formular den Standardwert dar.  
  
 Ereignisse für die Schlüssel der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente umfassen Folgendes:</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.BeginPrint>das Ereignis.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.BeginPrint> Tritt auf, wenn die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>aufgerufen und bevor die erste Seite des Dokuments gedruckt.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.EndPrint>das Ereignis.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.EndPrint> Tritt auf, nachdem die letzte Seite gedruckt wurde.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.QueryPageSettings>das Ereignis.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.QueryPageSettings> Tritt auf, unmittelbar bevor jede Seite gedruckt wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Formular Text oder Grafiken, die vom <xref:System.Drawing.Graphics>Methoden verwenden, die grundlegende <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>(`Print()`)-Methode ausgegeben it.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> </xref:System.Drawing.Graphics> Grafiken möglicherweise unter einigen Betriebssystemen nicht gerendert bei überladenen <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>Methode wird verwendet.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
  
 Wenn die Breite eines Formulars die Breite des Papiers im Drucker überschreitet, wird die rechte Seite des Formulars möglicherweise abgeschnitten. Achten Sie beim Entwerfen von Formularen für den Druck darauf, dass die Formulare auf Papier in Standardformaten passen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine häufige Verwendung der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Komponente.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
```  
' Visual Basic.  
Dim pf As New PrintForm  
pf.Form = Me  
pf.PrintAction = PrintToPrinter  
pf.Print()  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A></xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A></xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>   
 [Gewusst wie: Drucken eines Formulars mithilfe der PrintForm-Komponente](../../../visual-basic/developing-apps/printing/how-to-print-a-form-by-using-the-printform-component.md)   
 [Gewusst wie: Drucken des Clientbereichs eines Formulars](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)   
 [Gewusst wie: Drucken von Client- und nicht-Client-Bereichen eines Formulars](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)   
 [Gewusst wie: Drucken eines bildlauffähigen Formulars](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
