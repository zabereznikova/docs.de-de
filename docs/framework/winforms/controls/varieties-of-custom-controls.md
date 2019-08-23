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
ms.openlocfilehash: 106da550fc6e6c50bc40e103e1f855059a9ffa9c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950096"
---
# <a name="varieties-of-custom-controls"></a>Arten von benutzerdefinierten Steuerelementen
.NET Framework bietet Ihnen die Möglichkeit, neue Steuerelemente zu entwickeln und zu implementieren. Sie können die Funktionalität des vertrauten Benutzersteuerelements sowie von vorhandenen Steuerelementen durch Vererbung erweitern. Sie können auch benutzerdefinierte Steuerelemente schreiben, die ihre eigene Grafikausgabe ausführen.  
  
 Es kann verwirrend sein, eine Entscheidung zu treffen, welche Art von Steuerelement erstellt werden soll. Dieses Thema behandelt die Unterschiede zwischen verschiedenen Arten von Steuerelementen, von denen geerbt werden kann, und bietet Informationen über die Auswahl einer bestimmten Art von Steuerelement für Ihr Projekt.  
  
> [!NOTE]
> Informationen zum Erstellen eines Steuerelements, das in Web Forms verwendet werden soll, finden Sie unter [Entwickeln von benutzerdefinierten ASP.NET-Serversteuerelementen](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).  
  
## <a name="base-control-class"></a>Control-Basisklasse  
 Die <xref:System.Windows.Forms.Control> -Klasse ist die Basisklasse für Windows Forms-Steuerelemente. Sie bietet die Infrastruktur, die für die grafische Darstellung in Windows Forms-Anwendungen benötigt wird.  
  
 Die <xref:System.Windows.Forms.Control> -Klasse führt die folgenden Aufgaben aus, um die visuelle Darstellung in Windows Forms Anwendungen bereitzustellen:  
  
- Macht ein Fensterhandle verfügbar.  
  
- Verwaltet Meldungsrouting.  
  
- Bietet Maus- und Tastaturereignisse und viele weitere Ereignisse der Benutzeroberfläche.  
  
- Bietet erweiterte Layoutfunktionen.  
  
- Enthält zahlreiche Eigenschaften, die für die visuelle Anzeige <xref:System.Windows.Forms.Control.ForeColor%2A>spezifisch <xref:System.Windows.Forms.Control.BackColor%2A>sind, z <xref:System.Windows.Forms.Control.Width%2A>. b.,, <xref:System.Windows.Forms.Control.Height%2A>und.  
  
- Bietet die notwendige Unterstützung für Sicherheit und Threading für ein Windows Forms-Steuerelement, um als Microsoft® ActiveX®-Steuerelement zu fungieren.  
  
 Da der Großteil der Infrastruktur von der Basisklasse bereitgestellt wird, ist es relativ einfach, Ihre eigenen Windows Forms-Steuerelemente zu entwickeln.  
  
## <a name="kinds-of-controls"></a>Arten von Steuerelementen  
 Windows Forms unterstützt drei Arten von benutzerdefinierten Steuerelementen: *zusammengesetzt*, *erweitert* und *benutzerdefiniert*. In den folgenden Abschnitten werden die Arten von Steuerelementen beschrieben und Empfehlungen für die Auswahl gegeben, welche Art Sie in Ihren Projekten verwenden sollten.  
  
### <a name="composite-controls"></a>Zusammengesetzte Steuerelemente  
 Ein zusammengesetztes Steuerelement ist eine Sammlung von Windows Forms-Steuerelementen, die in einem gemeinsamen Container gekapselt sind. Diese Art von Steuerelement wird manchmal auch als *Benutzersteuerelement* bezeichnet. Die enthaltenen Steuerelemente werden *konstituierende Steuerelemente* genannt.  
  
 Ein zusammengesetztes Steuerelement enthält die gesamte Funktionalität, die in jedem der enthaltenen Windows Forms-Steuerelemente implementiert ist, und ermöglicht es Ihnen, deren Eigenschaften selektiv verfügbar zu machen und zu binden. Ein zusammengesetztes Steuerelement bietet auch hohe Funktionalität für die standardmäßige Tastaturbehandlung, sodass Sie keinen zusätzlichen Entwicklungsaufwand betreiben müssen.  
  
 Ein zusammengesetztes Steuerelement kann z.B. erstellt werden, um die Adressdaten von Kunden aus einer Datenbank anzuzeigen. Dieses Steuerelement kann ein <xref:System.Windows.Forms.DataGridView> Steuerelement enthalten, um die Daten Bank <xref:System.Windows.Forms.BindingSource> Felder anzuzeigen, ein zum Behandeln der Bindung an eine <xref:System.Windows.Forms.BindingNavigator> Datenquelle und ein-Steuerelement, um durch die Datensätze zu navigieren. Sie können Datenbindungseigenschaften selektiv verfügbar machen und das gesamte Steuerelement verpacken und von Anwendung zu Anwendung wiederverwenden. Ein Beispiel für diese Art von zusammengesetztes Steuerelement [finden Sie unter Gewusst wie: Anwenden von Attributen in Windows Forms](how-to-apply-attributes-in-windows-forms-controls.md)-Steuerelementen.  
  
 Zum Erstellen eines zusammengesetzten Steuer Elements leiten Sie <xref:System.Windows.Forms.UserControl> von der-Klasse ab. Die <xref:System.Windows.Forms.UserControl> -Basisklasse stellt Tastatur Routing für untergeordnete Steuerelemente bereit und ermöglicht, dass untergeordnete Steuerelemente als Gruppe funktionieren. Weitere Informationen finden Sie unter [Entwickeln eines zusammengesetzten Windows Forms-Steuerelements](developing-a-composite-windows-forms-control.md).  
  
 **Empfehlung**  
  
 Verwenden Sie Vererbung von der <xref:System.Windows.Forms.UserControl>-Klasse, wenn Folgendes zutrifft:  
  
- Sie möchten die Funktionalität mehrerer Windows Forms-Steuerelemente in einer einzigen wiederverwendbaren Einheit kombinieren.  
  
### <a name="extended-controls"></a>Erweiterte Steuerelemente  
 Sie können ein geerbtes Steuerelement aus jedem vorhandenen Windows Forms-Steuerelement ableiten. Diese Vorgehensweise ermöglicht es Ihnen, die in einem Windows Forms-Steuerelement implementierte Funktionalität zu übernehmen und diese Funktionalität dann durch Hinzufügen von benutzerdefinierten Eigenschaften, Methoden oder weiteren Funktionen zu erweitern. Mit dieser Option können Sie die Farblogik des Basissteuerelements außer Kraft setzen und anschließend die Benutzeroberfläche durch Verändern des Aussehens erweitern.  
  
 Beispielsweise können Sie ein Steuerelement erstellen, das vom <xref:System.Windows.Forms.Button> -Steuerelement abgeleitet wird und nachverfolgt, wie oft ein Benutzer darauf geklickt hat.  
  
 In einigen Steuerelementen können Sie auch eine benutzerdefinierte Darstellung der grafischen Benutzeroberfläche des Steuer Elements hinzufügen, indem <xref:System.Windows.Forms.Control.OnPaint%2A> Sie die-Methode der-Basisklasse überschreiben. Für eine erweiterte Schaltfläche, mit der Klicks nachverfolgt werden <xref:System.Windows.Forms.Control.OnPaint%2A> , können Sie die-Methode über <xref:System.Windows.Forms.Control.OnPaint%2A>schreiben, um die Basis Implementierung von aufzurufen, und dann <xref:System.Windows.Forms.Button> die Click-Anzahl in einer Ecke des Client Bereichs des Steuer Elements zeichnen.  
  
 **Empfehlung**  
  
 Verwenden Sie Vererbung von einem Windows Forms-Steuerelement, wenn Folgendes zutrifft:  
  
- Ein Großteil der Funktionalität, die Sie benötigen, mit ist der Funktionalität eines vorhandenen Windows Forms-Steuerelements identisch.  
  
- Sie benötigen keine benutzerdefinierte grafische Benutzeroberfläche, oder Sie möchten eine neue grafische Benutzeroberfläche für ein vorhandenes Steuerelement entwerfen.  
  
### <a name="custom-controls"></a>Benutzerdefinierte Steuerelemente  
 Eine andere Möglichkeit zum Erstellen eines Steuer Elements besteht darin, ein Steuerelement von Anfang an zu <xref:System.Windows.Forms.Control>erstellen, indem es von erbt. Die <xref:System.Windows.Forms.Control> -Klasse stellt die gesamte grundlegende Funktionalität bereit, die für Steuerelemente erforderlich ist, einschließlich Maus-und Tastatur Behandlungs Ereignissen, aber keine Steuerelement spezifische Funktionalität bzw. grafische Benutzeroberfläche.  
  
 Das Erstellen eines-Steuer Elements durch Erben <xref:System.Windows.Forms.Control> von der-Klasse erfordert viel mehr Überlegungen und Aufwand <xref:System.Windows.Forms.UserControl> als die Vererbung von oder einem vorhandenen Windows Forms-Steuerelement. Da ein Großteil der Implementierung Ihnen überlassen ist, hat Ihr Steuerelement größere Flexibilität als ein zusammengesetztes oder erweitertes Steuerelement, und Sie können Ihr Steuerelement exakt an Ihre Anforderungen anpassen.  
  
 Um ein benutzerdefiniertes Steuerelement zu implementieren, müssen Sie <xref:System.Windows.Forms.Control.OnPaint%2A> Code für das-Ereignis des-Steuer Elements sowie für jeden featurespezifischen Code schreiben, den Sie benötigen. Sie können die <xref:System.Windows.Forms.Control.WndProc%2A> -Methode auch überschreiben und Windows-Meldungen direkt verarbeiten. Dies ist die beste Möglichkeit, ein Steuerelement zu erstellen. Sie müssen allerdings mit der Microsoft Win32-API vertraut sein, um diese Technik effektiv einsetzen zu können.  
  
 Ein Beispiel für ein benutzerdefiniertes Steuerelement ist ein Uhren-Steuerelement, das das Erscheinungsbild und das Verhalten einer analogen Uhr dupliziert. Ein benutzerdefiniertes Zeichnen wird aufgerufen, um zu bewirken, dass die Hände der <xref:System.Windows.Forms.Timer.Tick> Uhr als Reaktion auf <xref:System.Windows.Forms.Timer> Ereignisse aus einer internen Komponente verschoben werden. Weitere Informationen finden Sie unter [Vorgehensweise: Entwickeln Sie ein einfaches Windows Forms](how-to-develop-a-simple-windows-forms-control.md)-Steuerelement.  
  
 **Empfehlung**  
  
 Verwenden Sie Vererbung von der <xref:System.Windows.Forms.Control>-Klasse, wenn Folgendes zutrifft:  
  
- Sie möchten eine benutzerdefinierte grafische Darstellung Ihres Steuerelements bereitstellen.  
  
- Sie müssen benutzerdefinierte Funktionalität implementieren, die über Standardsteuerelemente nicht verfügbar ist.  
  
### <a name="activex-controls"></a>ActiveX-Steuerelemente  
 Obwohl die Windows Forms-Infrastruktur zum Hosten von Windows Forms-Steuerelementen optimiert wurde, können Sie weiterhin ActiveX-Steuerelemente verwenden. Visual Studio bietet Unterstützung für diese Aufgabe. Weitere Informationen finden Sie unter [Vorgehensweise: Fügen Sie Windows Forms](how-to-add-activex-controls-to-windows-forms.md)ActiveX-Steuerelemente hinzu.  
  
### <a name="windowless-controls"></a>Fensterlose Steuerelemente  
 Die Microsoft Visual Basic® 6.0- und ActiveX-Technologien unterstützen *fensterlose* Steuerelemente. Fensterlose Steuerelemente werden in Windows Forms nicht unterstützt.  
  
## <a name="custom-design-experience"></a>Benutzerdefiniertes Entwurfserlebnis  
 Wenn Sie eine benutzerdefinierte Handhabung zur Entwurfszeit implementieren müssen, können Sie Ihren eigenen Designer erstellen. Leiten Sie für zusammengesetzte Steuerelemente die benutzerdefinierte Designer <xref:System.Windows.Forms.Design.ParentControlDesigner> Klasse von <xref:System.Windows.Forms.Design.DocumentDesigner> der-Klasse oder der-Klasse ab. Leiten Sie für erweiterte und benutzerdefinierte Steuerelemente die benutzerdefinierte Designer <xref:System.Windows.Forms.Design.ControlDesigner> Klasse von der-Klasse ab.  
  
 Verwenden Sie <xref:System.ComponentModel.DesignerAttribute> , um das Steuerelement dem Designer zuzuordnen. Weitere Informationen finden Sie [unter Erweitern der Entwurfszeit Unterstützung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)) und [Gewusst wie: Erstellen Sie ein Windows Forms-Steuerelement, das Entwurfszeit Funktionen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))nutzt.  
  
## <a name="see-also"></a>Siehe auch

- [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](developing-custom-windows-forms-controls.md)
- [Vorgehensweise: Entwickeln eines einfachen Windows Forms-Steuer Elements](how-to-develop-a-simple-windows-forms-control.md)
- [Entwickeln eines zusammengesetzten Windows Forms-Steuerelements](developing-a-composite-windows-forms-control.md)
- [Erweitern der Entwurfszeitunterstützung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))
- [Vorgehensweise: Erstellen eines Windows Forms-Steuer Elements, das Entwurfszeit Features nutzt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))
