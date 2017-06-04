---
title: "Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit | Microsoft Docs"
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
  - "Steuerelemente für Windows Forms"
  - "Erstellen von Windows Forms-Steuerelemente"
  - "Steuerelemente [Windows Forms]"
  - "Steuerelemente [Windows Forms], erstellen"
  - "Benutzersteuerelemente [Windows Forms]"
  - "Benutzerdefinierte Steuerelemente [Windows Forms]"
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit
Für Autoren von Steuerelementen bietet .NET Framework eine Fülle von Technologie das Erstellen von Steuerelementen. Autoren sind nicht mehr darauf beschränkt, zum Entwerfen von zusammengesetzter Steuerelementen, die als Auflistung bereits vorhandener Steuerelemente verwendet. Durch Vererbung können Sie eigene Steuerelemente aus bereits vorhandenen zusammengesetzten Steuerelementen oder Windows Forms-Steuerelementen erstellen. Sie können auch eigene Steuerelemente entwerfen, die benutzerdefinierte Zeichnen implementiert. Diese Optionen ermöglichen ein hohes Maß an Flexibilität für den Entwurf und Funktionalität der visuellen Schnittstelle. Um diese Funktionen nutzen zu können, sollten Sie mit den Konzepten der objektbasierten Programmierung vertraut sein.  
  
> [!NOTE]
>  Es ist nicht erforderlich, damit eine gründliche Kenntnisse über Vererbung, jedoch kann es hilfreich zum Verweisen auf [nicht im BUILD: Vererbung in Visual Basic](http://msdn.microsoft.com/de-de/e5e6e240-ed31-4657-820c-079b7c79313c).  
  
 Wenn Sie benutzerdefinierte Steuerelemente zur Verwendung in Web Forms finden Sie unter erstellen möchten [Entwickeln von benutzerdefinierten ASP.NET-Serversteuerelementen](../Topic/Developing%20Custom%20ASP.NET%20Server%20Controls.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 Veranschaulicht das Erstellen eines einfachen zusammengesetzten Steuerelements in Visual Basic.  
  
 [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual c#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 Erstellen ein einfaches zusammengesetztes Steuerelements in c# veranschaulicht.  
  
 [Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 Veranschaulicht das Erstellen eines einfachen Windows Forms-Steuerelements mit Vererbung in Visual Basic.  
  
 [Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit Visual c#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 Veranschaulicht das Erstellen eines einfachen Windows Forms-Steuerelements mithilfe von Vererbung in c#.  
  
 [Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags auf Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 Veranschaulicht, wie das Smarttagfeature für Windows Forms-Steuerelemente.  
  
 [Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](../../../../docs/framework/winforms/controls/serializing-collections-designerserializationvisibilityattribute.md)  
 Veranschaulicht, wie die <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=fullName> Attribut, um eine Auflistung zu serialisieren.  
  
 [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 Zeigt, wie das Entwurfszeitverhalten eines Windows Forms-Steuerelements zu debuggen.  
  
 [Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfeatures nutzt](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 Zeigt, wie ein zusammengesetztes Steuerelement eng in der Design-Umgebung zu integrieren.  
  
 [Gewusst wie: Erstellen von Steuerelementen für Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 Bietet einen Überblick über die Aspekte der Implementierung eines Windows Forms-Steuerelements.  
  
 [Gewusst wie: Erstellen von zusammengesetzten Steuerelementen](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 Zeigt, wie Sie ein Steuerelement durch Erben von einem zusammengesetzten Steuerelement zu erstellen.  
  
 [Gewusst wie: erben von der UserControl-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 Bietet eine Übersicht über das Verfahren zum Erstellen eines zusammengesetzten Steuerelements.  
  
 [Gewusst wie: erben von vorhandenen Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 Zeigt, wie erstellen Sie ein erweitertes Steuerelement durch Vererbung von der <xref:System.Windows.Forms.Button> Klasse steuern.  
  
 [Gewusst wie: erben von der Control-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 Bietet eine Übersicht über das Erstellen eines erweiterten Steuerelements.  
  
 [Gewusst wie: ausrichten ein Steuerelements an den Rändern eines Formulars zur Entwurfszeit](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 Veranschaulicht, wie die <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft, um das Steuerelement an den Rand des Formulars ausrichten es einnimmt.  
  
 [Gewusst wie: Anzeigen eines Steuerelements in das Dialogfeld Toolboxelemente auswählen](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 Zeigt das Verfahren zum Installieren des Steuerelements, damit er in angezeigt wird der **Toolbox anpassen** Dialogfeld.  
  
 [Gewusst wie: Bereitstellen eine Toolboxbitmap für ein Steuerelement](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 Veranschaulicht, wie die <xref:System.Drawing.ToolboxBitmapAttribute> zum Anzeigen eines Symbols neben das benutzerdefinierte Steuerelement in der **Toolbox**.  
  
 [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 Veranschaulicht, wie die **UserControl-Testcontainer** um das Verhalten eines zusammengesetzten Steuerelements testen.  
  
 [Entwurfszeitfehler im Windows Forms-Designer](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)  
 Erläutert die Bedeutung und die Verwendung von Entwurfszeit-Fehlerliste, die in Microsoft Visual Studio angezeigt wird, wenn der Windows Forms-Designer nicht geladen.  
  
 [Problembehandlung bei Komponenten und Steuerelementen](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 Zeigt, wie diagnostizieren und beheben Probleme, die auftreten können, wenn Sie eine benutzerdefinierte Komponente oder ein Steuerelement erstellen.  
  
## <a name="reference"></a>Verweis  
 <xref:System.Windows.Forms.Control?displayProperty=fullName>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 Erläutert, wie eigene benutzerdefinierte Steuerelemente mit .NET Framework erstellen.  
  
 [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../../docs/standard/language-independence-and-language-independent-components.md)  
 Führt die CLR, die zum Vereinfachen der Erstellung und Verwendung von Komponenten entworfen wurde. Ein wichtiger Aspekt dieser Vereinfachung ist Verbesserte Interoperabilität zwischen Komponenten, die mit verschiedenen Programmiersprachen geschrieben wurden. Der Common Language Specification (CLS) ermöglicht das Erstellen von Tools und Komponenten, die mit verschiedenen Programmiersprachen arbeiten.  
  
 [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 Beschreibt, wie Sie die Komponente oder das Steuerelement anzuzeigenden Aktivieren der **Toolbox anpassen** Dialogfeld.