---
title: Anwendungseinstellungen für benutzerdefinierte Steuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
ms.openlocfilehash: 69a5caef8bab45503b9f34422de8c2ba2e7f01ff
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317297"
---
# <a name="application-settings-for-custom-controls"></a>Anwendungseinstellungen für benutzerdefinierte Steuerelemente
Sie müssen bestimmte Aufgaben aus, um Ihre benutzerdefinierten Steuerelemente bieten die Möglichkeit, Anwendungseinstellungen beizubehalten, wenn die Steuerelemente in Anwendungen von Drittanbietern gehostet werden, ausführen.  
  
 Unter der Annahme, dass Sie eine eigenständige Anwendung erstellen, wird ein Großteil der Dokumentation über die Funktion "Anwendungseinstellungen" geschrieben. Jedoch wenn Sie in ihren Anwendungen ein Steuerelement, der als anderer Entwickler Host erstellen, müssen Sie einige weitere Schritte ausführen, für das Steuerelement, dessen Einstellungen beizubehalten ordnungsgemäß.  
  
## <a name="application-settings-and-custom-controls"></a>Für Anwendungen und benutzerdefinierte Steuerelemente  
 Für das Steuerelement ordnungsgemäß Einstellungen beizubehalten, müssen sie den Prozess kapseln, erstellen Sie eine eigene dedizierten Anwendungen Wrapperklasse für Anwendungseinstellungen, abgeleitet <xref:System.Configuration.ApplicationSettingsBase>. Darüber hinaus muss die main-Control-Klasse implementieren die <xref:System.Configuration.IPersistComponentSettings>. Die Schnittstelle enthält verschiedene Eigenschaften als auch zwei Methoden, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> und <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>. Wenn Sie das Steuerelement dem Formular mit Hinzufügen der **Windows Forms-Designer** in Visual Studio, Windows Forms rufen <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automatisch Wenn das Steuerelement initialisiert wird, rufen Sie <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> selbst in die `Dispose` die Methode des Steuerelements.  
  
 Darüber hinaus müssen Sie Folgendes in der Reihenfolge für Anwendungseinstellungen für benutzerdefinierte Steuerelemente zum ordnungsgemäßen in zur Entwurfszeit-Umgebungen wie Visual Studio implementieren:  
  
1. Eine benutzerdefinierte Anwendung Settings-Klasse mit einem Konstruktor, akzeptiert eine <xref:System.ComponentModel.IComponent> als einzelner Parameter. Verwenden Sie diese Klasse zum Speichern und laden alle Einstellungen Ihrer Anwendung. Wenn Sie eine neue Instanz dieser Klasse erstellen, übergeben Sie das benutzerdefinierte Steuerelement mit dem Konstruktor.  
  
2. Diese benutzerdefinierten Einstellungen-Klasse erstellen, nachdem das Steuerelement erstellt und in der Form eines Formulars, wie z. B. platziert wurde <xref:System.Windows.Forms.Form.Load> -Ereignishandler.  
  
 Anweisungen zum Erstellen einer CustomSettings-Klasse, finden Sie unter [Vorgehensweise: Erstellen von Anwendungseinstellungen](how-to-create-application-settings.md).  
  
## <a name="settings-keys-and-shared-settings"></a>Freigegebene Einstellungen und Einstellungsschlüssel  
 Einige Steuerelemente können mehrere Male in derselben Form verwendet werden. In den meisten Fällen, sollten Sie diese Steuerelemente auf ihre eigenen individuellen Einstellungen beizubehalten. Mit der <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> Eigenschaft <xref:System.Configuration.IPersistComponentSettings>, Sie können angeben, dass eine eindeutige Zeichenfolge, die mehrere Versionen eines Steuerelements in einem Formular eindeutig machen können.  
  
 Die einfachste Methode zum Implementieren <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> ist die Verwendung der <xref:System.Windows.Forms.Control.Name%2A> -Eigenschaft des Steuerelements für die <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>. Beim Laden oder speichern die Einstellungen des Steuerelements, übergeben Sie den Wert des <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> auf die <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> Eigenschaft der <xref:System.Configuration.ApplicationSettingsBase> Klasse. Anwendungseinstellungen verwendet diesen eindeutigen Schlüssel an, wenn sie die Einstellungen des Benutzers in XML beibehalten wird. Im folgenden Codebeispiel wird veranschaulicht, wie eine `<userSettings>` Abschnitt möglicherweise eine Instanz eines benutzerdefinierten Steuerelements mit dem Namen gesucht `CustomControl1` , speichert es sich um eine Einstellung für die `Text` Eigenschaft.  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 Alle Instanzen eines Steuerelements, die keinen Wert für bereitstellen <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> werden die gleichen Einstellungen verwenden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.IPersistComponentSettings>
- [Architektur der Anwendungseinstellungen](application-settings-architecture.md)
