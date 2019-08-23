---
title: Empfehlungen zum Typ von Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- user controls [Windows Forms], when to use
- custom controls [Windows Forms], types
- controls [Windows Forms], creating
ms.assetid: 5235fe9d-c36a-4c08-ae76-6cb90b50085e
ms.openlocfilehash: 40451aea3026a492864cf94031c0bea196a18ff3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930256"
---
# <a name="control-type-recommendations"></a>Empfehlungen zum Typ von Steuerelementen
.NET Framework bietet Ihnen die Möglichkeit, neue Steuerelemente zu entwickeln und zu implementieren. Zusätzlich zu den bekannten Benutzersteuerelementen können Sie nun benutzerdefinierte Steuerelemente schreiben, die ihre eigene Grafikausgabe ausführen und über Vererbung sogar die Funktionalität von vorhandenen Steuerelementen erweitern können. Das Treffen einer Entscheidung, welcher Typ von Steuerelement erstellt werden soll, kann verwirrend sein kann. In diesem Abschnitt werden die Unterschiede aufgezeigt, die es zwischen den verschiedenen Typen von Steuerelementen gibt, von denen geerbt werden kann, und werden Aspekte hinsichtlich des Typs vorgestellt, den Sie für Ihr Projekt wählen sollten.  
  
> [!NOTE]
> Wenn Sie ein Steuerelement erstellen möchten, das in Web Forms verwendet werden soll, sollten Sie [Entwickeln von benutzerdefinierten ASP.NET-Serversteuerelementen](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)) lesen.  
  
## <a name="inheriting-from-a-windows-forms-control"></a>Erben von einem Windows Forms-Steuerelement  
 Sie können ein geerbtes Steuerelement aus jedem vorhandenen Windows Forms-Steuerelement ableiten. Diese Vorgehensweise ermöglicht es Ihnen, die in einem Windows Forms-Steuerelement implementierte Funktionalität zu übernehmen und diese Funktionalität dann durch Hinzufügen von benutzerdefinierten Eigenschaften, Methoden oder weiteren Funktionen zu erweitern. Sie könnten z. B. ein aus <xref:System.Windows.Forms.TextBox> abgeleitetes Steuerelement erstellen, das nur Zahlen akzeptiert und die jeweilige Eingabe automatisch in einen Wert konvertiert. Ein solches Steuerelement könnte Validierungscode enthalten, der immer dann aufgerufen wird, wenn der Text im Textfeld geändert wurde, und könnte die zusätzliche Eigenschaft „Wert“ haben. Bei einigen Steuerelementen können Sie auch eine benutzerdefinierte Darstellung der grafischen Oberfläche des Steuerelements hinzufügen, indem Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>-Methode der Basisklasse überschreiben.  
  
 Verwenden Sie Vererbung von einem Windows Forms-Steuerelement, wenn Folgendes zutrifft:  
  
- Ein Großteil der Funktionalität, die Sie benötigen, mit ist der Funktionalität eines vorhandenen Windows Forms-Steuerelements identisch.  
  
- Sie benötigen keine benutzerdefinierte grafische Oberfläche, oder Sie möchten ein neues grafisches Front-End für ein vorhandenes Steuerelement entwerfen.  
  
## <a name="inheriting-from-the-usercontrol-class"></a>Erben von der UserControl-Klasse  
 Ein Benutzersteuerelement ist eine Sammlung von Windows Forms-Steuerelementen, die in einem gemeinsamen Container gekapselt sind. Der Container enthält die gesamte Funktionalität, die in jedem der Windows Forms-Steuerelemente implementiert ist, und ermöglicht es Ihnen, deren Eigenschaften selektiv verfügbar zu machen und zu binden. Ein Beispiel für ein Benutzersteuerelement könnte ein Steuerelement sein, das erstellt wurde, um Kundenadressdaten aus einer Datenbank anzuzeigen. Dieses Steuerelement würde mehrere Textfelder zum Anzeigen jedes Felds sowie Schaltflächensteuerelemente enthalten, mit denen durch die Datensätze navigiert werden kann. Datenbindungseigenschaften könnten selektiv verfügbar gemacht werden, und das gesamte Steuerelement könnte paketiert und von Anwendung zu Anwendung wiederverwendet werden.  
  
 Verwenden Sie Vererbung von der <xref:System.Windows.Forms.UserControl>-Klasse, wenn Folgendes zutrifft:  
  
- Sie möchten die Funktionalität mehrerer Windows Forms-Steuerelemente in einer einzigen wiederverwendbaren Einheit kombinieren.  
  
## <a name="inheriting-from-the-control-class"></a>Erben von der Control-Klasse  
 Eine weitere Möglichkeit zum Erstellen eines Steuerelements besteht darin, ein Steuerelement von Grund auf neu zu erstellen, indem es von <xref:System.Windows.Forms.Control> erbt. Die <xref:System.Windows.Forms.Control>-Klasse stellt die gesamte grundlegende Funktionalität bereit, die für Steuerelemente erforderlich ist (z. B. Ereignisse), stellt aber weder steuerelementspezifische Funktionalität noch eine grafische Oberfläche bereit. Ein Erstellen eines Steuerelement durch Erben von der <xref:System.Windows.Forms.Control>-Klasse erfordert viel mehr Überlegungen und Anstrengungen als ein Erben von einem Benutzersteuerelement oder einem vorhandenen Windows Forms-Steuerelement. Der Autor muss sowohl Code für das <xref:System.Windows.Forms.Control.OnPaint%2A>-Ereignis des Steuerelements als auch jeglichen für die jeweilige Funktionalität erforderlichen Code schreiben. Es ist jedoch größere Flexibilität möglich, und Sie können ein Steuerelement so anpassen, das es exakt Ihren Anforderungen entspricht. Ein Beispiel für ein benutzerdefiniertes Steuerelement ist ein Uhren-Steuerelement, das das Erscheinungsbild und die Aktion einer analogen Uhr dupliziert. Benutzerdefiniertes Zeichnen würde aufgerufen, um die Zeiger der Uhr als Reaktion auf <xref:System.Windows.Forms.Timer.Tick>-Ereignisse zu bewegen, die aus einer internen Timer-Komponente stammen.  
  
 Verwenden Sie Vererbung von der <xref:System.Windows.Forms.Control>-Klasse, wenn Folgendes zutrifft:  
  
- Sie möchten eine benutzerdefinierte grafische Darstellung Ihres Steuerelements bereitstellen.  
  
- Sie müssen benutzerdefinierte Funktionalität implementieren, die über Standardsteuerelemente nicht verfügbar ist.  
  
- [Vorgehensweise: Anzeigen eines Steuer Elements im Dialog Feld "Toolbox Elemente auswählen"](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
  
- [Exemplarische Vorgehensweise: Serialisieren von Auflistungen von Standard Typen mit dem DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)  
  
- [Exemplarische Vorgehensweise: Erben von einem Windows Forms-Steuerelement mit VisualC#](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
  
- [Vorgehensweise: Bereitstellen einer Toolbox Bitmap für ein Steuerelement](how-to-provide-a-toolbox-bitmap-for-a-control.md)  
  
- [Vorgehensweise: Von vorhandenen Windows Forms Steuerelementen erben](how-to-inherit-from-existing-windows-forms-controls.md)  
  
- [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
  
- [Vorgehensweise: Erben von der Control-Klasse](how-to-inherit-from-the-control-class.md)  
  
- [Vorgehensweise: Testen des Lauf Zeit Verhaltens eines UserControl-Steuer Elements](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
  
- [Vorgehensweise: Ausrichten eines Steuer Elements an den Kanten von Formularen zur Entwurfszeit](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
  
- [Vorgehensweise: Erben von der UserControl-Klasse](how-to-inherit-from-the-usercontrol-class.md)  
  
- [Vorgehensweise: Steuerelemente für Windows Forms erstellen](how-to-author-controls-for-windows-forms.md)  
  
- [Vorgehensweise: Zusammengesetzte Steuerelemente verfassen](how-to-author-composite-controls.md)  
  
- [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuer Elements mit Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md)  
  
- [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuer Elements mit VisualC#](walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
  
- [Exemplarische Vorgehensweise: Erben von einem Windows Forms-Steuerelement mit Visual Basic](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
  
- [Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuer Elements, das Visual Studio-Entwurfszeit Funktionen nutzt](creating-a-wf-control-design-time-features.md)  
  
- [Vorgehensweise: Erstellen eines Windows Forms-Steuer Elements, das Entwurfszeit Features nutzt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Entwickeln eines einfachen Windows Forms-Steuer Elements](how-to-develop-a-simple-windows-forms-control.md)
- [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](varieties-of-custom-controls.md)
