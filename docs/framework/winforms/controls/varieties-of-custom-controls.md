---
title: "Arten von benutzerdefinierten Steuerelementen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Zusammengesetzte Steuerelemente"
  - "Steuerelemente [Windows Forms], Zusammengesetzt"
  - "Steuerelemente [Windows Forms], Erweitert"
  - "Steuerelemente [Windows Forms], Typen"
  - "Steuerelemente [Windows Forms], Benutzersteuerelemente"
  - "Benutzerdefinierte Steuerelemente [Windows Forms]"
  - "Erweiterte Steuerelemente"
  - "Benutzersteuerelemente [Windows Forms]"
ms.assetid: 3cea09e5-4344-4ccb-9858-b66ccac210ff
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Arten von benutzerdefinierten Steuerelementen
Mit .NET Framework können Sie neue Steuerelemente entwickeln und implementieren.  Sie können die Funktionalität von vertrauten Benutzersteuerelementen sowie von vorhandenen Steuerelementen durch Vererbung erweitern.  Sie können auch benutzerdefinierte Steuerelemente erstellen, die eigenständig zeichnen.  
  
 Die Auswahl des Steuerelementtyps, der erstellt werden soll, kann schwierig sein.  In diesem Abschnitt werden die Unterschiede zwischen den verschiedenen Steuerelementtypen herausgestellt, von denen geerbt werden kann. Außerdem werden Informationen über die Wahl des richtigen Typs für das Projekt bereitgestellt.  
  
> [!NOTE]
>  Informationen über das Erstellen eines Steuerelements zur Verwendung auf Web Forms finden Sie unter [Developing Custom ASP.NET Server Controls](../Topic/Developing%20Custom%20ASP.NET%20Server%20Controls.md).  
  
## Basissteuerelementklasse  
 Die <xref:System.Windows.Forms.Control>\-Klasse ist die Basisklasse für Windows Forms\-Steuerelemente.  Sie stellt die zur visuellen Anzeige in Windows Forms\-Anwendungen erforderliche Infrastruktur bereit.  
  
 Die <xref:System.Windows.Forms.Control>\-Klasse führt zur visuellen Anzeige in Windows Forms\-Anwendungen die folgenden Aufgaben aus:  
  
-   Sie macht ein Fensterhandle verfügbar.  
  
-   Sie verwaltet Meldungsrouting.  
  
-   Sie stellt Maus\- und Tastaturereignisse sowie viele andere Benutzeroberflächenereignisse bereit.  
  
-   Sie stellt erweiterte Layoutfeatures bereit.  
  
-   Sie enthält zahlreiche Eigenschaften für die visuelle Anzeige, z. B. <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A> und <xref:System.Windows.Forms.Control.Width%2A>.  
  
-   Sie stellt die Sicherheit und Threadingunterstützung bereit, die ein Windows Forms\-Steuerelement als Microsoft® ActiveX®\-Steuerelement benötigt.  
  
 Da die Basisklasse bereits einen Großteil der Infrastruktur zur Verfügung stellt, ist das Erstellen eigener Windows Forms\-Steuerelemente relativ einfach.  
  
## Arten von Steuerelementen  
 Windows Forms unterstützen drei Arten von benutzerdefinierten Steuerelementen, nämlich *zusammengesetzte*, *erweiterte* und *benutzerdefinierte* Steuerelemente.  In den folgenden Abschnitten werden die verschiedenen Arten von Steuerelementen beschrieben und Empfehlungen zur Wahl des jeweils angemessenen Steuerelements bereitgestellt.  
  
### Zusammengesetzte Steuerelemente  
 Bei einem zusammengesetzten Steuerelement handelt es sich um eine Auflistung von Windows Forms\-Steuerelementen, die in einem allgemeinen Container eingeschlossen sind.  Diese Art von Steuerelement wird manchmal als *Benutzersteuerelement* bezeichnet.  Die enthaltenen Steuerelemente werden als *konstituierende Steuerelemente* bezeichnet.  
  
 In einem zusammengesetzten Steuerelement sind alle inhärenten Funktionalitäten enthalten, die mit den darin enthaltenen Windows Forms\-Steuerelementen verknüpft sind. Gleichzeitig können mithilfe des Containers einzelne Eigenschaften der Steuerelemente selektiv verfügbar gemacht und gebunden werden.  Ein zusammengesetztes Steuerelement stellt zudem einen Großteil der standardmäßigen Tastaturbehandlungsfunktionen bereit, ohne dass hierfür zusätzliche Entwicklungsaufgaben erforderlich sind.  
  
 Zum Beispiel könnte ein zusammengesetztes Steuerelement erstellt werden, um Kundenadressdaten aus einer Datenbank anzuzeigen.  Dieses Steuerelement könnte ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement enthalten, um die Datenbankfelder anzuzeigen, eine <xref:System.Windows.Forms.BindingSource>, um das Binden an eine Datenquelle zu behandeln, und ein <xref:System.Windows.Forms.BindingNavigator>\-Steuerelement, um durch die Datensätze zu navigieren.  Sie könnten Datenbindungseigenschaften wahlweise verfügbar machen und das gesamte Steuerelement je nach Anwendung packen und wiederverwenden.  Ein Beispiel für ein derartiges zusammengesetztes Steuerelement finden Sie unter [Gewusst wie: Anwenden von Attributen auf Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).  
  
 Um ein zusammengesetztes Steuerelement zu erstellen, leiten Sie von der <xref:System.Windows.Forms.UserControl>\-Klasse ab.  Die <xref:System.Windows.Forms.UserControl>\-Basisklasse stellt Tastaturrouting für untergeordnete Steuerelemente zur Verfügung und ermöglicht untergeordneten Steuerelementen, in einer Gruppe zu arbeiten.  Weitere Informationen finden Sie unter [Entwickeln eines zusammengesetzten Windows Forms\-Steuerelements](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md).  
  
 **Empfehlung**  
  
 Erben Sie von der <xref:System.Windows.Forms.UserControl>\-Klasse, wenn:  
  
-   Die Funktionalitäten mehrerer Windows Forms\-Steuerelemente in einer einzigen wiederverwendbaren Einheit kombiniert werden sollen.  
  
### Erweiterte Steuerelemente  
 Ein geerbtes Steuerelement kann von einem beliebigen Windows Forms\-Steuerelement abgeleitet werden.  Mit dieser Vorgehensweise gelingt es, die gesamte inhärente Funktionalität eines Steuerelements in Windows Forms beizubehalten. Anschließend kann diese Funktionalität erweitert werden, indem benutzerdefinierte Eigenschaften, Methoden oder andere Features hinzugefügt werden.  Dies ermöglicht es Ihnen, die Zeichenlogik des Basissteuerelements zu überschreiben und anschließend die Benutzeroberfläche zu erweitern, indem Sie sein Aussehen ändern.  
  
 Beispielsweise können Sie ein vom <xref:System.Windows.Forms.Button>\-Steuerelement abgeleitetes Steuerelement erstellen, das aufzeichnet, wie oft ein Benutzer darauf geklickt hat.  
  
 In einigen Steuerelementen kann außerdem eine benutzerdefinierte Darstellung zur grafischen Benutzeroberfläche des Steuerelements hinzugefügt werden, indem die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode der Basisklasse überschrieben wird.  Um eine erweiterte Schaltfläche zu erstellen, mit der Klicks aufgezeichnet werden, können Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode überschreiben, um die Basisimplementierung von <xref:System.Windows.Forms.Control.OnPaint%2A> aufzurufen und anschließend die Anzahl der Klicks in eine Ecke des Clientbereichs vom <xref:System.Windows.Forms.Button>\-Steuerelement zu schreiben.  
  
 **Empfehlung**  
  
 Erben Sie von einem Windows Forms\-Steuerelement, wenn:  
  
-   Der größte Teil der benötigten Funktionalität bereits mit einem vorhandenen Windows Forms\-Steuerelement identisch ist.  
  
-   Eine benutzerdefinierte grafische Benutzeroberfläche nicht benötigt wird oder eine neue grafische Benutzeroberfläche für ein vorhandenes Steuerelement erstellt werden soll.  
  
### Benutzerdefinierte Steuerelemente  
 Eine weitere Möglichkeit zum Erstellen eines Steuerelements besteht darin, es von Grund auf neu zu erstellen, indem von <xref:System.Windows.Forms.Control> geerbt wird.  Mit der <xref:System.Windows.Forms.Control>\-Klasse wird die gesamte grundlegende Funktionalität bereitgestellt, die für Steuerelemente erforderlich ist, z. B. Maus\- und Tastaturbehandlungsereignisse. Steuerelementspezifische Funktionalität oder eine grafische Oberfläche sind darin jedoch nicht enthalten.  
  
 Es ist wesentlich aufwändiger, ein Steuerelement durch Erben von der <xref:System.Windows.Forms.Control>\-Klasse zu erstellen als durch Erben von <xref:System.Windows.Forms.UserControl> oder einem vorhandenen Windows Forms\-Steuerelement.  Da die Implementierung weitestgehend Ihnen überlassen ist, können Sie das Steuerelement flexibler gestalten als bei einem zusammengesetzten oder erweiterten Steuerelement und es genau an Ihre Anforderungen anpassen.  
  
 Um ein benutzerdefiniertes Steuerelement zu implementieren, müssen Sie Code für das <xref:System.Windows.Forms.Control.OnPaint%2A>\-Ereignis des Steuerelements sowie ggf. featurespezifischen Code schreiben.  Sie können auch die <xref:System.Windows.Forms.Control.WndProc%2A>\-Methode überschreiben und Fenstermeldungen direkt behandeln.  Dies ist die beste Möglichkeit zur Erstellung eines Steuerelements. Um sie effektiv verwenden zu können, müssen Sie jedoch mit der Microsoft Win32®\-API vertraut sein.  
  
 Als Beispiel eines benutzerdefinierten Steuerelements kann ein Uhren\-Steuerelement herangezogen werden, das das Aussehen und Verhalten einer Analoguhr widerspiegelt.  Durch das Aufrufen des benutzerdefinierten Zeichnens wird erreicht, dass sich die Zeiger der Uhr als Antwort auf <xref:System.Windows.Forms.Timer.Tick>\-Ereignisse einer internen <xref:System.Windows.Forms.Timer>\-Komponente bewegen.  Weitere Informationen finden Sie unter [Gewusst wie: Entwickeln eines einfachen Windows Forms\-Steuerelements](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md).  
  
 **Empfehlung**  
  
 Erben Sie von der <xref:System.Windows.Forms.Control>\-Klasse, wenn:  
  
-   Eine benutzerdefinierte grafische Darstellung des Steuerelements bereitgestellt werden soll.  
  
-   Benutzerdefinierte Funktionalität hinzugefügt werden muss, die nicht über Standardsteuerelemente verfügbar ist.  
  
### ActiveX\-Steuerelemente  
 Obwohl die Windows Forms\-Infrastruktur für die Aufnahme von Windows Forms\-Steuerelementen optimiert ist, können Sie weiterhin ActiveX\-Steuerelemente verwenden.  Visual Studio bietet Unterstützung für diese Aufgabe.  Weitere Informationen hierzu finden Sie unter [Gewusst wie: Hinzufügen von ActiveX\-Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md).  
  
### Fensterlose Steuerelemente  
 Die Microsoft\-Visual\-Basic® 6.0\- und ActiveX\-Technologien unterstützen *fensterlose* Steuerelemente.  Fensterlose Steuerelemente werden in Windows Forms nicht unterstützt.  
  
## Benutzerdefinierte Entwurfserfahrung  
 Wenn Sie eine benutzerdefinierte Entwurfszeiterfahrung implementieren müssen, können Sie Ihren eigenen Designer erstellen.  Leiten Sie bei zusammengesetzten Steuerelementen die benutzerdefinierte Designerklasse vom <xref:System.Windows.Forms.Design.ParentControlDesigner> oder den <xref:System.Windows.Forms.Design.DocumentDesigner>\-Klassen ab.  Bei erweiterten und benutzerdefinierten Steuerelementen leiten Sie die benutzerdefinierte Designerklasse von der <xref:System.Windows.Forms.Design.ControlDesigner>\-Klasse ab.  
  
 Verwenden Sie das <xref:System.ComponentModel.DesignerAttribute>, um das Steuerelement mit dem Designer zu verknüpfen.  Weitere Informationen finden Sie unter [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md) und [How to: Create a Windows Forms Control That Takes Advantage of Design\-Time Features](../Topic/How%20to:%20Create%20a%20Windows%20Forms%20Control%20That%20Takes%20Advantage%20of%20Design-Time%20Features.md).  
  
## Siehe auch  
 [Entwickeln benutzerdefinierter Windows Forms\-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Gewusst wie: Entwickeln eines einfachen Windows Forms\-Steuerelements](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)   
 [Entwickeln eines zusammengesetzten Windows Forms\-Steuerelements](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)   
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [How to: Create a Windows Forms Control That Takes Advantage of Design\-Time Features](../Topic/How%20to:%20Create%20a%20Windows%20Forms%20Control%20That%20Takes%20Advantage%20of%20Design-Time%20Features.md)