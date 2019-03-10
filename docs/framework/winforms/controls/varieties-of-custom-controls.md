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
ms.openlocfilehash: 140b9284d9361aa149b4f739908376d1cbe6902c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713019"
---
# <a name="varieties-of-custom-controls"></a>Arten von benutzerdefinierten Steuerelementen
.NET Framework bietet Ihnen die Möglichkeit, neue Steuerelemente zu entwickeln und zu implementieren. Sie können die Funktionalität des vertrauten Benutzersteuerelements sowie von vorhandenen Steuerelementen durch Vererbung erweitern. Sie können auch benutzerdefinierte Steuerelemente schreiben, die ihre eigene Grafikausgabe ausführen.  
  
 Es kann verwirrend sein, eine Entscheidung zu treffen, welche Art von Steuerelement erstellt werden soll. Dieses Thema behandelt die Unterschiede zwischen verschiedenen Arten von Steuerelementen, von denen geerbt werden kann, und bietet Informationen über die Auswahl einer bestimmten Art von Steuerelement für Ihr Projekt.  
  
> [!NOTE]
>  Informationen zum Erstellen eines Steuerelements, das in Web Forms verwendet werden soll, finden Sie unter [Entwickeln von benutzerdefinierten ASP.NET-Serversteuerelementen](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).  
  
## <a name="base-control-class"></a>Control-Basisklasse  
 Die <xref:System.Windows.Forms.Control> Klasse ist die Basisklasse für Windows Forms-Steuerelemente. Sie bietet die Infrastruktur, die für die grafische Darstellung in Windows Forms-Anwendungen benötigt wird.  
  
 Die <xref:System.Windows.Forms.Control> Klasse führt die folgenden Aufgaben zur visuellen Darstellung in Windows Forms-Anwendungen zu bieten:  
  
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
  
 Ein zusammengesetztes Steuerelement kann z.B. erstellt werden, um die Adressdaten von Kunden aus einer Datenbank anzuzeigen. Dieses Steuerelement kann umfassen eine <xref:System.Windows.Forms.DataGridView> -Steuerelement zum Anzeigen der Datenbankfelder, eine <xref:System.Windows.Forms.BindingSource> zum Binden an eine Datenquelle zu behandeln und eine <xref:System.Windows.Forms.BindingNavigator> -Steuerelements zum Navigieren durch Datensätze. Sie können Datenbindungseigenschaften selektiv verfügbar machen und das gesamte Steuerelement verpacken und von Anwendung zu Anwendung wiederverwenden. Ein Beispiel dieser Art von Benutzersteuerelement finden Sie unter [Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente](how-to-apply-attributes-in-windows-forms-controls.md).  
  
 Um ein zusammengesetztes Steuerelement zu erstellen, leiten Sie von der <xref:System.Windows.Forms.UserControl> Klasse. Die <xref:System.Windows.Forms.UserControl> Basisklasse stellt Tastaturrouting für untergeordnete Steuerelemente aus und ermöglicht untergeordnete Steuerelemente als Gruppe arbeiten kann. Weitere Informationen finden Sie unter [Entwickeln eines zusammengesetzten Windows Forms-Steuerelements](developing-a-composite-windows-forms-control.md).  
  
 **Empfehlung**  
  
 Verwenden Sie Vererbung von der <xref:System.Windows.Forms.UserControl>-Klasse, wenn Folgendes zutrifft:  
  
-   Sie möchten die Funktionalität mehrerer Windows Forms-Steuerelemente in einer einzigen wiederverwendbaren Einheit kombinieren.  
  
### <a name="extended-controls"></a>Erweiterte Steuerelemente  
 Sie können ein geerbtes Steuerelement aus jedem vorhandenen Windows Forms-Steuerelement ableiten. Diese Vorgehensweise ermöglicht es Ihnen, die in einem Windows Forms-Steuerelement implementierte Funktionalität zu übernehmen und diese Funktionalität dann durch Hinzufügen von benutzerdefinierten Eigenschaften, Methoden oder weiteren Funktionen zu erweitern. Mit dieser Option können Sie die Farblogik des Basissteuerelements außer Kraft setzen und anschließend die Benutzeroberfläche durch Verändern des Aussehens erweitern.  
  
 Sie können z. B. ein von abgeleitetes Steuerelement erstellen die <xref:System.Windows.Forms.Button> Steuerelement, das nachverfolgt, wie oft einen Benutzer geklickt hat.  
  
 Bei einigen Steuerelementen können Sie auch eine benutzerdefinierte Darstellung auf der grafischen Benutzeroberfläche des Steuerelements hinzufügen, durch Überschreiben der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode der Basisklasse. Sie können für eine erweiterte Schaltfläche, die Klicks nachverfolgt, überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode, die die basisimplementierung aufgerufen <xref:System.Windows.Forms.Control.OnPaint%2A>, und zeichnen Sie die Anzahl der Klicks in einer Ecke des der <xref:System.Windows.Forms.Button> Clientbereich des Steuerelements.  
  
 **Empfehlung**  
  
 Verwenden Sie Vererbung von einem Windows Forms-Steuerelement, wenn Folgendes zutrifft:  
  
-   Ein Großteil der Funktionalität, die Sie benötigen, mit ist der Funktionalität eines vorhandenen Windows Forms-Steuerelements identisch.  
  
-   Sie benötigen keine benutzerdefinierte grafische Benutzeroberfläche, oder Sie möchten eine neue grafische Benutzeroberfläche für ein vorhandenes Steuerelement entwerfen.  
  
### <a name="custom-controls"></a>Benutzerdefinierte Steuerelemente  
 Eine weitere Möglichkeit zum Erstellen eines Steuerelements ist von Beginn zu erstellen, durch Erben von <xref:System.Windows.Forms.Control>. Die <xref:System.Windows.Forms.Control> Klasse alle die grundlegende Funktionalität, die von Steuerelementen, darunter Maus- und Tastaturbehandlungsereignisse, benötigt aber keine steuerelementspezifische Funktionalität oder die grafische Benutzeroberfläche bereitstellt.  
  
 Erstellen ein Steuerelement durch Erben von der <xref:System.Windows.Forms.Control> -Klasse erfordert viel mehr Überlegungen und anstrengungen als ein erben von <xref:System.Windows.Forms.UserControl> oder einem vorhandenen Windows Forms-Steuerelement. Da ein Großteil der Implementierung Ihnen überlassen ist, hat Ihr Steuerelement größere Flexibilität als ein zusammengesetztes oder erweitertes Steuerelement, und Sie können Ihr Steuerelement exakt an Ihre Anforderungen anpassen.  
  
 Um ein benutzerdefiniertes Steuerelement zu implementieren, Sie müssen Code schreiben, für die <xref:System.Windows.Forms.Control.OnPaint%2A> Ereignis des Steuerelements als auch alle funktionsspezifischen Code, die Sie benötigen. Sie können auch überschreiben die <xref:System.Windows.Forms.Control.WndProc%2A> -Methode und behandeln Windows-Meldungen direkt. Dies ist die beste Möglichkeit, ein Steuerelement zu erstellen. Sie müssen allerdings mit der Microsoft Win32-API vertraut sein, um diese Technik effektiv einsetzen zu können.  
  
 Ein Beispiel für ein benutzerdefiniertes Steuerelement ist ein Uhren-Steuerelement, das das Erscheinungsbild und das Verhalten einer analogen Uhr dupliziert. Die benutzerdefinierte Darstellung wird aufgerufen, um die Zeiger der Uhr sich als Reaktion auf verschieben <xref:System.Windows.Forms.Timer.Tick> Ereignisse aus einer internen <xref:System.Windows.Forms.Timer> Komponente. Weitere Informationen finden Sie unter [Vorgehensweise: Entwickeln ein einfachen Windows Forms-Steuerelements](how-to-develop-a-simple-windows-forms-control.md).  
  
 **Empfehlung**  
  
 Verwenden Sie Vererbung von der <xref:System.Windows.Forms.Control>-Klasse, wenn Folgendes zutrifft:  
  
-   Sie möchten eine benutzerdefinierte grafische Darstellung Ihres Steuerelements bereitstellen.  
  
-   Sie müssen benutzerdefinierte Funktionalität implementieren, die über Standardsteuerelemente nicht verfügbar ist.  
  
### <a name="activex-controls"></a>ActiveX-Steuerelemente  
 Obwohl die Windows Forms-Infrastruktur zum Hosten von Windows Forms-Steuerelementen optimiert wurde, können Sie weiterhin ActiveX-Steuerelemente verwenden. Visual Studio bietet Unterstützung für diese Aufgabe. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von ActiveX-Steuerelemente zu Windows Forms](how-to-add-activex-controls-to-windows-forms.md).  
  
### <a name="windowless-controls"></a>Fensterlose Steuerelemente  
 Die Microsoft Visual Basic® 6.0- und ActiveX-Technologien unterstützen *fensterlose* Steuerelemente. Fensterlose Steuerelemente werden in Windows Forms nicht unterstützt.  
  
## <a name="custom-design-experience"></a>Benutzerdefiniertes Entwurfserlebnis  
 Wenn Sie eine benutzerdefinierte Handhabung zur Entwurfszeit implementieren müssen, können Sie Ihren eigenen Designer erstellen. Leiten Sie bei zusammengesetzten Steuerelementen Ihre benutzerdefinierte Designerklasse von den <xref:System.Windows.Forms.Design.ParentControlDesigner> oder <xref:System.Windows.Forms.Design.DocumentDesigner> Klassen. Leiten Sie für erweiterte und benutzerdefinierte Steuerelemente, Ihre benutzerdefinierte Designerklasse von den <xref:System.Windows.Forms.Design.ControlDesigner> Klasse.  
  
 Verwenden der <xref:System.ComponentModel.DesignerAttribute> auf Ihr Steuerelement Ihrem Designer zuzuordnen. Weitere Informationen finden Sie unter [Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)) und [Vorgehensweise: Erstellen Sie ein Windows Forms-Steuerelement, das Entwurfszeitfeatures nutzt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).  
  
## <a name="see-also"></a>Siehe auch
- [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](developing-custom-windows-forms-controls.md)
- [Vorgehensweise: Entwickeln eines einfachen Windows Forms-Steuerelements](how-to-develop-a-simple-windows-forms-control.md)
- [Entwickeln eines zusammengesetzten Windows Forms-Steuerelements](developing-a-composite-windows-forms-control.md)
- [Erweitern der Entwurfszeitunterstützung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))
- [Vorgehensweise: Erstellen Sie ein Windows Forms-Steuerelement, das Entwurfszeitfeatures nutzt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))
