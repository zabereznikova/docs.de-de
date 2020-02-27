---
title: Entwickeln von Steuerelementen zur Entwurfszeit
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7626e1efbb30ef3bfe9b5b1278c0adb18dd5944b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628708"
---
# <a name="develop-windows-forms-controls-at-design-time"></a>Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit

NET Framework bietet Autoren von Steuerelementen eine Fülle von Technologien zum Erstellen von Steuerelementen. Autoren sind nicht mehr darauf beschränkt, zusammengesetzte Steuerelemente zu entwerfen, die als Auflistung bereits vorhandener Steuerelemente verwendet werden. Durch Vererbung können Sie eigene Steuerelemente aus bereits vorhandenen zusammengesetzten Steuerelementen bzw. bereits vorhandenen Windows Forms-Steuerelementen erstellen. Sie können auch eigene Steuerelemente entwerfen, durch die das benutzerdefinierte Zeichnen implementiert wird. Dank dieser Möglichkeiten zeichnen sich sowohl die Entwurfsfeatures als auch die Funktionalität der grafischen Oberfläche durch eine hohe Flexibilität aus. Um die Vorteile dieser Features nutzen zu können, sollten Sie mit den Konzepten der objektbasierten Programmierung vertraut sein.

> [!NOTE]
> Es ist nicht erforderlich, ein umfassendes Verständnis der Vererbung zu haben, aber Sie finden es möglicherweise hilfreich, wenn Sie auf [Grundlagen der Vererbung (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)verweisen.

Informationen zum Erstellen benutzerdefinierter Steuerelemente zur Verwendung in Web Forms finden Sie unter [Entwickeln von benutzerdefinierten ASP.NET-Serversteuerelementen](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).

## <a name="in-this-section"></a>In diesem Abschnitt

Exemplarische Vorgehensweise [: Erstellen eines zusammengesetzten Steuer](walkthrough-authoring-a-composite-control-with-visual-csharp.md) Elements\
Veranschaulicht das Erstellen eines einfachen zusammengesetzten Steuerelements in Visual C#.

Exemplarische Vorgehensweise [: Vererben von einem Windows Forms-Steuer](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md) Element\
Veranschaulicht, wie ein einfaches Windows Forms-Steuerelement unter Verwendung der Vererbung in Visual C# erstellt wird.

Exemplarische [Vorgehensweise: Ausführen allgemeiner Aufgaben mithilfe von Designer Aktionen](perform-common-tasks-design-actions.md)\
Veranschaulicht, wie das Smarttagfeature auf Windows Forms-Steuerelemente angewendet wird.

Exemplarische Vorgehensweise [: Serialisieren von Auflistungen von Standard Typen mit dem DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md) -\
Zeigt, wie das <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType>-Attribut verwendet wird, um eine Auflistung zu serialisieren.

[Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)\
Veranschaulicht das Debuggen des Verhaltens eines Windows Forms-Steuerelements zur Entwurfszeit.

Exemplarische Vorgehensweise [: Erstellen eines Windows Forms-Steuer Elements, das Visual Studio-Entwurfszeit Funktionen](creating-a-wf-control-design-time-features.md) nutzt\
Zeigt, wie ein zusammengesetztes Steuerelement nahtlos in die Entwurfsumgebung integriert wird.

[Vorgehensweise: Erstellen von Steuerelementen für Windows Forms](how-to-author-controls-for-windows-forms.md)\
Bietet einen Überblick über die Aspekte der Implementierung eines Windows Forms-Steuerelements.

[Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen](how-to-author-composite-controls.md)\
Veranschaulicht, wie ein Steuerelement durch Vererbung von einem zusammengesetzten Steuerelement erstellt wird.

[Vorgehensweise: Erben von der UserControl-Klasse](how-to-inherit-from-the-usercontrol-class.md)\
Bietet eine Übersicht über das Verfahren zum Erstellen eines zusammengesetzten Steuerelements.

[Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen](how-to-inherit-from-existing-windows-forms-controls.md)\
Zeigt, wie ein erweitertes Steuerelement erstellt wird, indem von der <xref:System.Windows.Forms.Button> Steuerelement Klasse geerbt wird.

[Vorgehensweise: Erben von der Control-Klasse](how-to-inherit-from-the-control-class.md)\
Bietet eine Übersicht über das Erstellen eines erweiterten Steuerelements.

Gewusst [wie: Ausrichten eines Steuer Elements an den Kanten von Formularen zur Entwurfszeit](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)\
Zeigt, wie Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft verwenden, um das Steuerelement an der Kante des Formulars auszurichten, das es einnimmt.

[Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)\
Veranschaulicht das Verfahren, in dem das Steuerelement so installiert wird, dass es im Dialogfeld **Toolbox anpassen** angezeigt wird.

Gewusst [wie: Bereitstellen einer Toolbox Bitmap für ein Steuer](how-to-provide-a-toolbox-bitmap-for-a-control.md) Element\
Zeigt, wie die <xref:System.Drawing.ToolboxBitmapAttribute> verwendet wird, um ein Symbol neben dem benutzerdefinierten Steuerelement in der **Toolbox**anzuzeigen.

[Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)\
Veranschaulicht, wie der **UserControl-Testcontainer** verwendet wird, um das Verhalten eines zusammengesetzten Steuerelements zu testen.

[Entwurfszeitfehler im Windows Forms-Designer](design-time-errors-in-the-windows-forms-designer.md)\
Erläutert die Bedeutung und den Verwendungszweck der Entwurfszeitfehlerliste, die in Microsoft Visual Studio angezeigt wird, wenn der Windows Forms-Designer nicht geladen werden kann.

[Problembehandlung beim Erstellen von Komponenten und Steuerelementen](troubleshooting-control-and-component-authoring.md)\
Veranschaulicht, wie häufige Probleme diagnostiziert und behoben werden, die beim Erstellen einer benutzerdefinierten Komponente bzw. eines benutzerdefinierten Steuerelements auftreten können.

## <a name="reference"></a>Verweis

- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>

- <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>

## <a name="related-sections"></a>Verwandte Abschnitte

[Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](developing-custom-windows-forms-controls.md)\
Erörtert, wie Sie mit .NET Framework eigene benutzerdefinierte Steuerelemente erstellen können.

[Sprachunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md)\
Bietet eine Einführung in die Common Language Runtime, die zum Vereinfachen der Erstellung und Verwendung von Komponenten entworfen wurde. Ein wichtiger Aspekt dieser Vereinfachung ist die verbesserte Interoperabilität zwischen Komponenten, die mit verschiedenen Programmiersprachen geschrieben wurden. Durch die Common Language Specification (CLS) wird das Erstellen von Tools und Komponenten ermöglicht, die für mehrere Programmiersprachen ausgelegt sind.

[Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)\
Erläutert, wie Sie vorgehen müssen, damit eine Komponente oder ein Steuerelement im Dialogfeld **Toolbox anpassen** angezeigt wird.
