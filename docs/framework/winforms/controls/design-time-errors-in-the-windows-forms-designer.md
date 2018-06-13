---
title: Entwurfszeitfehler im Windows Forms-Designer
ms.date: 03/30/2017
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
ms.openlocfilehash: 00296b51563a5f973b8e5d64c55867568ff0324e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527786"
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a>Entwurfszeitfehler im Windows Forms-Designer
In diesem Thema wird die Bedeutung und der Verwendungszweck der Entwurfszeitfehlerliste erläutert, die in Microsoft Visual Studio angezeigt wird, wenn der Windows Forms-Designer nicht geladen werden kann. Wenn diese Fehlerliste angezeigt wird, sollten Sie sie nicht als Fehler im Designer, sondern als Hilfe beim Beheben von Fehlern in Ihrem Code interpretieren.  
  
 Ein grundlegendes Verständnis dieser Fehlerliste hilft Ihnen beim Debuggen Ihrer Anwendungen, indem detaillierte Informationen zu den Fehlern und mögliche Lösungen vorgeschlagen werden.  
  
## <a name="the-design-time-error-list-interface"></a>Die Schnittstelle für Entwurfszeitfehlerliste  
 Wenn der Windows Forms-Designer nicht geladen werden kann, wird im Designer eine Fehlerliste angezeigt. Die Fehler werden in Kategorien gruppiert. Wenn Sie beispielsweise über vier Instanzen von nicht deklarierten Variablen verfügen, werden diese in der gleichen Fehlerkategorie gruppiert. Jede Fehlerkategorie enthält eine kurze Beschreibung, die den Fehler zusammenfasst.  
  
 Sie können eine Fehlerkategorie erweitern oder reduzieren, indem Sie auf die Überschrift der Fehlerkategorie klicken oder indem Sie auf das Chevron zum Erweitern/Reduzieren klicken. Wenn Sie eine Fehlerkategorie erweitern, wird folgende zusätzliche Hilfe angezeigt:  
  
-   Instanzen dieses Fehlers.  
  
-   Hilfe zu diesem Fehler.  
  
-   Forenbeiträge zu diesem Fehler.  
  
### <a name="instances-of-this-error"></a>Instanzen dieses Fehlers  
 In der zusätzlichen Hilfe werden alle Instanzen des Fehlers im aktuellen Projekt aufgeführt. Viele Fehler enthalten eine genaue Position im folgenden Format: *[Projektname]* *[Formularname]* Zeile:*[Zeilennummer]* Spalte:*[Spaltennummer]*. Über den Link **Gehe zu Code** gelangen Sie zu der Position im Code, an der der Fehler auftritt.  
  
 Wenn dem Fehler eine Aufrufliste zugeordnet ist, können Sie zur näheren Erläuterung des Fehlers auf den Link **Aufrufliste anzeigen** klicken, um die Aufrufliste anzuzeigen. Durch Überprüfen des Stapels können Sie wertvolle Debuginformationen erhalten. Sie können beispielsweise die Funktionen nachverfolgen, die vor Auftreten des Fehlers aufgerufen wurden. Die Aufrufliste ist auswählbar, sodass sie kopiert und gespeichert werden kann.  
  
> [!NOTE]
>  In Visual Basic wird in der Entwurfszeit-Fehlerliste nicht mehr als ein Fehler angezeigt, es können jedoch mehrere Instanzen desselben Fehlers angezeigt werden. In Visual C++ weisen die Fehler keine Verknüpfungen mit GoTo-Codes/Zeilennummern auf.  
  
### <a name="help-with-this-error"></a>Hilfe zu diesem Fehler  
 Wenn der Fehler einen Link zu einem MSDN-Hilfethema enthält, umfasst die zusätzliche Hilfe einen Link zum Hilfethema. Wenn Sie auf den Link klicken, wird das zugehörige Hilfethema in Visual Studio angezeigt.  
  
### <a name="forum-posts-about-this-error"></a>Forumbeiträge zu diesem Fehler  
 Die zusätzliche Hilfe umfasst einen Link zu MSDN-Forenbeiträgen zu dem Fehler. Die Foren werden basierend auf der Zeichenfolge der Fehlermeldung durchsucht. Sie können auch die folgenden Foren durchsuchen:  
  
-   [Forum von Windows Forms-Designer](http://go.microsoft.com/fwlink/?LinkId=203524)  
  
-   [Windows Forms-Foren](http://go.microsoft.com/fwlink/?LinkId=203523)  
  
### <a name="ignore-and-continue"></a>Ignorieren und fortfahren  
 Sie können die Fehlerbedingung ignorieren und mit dem Laden des Designers fortfahren. Die Auswahl dieser Aktion kann zu unerwartetem Verhalten führen. Beispielsweise werden Steuerelemente möglicherweise nicht auf der Entwurfsoberfläche angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Problembehandlung bei der Entwicklung zur Entwurfszeit](http://msdn.microsoft.com/library/e048d08e-fa7c-4be8-b238-4abaa199a0a6)  
 [Problembehandlung beim Erstellen von Komponenten und Steuerelementen](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [Fehlermeldungen im Windows Forms-Designer](http://msdn.microsoft.com/library/cf610bf4-5fe4-471c-bce7-6a05ece07bd2)
