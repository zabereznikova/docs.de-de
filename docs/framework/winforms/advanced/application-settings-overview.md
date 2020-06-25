---
title: Übersicht über Anwendungseinstellungen
description: Erfahren Sie mehr über das Feature "Anwendungseinstellungen" Windows Forms, z. b. das Erstellen und Speichern von Einstellungsdaten im Namen Ihrer Anwendung und ihrer Benutzer.
ms.date: 03/30/2017
f1_keywords:
- ApplicationsSettingsOverview
helpviewer_keywords:
- application settings [Windows Forms], about application settings
- dynamic properties
- user preferences [Windows Forms], tracking
ms.assetid: 0dd8bca5-a6bf-4ac4-8eec-5725d08b38dc
ms.openlocfilehash: 864cab72b26ff7989c570347fb88b4009e7d705a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324216"
---
# <a name="application-settings-overview"></a>Übersicht über Anwendungseinstellungen

In diesem Artikel wird erläutert, wie Einstellungsdaten im Namen Ihrer Anwendung und ihrer Benutzer erstellt und gespeichert werden.

 Die Funktion „Anwendungseinstellungen“ von Windows Forms erleichtert das Erstellen, Speichern und Verwalten von benutzerdefinierten Einstellungen für Anwendungen und Benutzer auf dem Clientcomputer. Mit Windows Forms-Anwendungseinstellungen können Sie nicht nur Anwendungsdaten wie Datenbankverbindungszeichenfolgen, sondern auch benutzerspezifische Daten, etwa Anwendungseinstellungen, speichern. Mithilfe von Visual Studio oder benutzerdefiniertem verwaltetem Code können Sie neue Einstellungen erstellen, diese vom Datenträger lesen bzw. sie darauf schreiben, sie an Eigenschaften in Ihren Formularen binden und Einstellungsdaten vor dem Laden und Speichern überprüfen.

 Anwendungseinstellungen ermöglichen Entwicklern das Speichern des Zustands in Ihrer Anwendung mithilfe von sehr geringem benutzerdefiniertem Code und sind ein Ersatz für dynamische Eigenschaften in früheren Versionen der .NET Framework. Anwendungseinstellungen enthalten zahlreiche Verbesserungen gegenüber dynamischen Eigenschaften, die schreibgeschützt und spät gebunden sind sowie mehr benutzerdefinierte Programmierung erfordern. Die dynamischen Eigenschaften Klassen wurden in .NET Framework 2,0 aufbewahrt, aber Sie sind lediglich shellklassen, die die Klassen für Anwendungseinstellungen schlank verpacken.

## <a name="what-are-application-settings"></a>Was sind Anwendungseinstellungen?
 Ihre Windows Forms Anwendungen benötigen häufig Daten, die für die Ausführung der Anwendung von entscheidender Bedeutung sind, die Sie jedoch nicht direkt in den Anwendungscode einschließen möchten. Wenn Ihre Anwendung einen Webdienst oder einen Datenbankserver verwendet, können Sie diese Informationen in einer separaten Datei speichern, damit Sie Sie in Zukunft ändern können, ohne Sie neu kompilieren zu müssen. Auf ähnliche Weise können Ihre Anwendungen die Speicherung von Daten erfordern, die für den aktuellen Benutzer spezifisch sind. Die meisten Anwendungen verfügen beispielsweise über Benutzereinstellungen, die das Aussehen und Verhalten der Anwendung anpassen.

 Anwendungseinstellungen tragen beiden dieser Anforderungen Rechnung, indem sie eine einfache Möglichkeit bereitstellen, um sowohl anwendungsspezifische als auch benutzerspezifische Einstellungen auf dem Clientcomputer zu speichern. Mithilfe von Visual Studio oder einem Code-Editor definieren Sie eine Einstellung für eine bestimmte Eigenschaft durch Angabe ihres Namens, Datentyps und Gültigkeitsbereichs (Anwendung oder Benutzer). Sie können sogar verwandte Einstellungen in benannten Gruppen ablegen, um ihre Verwendbarkeit und Lesbarkeit zu vereinfachen. Nachdem diese Einstellungen definiert wurden, werden sie dauerhaft gespeichert und zur Laufzeit automatisch zurück in den Speicher gelesen. Eine Architektur mit austauschbaren Komponenten ermöglicht die Änderung des Mechanismus für die dauerhafte Speicherung, doch standardmäßig wird das lokale Dateisystem verwendet.

 Anwendungseinstellungen funktionieren so, dass sie Daten als XML in unterschiedlichen Konfigurationsdateien (.config) dauerhaft speichern, je nachdem, ob die Einstellung anwendungsspezifisch oder benutzerspezifisch ist. In den meisten Fällen sind die anwendungsspezifischen Einstellungen schreibgeschützt. Da es sich dabei um Programminformationen handelt, müssen Sie sie in der Regel nicht überschreiben. Im Gegensatz dazu können benutzerspezifische Einstellungen zur Laufzeit problemlos gelesen und geschrieben werden, auch wenn Ihre Anwendung nur mit teilweiser Vertrauenswürdigkeit ausgeführt wird. Weitere Informationen zu teilweiser Vertrauenswürdigkeit finden Sie unter [Security in Windows Forms Overview](../security-in-windows-forms-overview.md).

 Einstellungen werden als XML-Fragmente in Konfigurationsdateien gespeichert. Anwendungsspezifische Einstellungen werden durch das `<applicationSettings>` -Element dargestellt und normalerweise in " *App*.exe.config" abgelegt, wobei *App* der Name Ihrer Hauptausführungsdatei ist. Benutzerspezifische Einstellungen werden durch das `<userSettings>` -Element dargestellt und in " *Benutzer*.config" abgelegt, wobei *Benutzer* der Benutzername der Person ist, die aktuell die Anwendung ausführt. Sie müssen die Datei " *App*.exe.config" mit Ihrer Anwendung bereitstellen. Die Architektur der Einstellungen erstellt die " *Benutzer*.config"-Dateien bei Bedarf, wenn die Anwendung Einstellungen für diesen Benutzer zum erste Mal speichert. Außerdem können Sie einen `<userSettings>` -Block in " *App*.exe.config" definieren, um Standardwerte für benutzerspezifische Einstellungen bereitzustellen.

 Benutzerdefinierte Steuerelemente können ihre eigenen Einstellungen auch speichern, indem die <xref:System.Configuration.IPersistComponentSettings> -Schnittstelle implementiert wird, die die <xref:System.Configuration.IPersistComponentSettings.SaveSettings%2A> -Methode verfügbar macht. Das Windows Forms-Steuerelement <xref:System.Windows.Forms.ToolStrip> implementiert diese Schnittstelle, um die Position von Symbolleisten und Symbolleistenelementen zwischen Anwendungssitzungen zu speichern. Weitere Informationen zu benutzerdefinierten Steuerelementen und Anwendungseinstellungen finden Sie unter [Application Settings for Custom Controls](application-settings-for-custom-controls.md).

## <a name="limitations-of-application-settings"></a>Einschränkungen von Anwendungseinstellungen
 Sie können keine Anwendungseinstellungen in einer nicht verwalteten Anwendung verwenden, die die .NET Framework hostet. Einstellungen funktionieren nicht in Umgebungen wie Visual Studio-Add-Ins, C++ für Microsoft Office, Steuerelementhosting in Internet Explorer oder Microsoft Outlook-Add-Ins und Projekte.

 Sie können derzeit keine Bindung an einige Eigenschaften in Windows Forms durchführen. Das bemerkenswerteste Beispiel ist die <xref:System.Windows.Forms.Form.ClientSize%2A> -Eigenschaft, weil das Binden an diese Eigenschaft zu unvorhersehbarem Verhalten zur Laufzeit führen würde. Sie können diese Probleme in der Regel umgehen, indem Sie diese Einstellungen programmgesteuert speichern und laden.

 Anwendungseinstellungen besitzen keine integrierte Funktion zum automatischen Verschlüsseln von Informationen. Sie sollten nie sicherheitsrelevante Informationen wie Datenbankkennwörter in Klartext speichern. Wenn Sie solche vertraulichen Informationen speichern möchten, sind Sie als Entwickler dafür verantwortlich, dass sie geschützt werden. Wenn Sie Verbindungszeichenfolgen speichern möchten, empfehlen wir Ihnen, die integrierte Sicherheit von Windows zu verwenden und nicht zur Hartcodierung von Kennwörtern in der URL zu greifen. Weitere Informationen finden Sie unter [Code Access Security and ADO.NET](../../data/adonet/code-access-security.md).

## <a name="getting-started-with-application-settings"></a>Erste Schritte mit Anwendungseinstellungen
 Wenn Sie Visual Studio verwenden, können Sie im Windows Forms-Designer mithilfe der **(ApplicationSettings)** -Eigenschaft im Fenster **Eigenschaften** Einstellungen definieren. Wenn Sie Einstellungen auf diese Weise definieren, erstellt Visual Studio automatisch eine benutzerdefinierte verwaltete Wrapper Klasse, die jede Einstellung einer Klassen Eigenschaft zuordnet. Visual Studio übernimmt außerdem das Binden der Einstellung an eine Eigenschaft in einem Formular oder Steuerelement, damit die Einstellungen des Steuerelements automatisch wiederhergestellt werden, wenn sein Formular angezeigt wird, und automatisch gespeichert werden, wenn das Formular geschlossen wird.

 Wenn Sie eine detailliertere Kontrolle über Ihre Einstellungen benötigen, können Sie Ihre eigene benutzerdefinierte Wrapperklasse für Anwendungseinstellungen definieren. Dies geschieht durch Ableiten einer Klasse von <xref:System.Configuration.ApplicationSettingsBase>, Hinzufügen einer Eigenschaft, die jeder Einstellung entspricht, und Anwenden bestimmter Attribute auf diese Eigenschaften. Detaillierte Informationen zum Erstellen von Wrapperklassen finden Sie unter [Architektur der Anwendungseinstellungen](application-settings-architecture.md).

 Sie können auch die <xref:System.Windows.Forms.Binding> -Klasse verwenden, um Einstellungen programmgesteuert an Eigenschaften in Formularen und Steuerelementen zu binden.

## <a name="see-also"></a>Siehe auch

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- <xref:System.Configuration.IPersistComponentSettings>
- [Vorgehensweise: Überprüfen von Anwendungseinstellungen](how-to-validate-application-settings.md)
- [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
- [Vorgehensweise: Lesen von Einstellungen zur Laufzeit mit C#](how-to-read-settings-at-run-time-with-csharp.md)
- [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](using-application-settings-and-user-settings.md)
- [Architektur der Anwendungseinstellungen](application-settings-architecture.md)
- [Anwendungseinstellungen für benutzerdefinierte Steuerelemente](application-settings-for-custom-controls.md)
