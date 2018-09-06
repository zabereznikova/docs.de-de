---
title: Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
ms.openlocfilehash: b58318a3e0e9881725d3c260251288c720fa4132
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44041341"
---
# <a name="developing-windows-forms-controls-at-design-time"></a>Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit
NET Framework bietet Autoren von Steuerelementen eine Fülle von Technologien zum Erstellen von Steuerelementen. Autoren sind nicht mehr darauf beschränkt, zusammengesetzte Steuerelemente zu entwerfen, die als Auflistung bereits vorhandener Steuerelemente verwendet werden. Durch Vererbung können Sie eigene Steuerelemente aus bereits vorhandenen zusammengesetzten Steuerelementen bzw. bereits vorhandenen Windows Forms-Steuerelementen erstellen. Sie können auch eigene Steuerelemente entwerfen, durch die das benutzerdefinierte Zeichnen implementiert wird. Dank dieser Möglichkeiten zeichnen sich sowohl die Entwurfsfeatures als auch die Funktionalität der grafischen Oberfläche durch eine hohe Flexibilität aus. Um die Vorteile dieser Features nutzen zu können, sollten Sie mit den Konzepten der objektbasierten Programmierung vertraut sein.  
  
> [!NOTE]
>  Es ist nicht erforderlich, damit Sie umfassende Informationen zu Vererbung, jedoch kann es hilfreich sein zum Verweisen auf [Grundlagen der Vererbung (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Informationen zum Erstellen benutzerdefinierter Steuerelemente zur Verwendung in Web Forms finden Sie unter [Entwickeln von benutzerdefinierten ASP.NET-Serversteuerelementen](https://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 Veranschaulicht das Erstellen eines einfachen zusammengesetzten Steuerelements in Visual Basic.  
  
 [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual C#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 Veranschaulicht das Erstellen eines einfachen zusammengesetzten Steuerelements in Visual C#.  
  
 [Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 Veranschaulicht, wie ein einfaches Windows Forms-Steuerelement unter Verwendung der Vererbung in Visual Basic erstellt wird.  
  
 [Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement mit Visual C#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 Veranschaulicht, wie ein einfaches Windows Forms-Steuerelement unter Verwendung der Vererbung in Visual C# erstellt wird.  
  
 [Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags auf Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 Veranschaulicht, wie das Smarttagfeature auf Windows Forms-Steuerelemente angewendet wird.  
  
 [Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](../../../../docs/framework/winforms/controls/serializing-collections-designerserializationvisibilityattribute.md)  
 Zeigt, wie die <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> Attribut, um eine Auflistung zu serialisieren.  
  
 [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 Veranschaulicht das Debuggen des Verhaltens eines Windows Forms-Steuerelements zur Entwurfszeit.  
  
 [Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfunktion nutzt](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 Zeigt, wie ein zusammengesetztes Steuerelement nahtlos in die Entwurfsumgebung integriert wird.  
  
 [Gewusst wie: Erstellen von Steuerelementen für Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 Bietet einen Überblick über die Aspekte der Implementierung eines Windows Forms-Steuerelements.  
  
 [Gewusst wie: Erstellen von zusammengesetzten Steuerelementen](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 Veranschaulicht, wie ein Steuerelement durch Vererbung von einem zusammengesetzten Steuerelement erstellt wird.  
  
 [Gewusst wie: Erben von der UserControl-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 Bietet eine Übersicht über das Verfahren zum Erstellen eines zusammengesetzten Steuerelements.  
  
 [Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 Veranschaulicht die Erstellung ein erweitertes Steuerelements durch Erben von der <xref:System.Windows.Forms.Button> -Klasse.  
  
 [Vorgehensweise: Erben von der Control-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 Bietet eine Übersicht über das Erstellen eines erweiterten Steuerelements.  
  
 [Vorgehensweise: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 Zeigt, wie die <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft, um das Steuerelement an den Rand des Formulars auszurichten, es belegt.  
  
 [Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 Veranschaulicht das Verfahren, in dem das Steuerelement so installiert wird, dass es im Dialogfeld **Toolbox anpassen** angezeigt wird.  
  
 [Vorgehensweise: Bereitstellen einer Toolboxbitmap für ein Steuerelement](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 Zeigt, wie die <xref:System.Drawing.ToolboxBitmapAttribute> zum Anzeigen eines Symbols neben einem benutzerdefinierten Steuerelement in der **Toolbox**.  
  
 [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 Veranschaulicht, wie der **UserControl-Testcontainer** verwendet wird, um das Verhalten eines zusammengesetzten Steuerelements zu testen.  
  
 [Entwurfszeitfehler im Windows Forms-Designer](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)  
 Erläutert die Bedeutung und den Verwendungszweck der Entwurfszeitfehlerliste, die in Microsoft Visual Studio angezeigt wird, wenn der Windows Forms-Designer nicht geladen werden kann.  
  
 [Problembehandlung beim Erstellen von Komponenten und Steuerelementen](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 Veranschaulicht, wie häufige Probleme diagnostiziert und behoben werden, die beim Erstellen einer benutzerdefinierten Komponente bzw. eines benutzerdefinierten Steuerelements auftreten können.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 Erörtert, wie Sie mit .NET Framework eigene benutzerdefinierte Steuerelemente erstellen können.  
  
 [Sprachunabhängigkeit und sprachunabhängige Komponenten](../../../../docs/standard/language-independence-and-language-independent-components.md)  
 Bietet eine Einführung in die Common Language Runtime, die zum Vereinfachen der Erstellung und Verwendung von Komponenten entworfen wurde. Ein wichtiger Aspekt dieser Vereinfachung ist die verbesserte Interoperabilität zwischen Komponenten, die mit verschiedenen Programmiersprachen geschrieben wurden. Durch die Common Language Specification (CLS) wird das Erstellen von Tools und Komponenten ermöglicht, die für mehrere Programmiersprachen ausgelegt sind.  
  
 [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 Erläutert, wie Sie vorgehen müssen, damit eine Komponente oder ein Steuerelement im Dialogfeld **Toolbox anpassen** angezeigt wird.
