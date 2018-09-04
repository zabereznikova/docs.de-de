---
title: Empfehlungen zum Typ von Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- user controls [Windows Forms], when to use
- custom controls [Windows Forms], types
- controls [Windows Forms], creating
ms.assetid: 5235fe9d-c36a-4c08-ae76-6cb90b50085e
ms.openlocfilehash: 5ce801a96bc4ef48934b983838dcf8578a5bc6e6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503016"
---
# <a name="control-type-recommendations"></a>Empfehlungen zum Typ von Steuerelementen
.NET Framework bietet Ihnen die Möglichkeit, neue Steuerelemente zu entwickeln und zu implementieren. Zusätzlich zu den bekannten Benutzersteuerelementen können Sie nun benutzerdefinierte Steuerelemente schreiben, die ihre eigene Grafikausgabe ausführen und über Vererbung sogar die Funktionalität von vorhandenen Steuerelementen erweitern können. Das Treffen einer Entscheidung, welcher Typ von Steuerelement erstellt werden soll, kann verwirrend sein kann. In diesem Abschnitt werden die Unterschiede aufgezeigt, die es zwischen den verschiedenen Typen von Steuerelementen gibt, von denen geerbt werden kann, und werden Aspekte hinsichtlich des Typs vorgestellt, den Sie für Ihr Projekt wählen sollten.  
  
> [!NOTE]
>  Wenn Sie ein Steuerelement erstellen möchten, das in Web Forms verwendet werden soll, sollten Sie [Entwickeln von benutzerdefinierten ASP.NET-Serversteuerelementen](https://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef) lesen.  
  
## <a name="inheriting-from-a-windows-forms-control"></a>Erben von einem Windows Forms-Steuerelement  
 Sie können ein geerbtes Steuerelement aus jedem vorhandenen Windows Forms-Steuerelement ableiten. Diese Vorgehensweise ermöglicht es Ihnen, die in einem Windows Forms-Steuerelement implementierte Funktionalität zu übernehmen und diese Funktionalität dann durch Hinzufügen von benutzerdefinierten Eigenschaften, Methoden oder weiteren Funktionen zu erweitern. Sie könnten z. B. ein aus <xref:System.Windows.Forms.TextBox> abgeleitetes Steuerelement erstellen, das nur Zahlen akzeptiert und die jeweilige Eingabe automatisch in einen Wert konvertiert. Ein solches Steuerelement könnte Validierungscode enthalten, der immer dann aufgerufen wird, wenn der Text im Textfeld geändert wurde, und könnte die zusätzliche Eigenschaft "Wert" haben. Bei einigen Steuerelementen können Sie auch eine benutzerdefinierte Darstellung der grafischen Oberfläche des Steuerelements hinzufügen, indem Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>-Methode der Basisklasse überschreiben.  
  
 Verwenden Sie Vererbung von einem Windows Forms-Steuerelement, wenn Folgendes zutrifft:  
  
-   Ein Großteil der Funktionalität, die Sie benötigen, mit ist der Funktionalität eines vorhandenen Windows Forms-Steuerelements identisch.  
  
-   Sie benötigen keine benutzerdefinierte grafische Oberfläche, oder Sie möchten ein neues grafisches Front-End für ein vorhandenes Steuerelement entwerfen.  
  
## <a name="inheriting-from-the-usercontrol-class"></a>Erben von der UserControl-Klasse  
 Ein Benutzersteuerelement ist eine Sammlung von Windows Forms-Steuerelementen, die in einem gemeinsamen Container gekapselt sind. Der Container enthält die gesamte Funktionalität, die in jedem der Windows Forms-Steuerelemente implementiert ist, und ermöglicht es Ihnen, deren Eigenschaften selektiv verfügbar zu machen und zu binden. Ein Beispiel für ein Benutzersteuerelement könnte ein Steuerelement sein, das erstellt wurde, um Kundenadressdaten aus einer Datenbank anzuzeigen. Dieses Steuerelement würde mehrere Textfelder zum Anzeigen jedes Felds sowie Schaltflächensteuerelemente enthalten, mit denen durch die Datensätze navigiert werden kann. Datenbindungseigenschaften könnten selektiv verfügbar gemacht werden, und das gesamte Steuerelement könnte paketiert und von Anwendung zu Anwendung wiederverwendet werden.  
  
 Verwenden Sie Vererbung von der <xref:System.Windows.Forms.UserControl>-Klasse, wenn Folgendes zutrifft:  
  
-   Sie möchten die Funktionalität mehrerer Windows Forms-Steuerelemente in einer einzigen wiederverwendbaren Einheit kombinieren.  
  
## <a name="inheriting-from-the-control-class"></a>Erben von der Control-Klasse  
 Eine weitere Möglichkeit zum Erstellen eines Steuerelements besteht darin, ein Steuerelement von Grund auf neu zu erstellen, indem es von <xref:System.Windows.Forms.Control> erbt. Die <xref:System.Windows.Forms.Control>-Klasse stellt die gesamte grundlegende Funktionalität bereit, die für Steuerelemente erforderlich ist (z. B. Ereignisse), stellt aber weder steuerelementspezifische Funktionalität noch eine grafische Oberfläche bereit. Ein Erstellen eines Steuerelement durch Erben von der <xref:System.Windows.Forms.Control>-Klasse erfordert viel mehr Überlegungen und Anstrengungen als ein Erben von einem Benutzersteuerelement oder einem vorhandenen Windows Forms-Steuerelement. Der Autor muss sowohl Code für das <xref:System.Windows.Forms.Control.OnPaint%2A>-Ereignis des Steuerelements als auch jeglichen für die jeweilige Funktionalität erforderlichen Code schreiben. Es ist jedoch größere Flexibilität möglich, und Sie können ein Steuerelement so anpassen, das es exakt Ihren Anforderungen entspricht. Ein Beispiel für ein benutzerdefiniertes Steuerelement ist ein Uhren-Steuerelement, das das Erscheinungsbild und die Aktion einer analogen Uhr dupliziert. Benutzerdefiniertes Zeichnen würde aufgerufen, um die Zeiger der Uhr als Reaktion auf <xref:System.Windows.Forms.Timer.Tick>-Ereignisse zu bewegen, die aus einer internen Timer-Komponente stammen.  
  
 Verwenden Sie Vererbung von der <xref:System.Windows.Forms.Control>-Klasse, wenn Folgendes zutrifft:  
  
-   Sie möchten eine benutzerdefinierte grafische Darstellung Ihres Steuerelements bereitstellen.  
  
-   Sie müssen benutzerdefinierte Funktionalität implementieren, die über Standardsteuerelemente nicht verfügbar ist.  
  
-   [Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“](https://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)  
  
-   [Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement mit Visual C#](https://msdn.microsoft.com/library/5h0k2e6x\(v=vs.110\))  
  
-   [Vorgehensweise: Bereitstellen einer Toolboxbitmap für ein Steuerelement](https://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))  
  
-   [Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen](https://msdn.microsoft.com/library/7h62478z\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit](https://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))  
  
-   [Vorgehensweise: Erben von der Control-Klasse](https://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))  
  
-   [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
  
-   [Vorgehensweise: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit](https://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))  
  
-   [Vorgehensweise: Erben von der UserControl-Klasse](https://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))  
  
-   [Vorgehensweise: Erstellen von Steuerelementen für Windows Forms](https://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))  
  
-   [Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen](https://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](https://msdn.microsoft.com/library/c316f119\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual C#](https://msdn.microsoft.com/library/a6h7e207\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit Visual Basic](https://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))  
  
-   [Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Entwurfszeitfeatures nutzt](https://msdn.microsoft.com/library/307hck25\(v=vs.110\))  
  
-   [Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Entwurfszeitfeatures nutzt](https://msdn.microsoft.com/library/307hck25\(v=vs.120\))  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Entwickeln eines einfachen Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)  
 [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
