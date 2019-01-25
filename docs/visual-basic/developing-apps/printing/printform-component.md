---
title: PrintForm-Komponente (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- PrintForm component [Visual Basic]
ms.assetid: 03de98b8-b54c-4764-91d7-83c64e974750
ms.openlocfilehash: a093dbb674a0d182b9a981cf39668d9ca11d0e8c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746194"
---
# <a name="printform-component-visual-basic"></a>PrintForm-Komponente (Visual Basic)
Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> für Visual Basic ermöglicht es Ihnen, ein Bild eines Windows Forms zur Laufzeit zu drucken. Ihr Verhalten ersetzt das der Methode `PrintForm` in früheren Visual Basic-Versionen.  
  
 Die PowerPack-Steuerelemente sind nicht mehr in Visual Studio enthalten, Sie können sie jedoch aus dem [Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=25169)herunterladen.  
  
## <a name="printform-component-overview"></a>PrintForm-Komponente – Übersicht  
 Ein häufiges Szenario bei Windows Forms bildet die Erstellung eines Formulars, das einem Papierformular oder einem Bericht ähnelt, von dem dann ein Bild gedruckt werden soll. Zwar können Sie dazu eine <xref:System.Drawing.Printing.PrintDocument> -Komponente verwenden, das würde aber viel Code erfordern. Mithilfe der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente können Sie ein Bild eines Formulars auf einem Drucker, in einem Druckvorschaufenster oder in einer Datei ausgeben, ohne eine <xref:System.Drawing.Printing.PrintDocument> -Komponente zu verwenden.  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente befindet sich auf der Registerkarte **Visual Basic PowerPacks** der **Toolbox**. Wenn sie auf ein Formular gezogen wird, wird sie in der Komponentenleiste angezeigt, dem kleinen Bereich unter dem unteren Rand des Formulars. Wenn die Komponente ausgewählt wird, können Eigenschaften zum Definieren ihres Verhaltens im Fenster **Eigenschaften** festgelegt werden. Alle diese Eigenschaften können auch im Code festgelegt werden. Außerdem können Sie eine Instanz der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente im Code erstellen, ohne die Komponente zur Entwurfszeit hinzuzufügen.  
  
 Wenn Sie ein Formular drucken, wird alles im Clientbereich des Formulars gedruckt. Dies schließt alle Steuerelemente und alle von den Grafikmethoden auf dem Formular gezeichneten Text- oder Grafikelemente ein. Standardmäßig werden die Titelleiste, die Scrollleisten und der Rahmen eines Formulars nicht gedruckt. Ferner druckt die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente standardmäßig nur den sichtbaren Teil des Formulars. Wenn der Benutzer beispielsweise die Größe des Formulars zur Laufzeit ändert, werden nur die Steuer- und Grafikelemente gedruckt, die aktuell sichtbar sind.  
  
 Der von der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente verwendete Standarddrucker wird durch die Einstellungen des Betriebssystems in der Systemsteuerung festgelegt.  
  
 Nach dem Einleiten des Drucks wird ein standardmäßiges <xref:System.Drawing.Printing.PrintDocument> -Druckdialogfeld angezeigt. In diesem Dialogfeld können Benutzer den Druckauftrag abbrechen.  
  
### <a name="key-methods-properties-and-events"></a>Wichtige Methoden, Eigenschaften und Ereignisse  
 Die wichtigste Methode der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente ist die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> -Methode, die ein Bild des Formulars an einen Drucker, ein Druckvorschaufenster oder eine Datei ausgibt. Es gibt zwei Versionen der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> -Methode:  
  
-   Eine einfache Version ohne Parameter: `Print()`  
  
-   Eine überladene Version mit Parametern, die das Druckverhalten angeben: `Print(printForm As Form, printFormOption As PrintOption)`  
  
     Der `PrintOption` -Parameter der überladenen Methode legt die zugrundeliegende Implementierung fest, die zum Drucken des Formulars verwendet wird, ob die Titelleiste, die Scrollleisten und der Rahmen und ob scrollbare Teile des Formulars gedruckt werden sollen.  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> -Eigenschaft stellt eine Schlüsseleigenschaft der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente dar. Diese Eigenschaft legt fest, ob die Ausgabe an einen Drucker gesendet, in einem Druckvorschaufenster angezeigt oder als Encapsulated PostScript-Datei gespeichert wird. Wenn die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> -Eigenschaft auf <xref:System.Drawing.Printing.PrintAction.PrintToFile>festgelegt ist, gibt die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> -Eigenschaft den Pfad und den Dateinamen an.  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrinterSettings%2A> -Eigenschaft ermöglicht den Zugriff auf ein zugrundeliegendes <xref:System.Drawing.Printing.PrintDocument.PrinterSettings%2A> -Objekt, mit dem Sie Einstellungen wie den zu verwendenden Drucker und die Anzahl der zu druckenden Kopien festlegen können. Sie können auch die Leistungsmerkmale des Druckers abfragen, etwa die Unterstützung für Farbe oder Duplexdruck. Diese Eigenschaft wird nicht im Fenster **Eigenschaften** angezeigt; der Zugriff auf sie ist nur über den Code möglich.  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Form%2A> -Eigenschaft dient dazu, beim programmgesteuerten Aufrufen der Komponente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> das zu druckende Formular anzugeben. Wenn die Komponente zur Laufzeit einem Formular hinzugefügt wird, stellt dieses Formular den Standardwert dar.  
  
 Zu den Tastaturereignissen der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente gehören:  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.BeginPrint> -Ereignis. Tritt beim Aufrufen der Methode <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> vor dem Drucken der ersten Seite des Dokuments auf.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.EndPrint> -Ereignis. Tritt auf, nachdem die letzte Seite gedruckt wurde.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.QueryPageSettings> -Ereignis. Tritt auf, unmittelbar bevor jede Seite gedruckt wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Formular Text oder Grafiken enthält, der bzw. die von <xref:System.Drawing.Graphics> -Methoden gezeichnet werden, verwenden Sie die einfache <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> (`Print()`)-Methode, um das Formular zu drucken. Grafiken werden bei einigen Betriebssystemen möglicherweise nicht gerendert, wenn die überladene <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> -Methode verwendet wird.  
  
 Wenn die Breite eines Formulars die Breite des Papiers im Drucker überschreitet, wird die rechte Seite des Formulars möglicherweise abgeschnitten. Achten Sie beim Entwerfen von Formularen für den Druck darauf, dass die Formulare auf Papier in Standardformaten passen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel ist eine häufige Verwendung der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente dargestellt.  
  
```  
' Visual Basic.  
Dim pf As New PrintForm  
pf.Form = Me  
pf.PrintAction = PrintToPrinter  
pf.Print()  
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>
- [Vorgehensweise: Drucken eines Formulars mithilfe der PrintForm-Komponente](../../../visual-basic/developing-apps/printing/how-to-print-a-form-by-using-the-printform-component.md)
- [Vorgehensweise: Drucken des Clientbereichs eines Formulars](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)
- [Vorgehensweise: Drucken von Client- und Nicht-Client-Bereichen eines Formulars](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
- [Vorgehensweise: Drucken eines bildlauffähigen Formulars](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
