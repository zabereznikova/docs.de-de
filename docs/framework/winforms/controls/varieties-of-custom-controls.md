---
title: Arten von benutzerdefinierten Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.assetid: 3cea09e5-4344-4ccb-9858-b66ccac210ff
ms.openlocfilehash: f35fdb0f82370ed3e40aeeda01b3c88f0a8c5ec0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="varieties-of-custom-controls"></a>Arten von benutzerdefinierten Steuerelementen
.NET Framework bietet Ihnen die Möglichkeit, neue Steuerelemente zu entwickeln und zu implementieren. Sie können die Funktionalität des vertrauten Benutzersteuerelements sowie von vorhandenen Steuerelementen durch Vererbung erweitern. Sie können auch benutzerdefinierte Steuerelemente schreiben, die ihre eigene Grafikausgabe ausführen.  
  
 Es kann verwirrend sein, eine Entscheidung zu treffen, welche Art von Steuerelement erstellt werden soll. Dieses Thema behandelt die Unterschiede zwischen verschiedenen Arten von Steuerelementen, von denen geerbt werden kann, und bietet Informationen über die Auswahl einer bestimmten Art von Steuerelement für Ihr Projekt.  
  
> [!NOTE]
>  Informationen zum Erstellen eines Steuerelements, das in Web Forms verwendet werden soll, finden Sie unter [Entwickeln von benutzerdefinierten ASP.NET-Serversteuerelementen](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).  
  
## <a name="base-control-class"></a>Control-Basisklasse  
 Die <xref:System.Windows.Forms.Control> Klasse ist die Basisklasse für Windows Forms-Steuerelemente. Sie bietet die Infrastruktur, die für die grafische Darstellung in Windows Forms-Anwendungen benötigt wird.  
  
 Die <xref:System.Windows.Forms.Control> Klasse führt die folgenden Aufgaben aus, um die visuelle Darstellung in Windows Forms-Anwendungen bereitstellen:  
  
-   Macht ein Fensterhandle verfügbar.  
  
-   Verwaltet Meldungsrouting.  
  
-   Bietet Maus- und Tastaturereignisse und viele weitere Ereignisse der Benutzeroberfläche.  
  
-   Bietet erweiterte Layoutfunktionen.  
  
-   Enthält zahlreiche Eigenschaften für die visuelle Anzeige, z. B. <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, und <xref:System.Windows.Forms.Control.Width%2A>.  
  
-   Bietet die notwendige Unterstützung für Sicherheit und Threading für ein Windows Forms-Steuerelement, um als Microsoft® ActiveX®-Steuerelement zu fungieren.  
  
 Da der Großteil der Infrastruktur von der Basisklasse bereitgestellt wird, ist es relativ einfach, Ihre eigenen Windows Forms-Steuerelemente zu entwickeln.  
  
## <a name="kinds-of-controls"></a>Arten von Steuerelementen  
 Windows Forms unterstützt drei Arten von benutzerdefinierten Steuerelementen: *zusammengesetzt*, *erweitert* und *benutzerdefiniert*. In den folgenden Abschnitten werden die Arten von Steuerelementen beschrieben und Empfehlungen für die Auswahl gegeben, welche Art Sie in Ihren Projekten verwenden sollten.  
  
### <a name="composite-controls"></a>Zusammengesetzte Steuerelemente  
 Ein zusammengesetztes Steuerelement ist eine Sammlung von Windows Forms-Steuerelementen, die in einem gemeinsamen Container gekapselt sind. Diese Art von Steuerelement wird manchmal auch als *Benutzersteuerelement* bezeichnet. Die enthaltenen Steuerelemente werden *konstituierende Steuerelemente* genannt.  
  
 Ein zusammengesetztes Steuerelement enthält die gesamte Funktionalität, die in jedem der enthaltenen Windows Forms-Steuerelemente implementiert ist, und ermöglicht es Ihnen, deren Eigenschaften selektiv verfügbar zu machen und zu binden. Ein zusammengesetztes Steuerelement bietet auch hohe Funktionalität für die standardmäßige Tastaturbehandlung, sodass Sie keinen zusätzlichen Entwicklungsaufwand betreiben müssen.  
  
 Ein zusammengesetztes Steuerelement kann z.B. erstellt werden, um die Adressdaten von Kunden aus einer Datenbank anzuzeigen. Dieses Steuerelement könnte es u. a. eine <xref:System.Windows.Forms.DataGridView> -Steuerelement zum Anzeigen von die Datenbankfelder eine <xref:System.Windows.Forms.BindingSource> zum Binden an eine Datenquelle zu behandeln und eine <xref:System.Windows.Forms.BindingNavigator> Steuerelement, durch die Datensätze verschoben werden. Sie können Datenbindungseigenschaften selektiv verfügbar machen und das gesamte Steuerelement verpacken und von Anwendung zu Anwendung wiederverwenden. Ein Beispiel dieser Art von Benutzersteuerelement finden Sie unter [Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).  
  
 Leiten Sie zum Erstellen eines zusammengesetzten Steuerelements aus der <xref:System.Windows.Forms.UserControl> Klasse. Die <xref:System.Windows.Forms.UserControl> Basisklasse stellt Tastaturrouting für untergeordnete Steuerelemente aus und ermöglicht es die untergeordneten Steuerelemente in einer Gruppe zu arbeiten. Weitere Informationen finden Sie unter [Entwickeln eines zusammengesetzten Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md).  
  
 **Empfehlung**  
  
 Verwenden Sie Vererbung von der <xref:System.Windows.Forms.UserControl>-Klasse, wenn Folgendes zutrifft:  
  
-   Sie möchten die Funktionalität mehrerer Windows Forms-Steuerelemente in einer einzigen wiederverwendbaren Einheit kombinieren.  
  
### <a name="extended-controls"></a>Erweiterte Steuerelemente  
 Sie können ein geerbtes Steuerelement aus jedem vorhandenen Windows Forms-Steuerelement ableiten. Diese Vorgehensweise ermöglicht es Ihnen, die in einem Windows Forms-Steuerelement implementierte Funktionalität zu übernehmen und diese Funktionalität dann durch Hinzufügen von benutzerdefinierten Eigenschaften, Methoden oder weiteren Funktionen zu erweitern. Mit dieser Option können Sie die Farblogik des Basissteuerelements außer Kraft setzen und anschließend die Benutzeroberfläche durch Verändern des Aussehens erweitern.  
  
 Sie können z. B. erstellen ein Steuerelements abgeleitet wurde. die <xref:System.Windows.Forms.Button> Steuerelement, das nachverfolgt, wie oft einen Benutzer geklickt hat.  
  
 Bei einigen Steuerelementen können Sie auch eine benutzerdefinierte Darstellung auf der grafischen Benutzeroberfläche des Steuerelements hinzufügen, durch Überschreiben der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode der Basisklasse. Für eine erweiterte Schaltfläche, die verfolgt, Klicks, überschreiben Sie die <xref:System.Windows.Forms.Control.OnPaint%2A> die grundlegende Implementierung der aufzurufenden Methode <xref:System.Windows.Forms.Control.OnPaint%2A>, und zeichnen Sie dann die Anzahl der auf eine in der die <xref:System.Windows.Forms.Button> Clientbereich des Steuerelements.  
  
 **Empfehlung**  
  
 Verwenden Sie Vererbung von einem Windows Forms-Steuerelement, wenn Folgendes zutrifft:  
  
-   Ein Großteil der Funktionalität, die Sie benötigen, mit ist der Funktionalität eines vorhandenen Windows Forms-Steuerelements identisch.  
  
-   Sie benötigen keine benutzerdefinierte grafische Benutzeroberfläche, oder Sie möchten eine neue grafische Benutzeroberfläche für ein vorhandenes Steuerelement entwerfen.  
  
### <a name="custom-controls"></a>Benutzerdefinierte Steuerelemente  
 Eine weitere Möglichkeit zum Erstellen eines Steuerelements ist im Wesentlichen von vorn zu erstellen, durch Vererben von <xref:System.Windows.Forms.Control>. Die <xref:System.Windows.Forms.Control> Klasse enthält alle Steuerelemente, einschließlich Tastatur- und Behandlung von Ereignissen, die grundlegenden Funktionen jedoch keine steuerelementspezifische Funktionalität oder grafische Benutzeroberfläche.  
  
 Erstellen ein Steuerelement durch Erben von der <xref:System.Windows.Forms.Control> -Klasse erfordert viel mehr Überlegungen und anstrengungen als ein erben von <xref:System.Windows.Forms.UserControl> oder einem vorhandenen Windows Forms-Steuerelement. Da ein Großteil der Implementierung Ihnen überlassen ist, hat Ihr Steuerelement größere Flexibilität als ein zusammengesetztes oder erweitertes Steuerelement, und Sie können Ihr Steuerelement exakt an Ihre Anforderungen anpassen.  
  
 Um ein benutzerdefiniertes Steuerelement zu implementieren, müssen Sie schreiben Code für die <xref:System.Windows.Forms.Control.OnPaint%2A> -Ereignis für das Steuerelement als auch funktionsspezifische Code müssen Sie. Sie können auch überschreiben die <xref:System.Windows.Forms.Control.WndProc%2A> -Methode und das Handle des Windows-Meldungen direkt. Dies ist die beste Möglichkeit, ein Steuerelement zu erstellen. Sie müssen allerdings mit der Microsoft Win32-API vertraut sein, um diese Technik effektiv einsetzen zu können.  
  
 Ein Beispiel für ein benutzerdefiniertes Steuerelement ist ein Uhren-Steuerelement, das das Erscheinungsbild und das Verhalten einer analogen Uhr dupliziert. Benutzerdefiniertes Zeichnen wird aufgerufen, um die Zeiger der Uhr als Reaktion auf verschieben <xref:System.Windows.Forms.Timer.Tick> Ereignisse aus einer internen <xref:System.Windows.Forms.Timer> Komponente. Weitere Informationen finden Sie unter [Vorgehensweise: Entwickeln eines einfachen Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md).  
  
 **Empfehlung**  
  
 Verwenden Sie Vererbung von der <xref:System.Windows.Forms.Control>-Klasse, wenn Folgendes zutrifft:  
  
-   Sie möchten eine benutzerdefinierte grafische Darstellung Ihres Steuerelements bereitstellen.  
  
-   Sie müssen benutzerdefinierte Funktionalität implementieren, die über Standardsteuerelemente nicht verfügbar ist.  
  
### <a name="activex-controls"></a>ActiveX-Steuerelemente  
 Obwohl die Windows Forms-Infrastruktur zum Hosten von Windows Forms-Steuerelementen optimiert wurde, können Sie weiterhin ActiveX-Steuerelemente verwenden. Visual Studio bietet Unterstützung für diese Aufgabe. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von ActiveX-Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md).  
  
### <a name="windowless-controls"></a>Fensterlose Steuerelemente  
 Die Microsoft Visual Basic® 6.0- und ActiveX-Technologien unterstützen *fensterlose* Steuerelemente. Fensterlose Steuerelemente werden in Windows Forms nicht unterstützt.  
  
## <a name="custom-design-experience"></a>Benutzerdefiniertes Entwurfserlebnis  
 Wenn Sie eine benutzerdefinierte Handhabung zur Entwurfszeit implementieren müssen, können Sie Ihren eigenen Designer erstellen. Für zusammengesetzte Steuerelemente, leiten Sie eine benutzerdefinierte Designer-Klasse von der <xref:System.Windows.Forms.Design.ParentControlDesigner> oder <xref:System.Windows.Forms.Design.DocumentDesigner> Klassen. Für erweiterte und benutzerdefinierte Steuerelemente, leiten Sie eine benutzerdefinierte Designer-Klasse von der <xref:System.Windows.Forms.Design.ControlDesigner> Klasse.  
  
 Verwenden der <xref:System.ComponentModel.DesignerAttribute> auf das Steuerelement mit Ihren Designer zuordnen. Weitere Informationen finden Sie unter [Erweitern der Entwurfszeitunterstützung](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2) und [Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Entwurfszeitfeatures nutzt](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c).  
  
## <a name="see-also"></a>Siehe auch  
 [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Gewusst wie: Entwickeln eines einfachen Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)  
 [Entwickeln eines zusammengesetzten Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)  
 [Erweitern der Entwurfszeitunterstützung](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Entwurfszeitfeatures nutzt](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)
