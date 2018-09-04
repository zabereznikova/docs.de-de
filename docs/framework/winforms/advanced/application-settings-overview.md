---
title: Übersicht über Anwendungseinstellungen
ms.date: 03/30/2017
f1_keywords:
- ApplicationsSettingsOverview
helpviewer_keywords:
- application settings [Windows Forms], about application settings
- dynamic properties
- user preferences [Windows Forms], tracking
ms.assetid: 0dd8bca5-a6bf-4ac4-8eec-5725d08b38dc
ms.openlocfilehash: e38be762fbfdaccc7d5ba01a1f24f5f3086ca8bf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503596"
---
# <a name="application-settings-overview"></a>Übersicht über Anwendungseinstellungen
In diesem Thema wird erläutert, wie Einstellungsdaten für Ihre Anwendung und deren Benutzer erstellt und gespeichert werden.  
  
 Die Funktion „Anwendungseinstellungen“ von Windows Forms erleichtert das Erstellen, Speichern und Verwalten von benutzerdefinierten Einstellungen für Anwendungen und Benutzer auf dem Clientcomputer. Mit Windows Forms-Anwendungseinstellungen können Sie nicht nur Anwendungsdaten wie Datenbankverbindungszeichenfolgen, sondern auch benutzerspezifische Daten, etwa Anwendungseinstellungen, speichern. Mithilfe von Visual Studio oder benutzerdefiniertem verwaltetem Code können Sie neue Einstellungen erstellen, diese vom Datenträger lesen bzw. sie darauf schreiben, sie an Eigenschaften in Ihren Formularen binden und Einstellungsdaten vor dem Laden und Speichern überprüfen.  
  
 Anwendungseinstellungen ermöglichen Entwicklern das Speichern des Zustands ihrer jeweiligen Anwendung mit sehr wenig benutzerdefiniertem Code und stellen einen Ersatz für die dynamischen Eigenschaften in früheren Versionen von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]dar. Anwendungseinstellungen enthalten zahlreiche Verbesserungen gegenüber dynamischen Eigenschaften, die schreibgeschützt und spät gebunden sind sowie mehr benutzerdefinierte Programmierung erfordern. Die dynamischen Eigenschaftenklassen wurden in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]beibehalten, sind aber nur noch Shell-Klassen, die nur einen schwachen Wrapper für die Anwendungseinstellungen-Klassen darstellen.  
  
## <a name="what-are-application-settings"></a>Was sind Anwendungseinstellungen?  
 Ihr Windows Forms-Anwendungen benötigen häufig Daten, die für die Ausführung der Anwendung von entscheidender Bedeutung sind, die Sie aber nicht direkt in den Anwendungscode einschließen möchten. Wenn Ihre Anwendung einen Webdienst oder einen Datenbankserver verwendet, sollten Sie diese Informationen in einer separaten Datei speichern, damit Sie sie später ändern können, ohne sie neu kompilieren zu müssen. Auf ähnliche Weise können Ihre Anwendungen die Speicherung von Daten erfordern, die für den aktuellen Benutzer spezifisch sind. Die meisten Anwendungen verfügen beispielsweise über Benutzereinstellungen, die das Aussehen und Verhalten der Anwendung anpassen.  
  
 Anwendungseinstellungen tragen beiden dieser Anforderungen Rechnung, indem sie eine einfache Möglichkeit bereitstellen, um sowohl anwendungsspezifische als auch benutzerspezifische Einstellungen auf dem Clientcomputer zu speichern. Mithilfe von Visual Studio oder einem Code-Editor definieren Sie eine Einstellung für eine bestimmte Eigenschaft durch Angabe ihres Namens, Datentyps und Gültigkeitsbereichs (Anwendung oder Benutzer). Sie können sogar verwandte Einstellungen in benannten Gruppen ablegen, um ihre Verwendbarkeit und Lesbarkeit zu vereinfachen. Nachdem diese Einstellungen definiert wurden, werden sie dauerhaft gespeichert und zur Laufzeit automatisch zurück in den Speicher gelesen. Eine Architektur mit austauschbaren Komponenten ermöglicht die Änderung des Mechanismus für die dauerhafte Speicherung, doch standardmäßig wird das lokale Dateisystem verwendet.  
  
 Anwendungseinstellungen funktionieren so, dass sie Daten als XML in unterschiedlichen Konfigurationsdateien (.config) dauerhaft speichern, je nachdem, ob die Einstellung anwendungsspezifisch oder benutzerspezifisch ist. In den meisten Fällen sind die anwendungsspezifischen Einstellungen schreibgeschützt. Da es sich dabei um Programminformationen handelt, müssen Sie sie in der Regel nicht überschreiben. Im Gegensatz dazu können benutzerspezifische Einstellungen zur Laufzeit problemlos gelesen und geschrieben werden, auch wenn Ihre Anwendung nur mit teilweiser Vertrauenswürdigkeit ausgeführt wird. Weitere Informationen zu teilweiser Vertrauenswürdigkeit finden Sie unter [Security in Windows Forms Overview](../../../../docs/framework/winforms/security-in-windows-forms-overview.md).  
  
 Einstellungen werden als XML-Fragmente in Konfigurationsdateien gespeichert. Anwendungsspezifische Einstellungen werden durch das `<application.Settings>` -Element dargestellt und normalerweise in " *App*.exe.config" abgelegt, wobei *App* der Name Ihrer Hauptausführungsdatei ist. Benutzerspezifische Einstellungen werden durch das `<userSettings>` -Element dargestellt und in " *Benutzer*.config" abgelegt, wobei *Benutzer* der Benutzername der Person ist, die aktuell die Anwendung ausführt. Sie müssen die Datei " *App*.exe.config" mit Ihrer Anwendung bereitstellen. Die Architektur der Einstellungen erstellt die " *Benutzer*.config"-Dateien bei Bedarf, wenn die Anwendung Einstellungen für diesen Benutzer zum erste Mal speichert. Außerdem können Sie einen `<userSettings>` -Block in " *App*.exe.config" definieren, um Standardwerte für benutzerspezifische Einstellungen bereitzustellen.  
  
 Benutzerdefinierte Steuerelemente können ihre eigenen Einstellungen auch speichern, indem die <xref:System.Configuration.IPersistComponentSettings> -Schnittstelle implementiert wird, die die <xref:System.Configuration.IPersistComponentSettings.SaveSettings%2A> -Methode verfügbar macht. Das Windows Forms-Steuerelement <xref:System.Windows.Forms.ToolStrip> implementiert diese Schnittstelle, um die Position von Symbolleisten und Symbolleistenelementen zwischen Anwendungssitzungen zu speichern. Weitere Informationen zu benutzerdefinierten Steuerelementen und Anwendungseinstellungen finden Sie unter [Application Settings for Custom Controls](../../../../docs/framework/winforms/advanced/application-settings-for-custom-controls.md).  
  
## <a name="limitations-of-application-settings"></a>Einschränkungen von Anwendungseinstellungen  
 Sie können keine Anwendungseinstellungen in einer nicht verwalteten Anwendung verwenden, die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]hostet. Einstellungen funktionieren nicht in Umgebungen wie Visual Studio-Add-Ins, C++ für Microsoft Office, Steuerelementhosting in Internet Explorer oder Microsoft Outlook-Add-Ins und Projekte.  
  
 Sie können derzeit keine Bindung an einige Eigenschaften in Windows Forms durchführen. Das bemerkenswerteste Beispiel ist die <xref:System.Windows.Forms.Form.ClientSize%2A> -Eigenschaft, weil das Binden an diese Eigenschaft zu unvorhersehbarem Verhalten zur Laufzeit führen würde. Sie können diese Probleme in der Regel umgehen, indem Sie diese Einstellungen programmgesteuert speichern und laden.  
  
 Anwendungseinstellungen besitzen keine integrierte Funktion zum automatischen Verschlüsseln von Informationen. Sie sollten nie sicherheitsrelevante Informationen wie Datenbankkennwörter in Klartext speichern. Wenn Sie solche vertraulichen Informationen speichern möchten, sind Sie als Entwickler dafür verantwortlich, dass sie geschützt werden. Wenn Sie Verbindungszeichenfolgen speichern möchten, empfehlen wir Ihnen, die integrierte Sicherheit von Windows zu verwenden und nicht zur Hartcodierung von Kennwörtern in der URL zu greifen. Weitere Informationen finden Sie unter [Code Access Security and ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md).  
  
## <a name="getting-started-with-application-settings"></a>Erste Schritte mit Anwendungseinstellungen  
 Wenn Sie Visual Studio verwenden, können Sie im Windows Forms-Designer mithilfe der **(ApplicationSettings)** -Eigenschaft im Fenster **Eigenschaften** Einstellungen definieren. Wenn Sie Einstellungen auf diese Weise definieren, erstellt Visual Studio automatisch eine benutzerdefinierte, verwaltete Wrapperklasse, die jede Einstellung einer Klasseneigenschaft zuordnet. Visual Studio übernimmt außerdem das Binden der Einstellung an eine Eigenschaft in einem Formular oder Steuerelement, damit die Einstellungen des Steuerelements automatisch wiederhergestellt werden, wenn sein Formular angezeigt wird, und automatisch gespeichert werden, wenn das Formular geschlossen wird.  
  
 Wenn Sie eine detailliertere Kontrolle über Ihre Einstellungen benötigen, können Sie Ihre eigene benutzerdefinierte Wrapperklasse für Anwendungseinstellungen definieren. Dies geschieht durch Ableiten einer Klasse von <xref:System.Configuration.ApplicationSettingsBase>, Hinzufügen einer Eigenschaft, die jeder Einstellung entspricht, und Anwenden bestimmter Attribute auf diese Eigenschaften. Weitere Informationen zum Erstellen von Wrapperklassen finden Sie unter [Application Settings Architecture](../../../../docs/framework/winforms/advanced/application-settings-architecture.md).  
  
 Sie können auch die <xref:System.Windows.Forms.Binding> -Klasse verwenden, um Einstellungen programmgesteuert an Eigenschaften in Formularen und Steuerelementen zu binden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.SettingsProvider>  
 <xref:System.Configuration.LocalFileSettingsProvider>  
 <xref:System.Configuration.IPersistComponentSettings>  
 [Gewusst wie: Überprüfen von Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/how-to-validate-application-settings.md)  
 [Verwalten von Anwendungseinstellungen (.NET)](https://msdn.microsoft.com/library/35254321-ad14-47d9-b8c6-39ab3203c5d9)  
 [Gewusst wie: Lesen von Einstellungen zur Laufzeit mit C#](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
 [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Architektur der Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)  
 [Anwendungseinstellungen für benutzerdefinierte Steuerelemente](../../../../docs/framework/winforms/advanced/application-settings-for-custom-controls.md)
