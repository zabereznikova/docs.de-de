---
title: "Anwendungseinstellungen für benutzerdefinierte Steuerelemente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e21a49b26a7493aaec31d5a97e627ce7925f39b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="application-settings-for-custom-controls"></a>Anwendungseinstellungen für benutzerdefinierte Steuerelemente
Führen Sie die bestimmte Aufgaben aus, um der benutzerdefinierten Steuerelemente bieten die Möglichkeit, Anwendungseinstellungen beizubehalten, wenn die Steuerelemente in der Anwendung eines Drittanbieters gehostet werden.  
  
 Unter der Annahme, dass Sie eine eigenständige Anwendung erstellen, wird ein Großteil der Dokumentation über die Funktion "Anwendungseinstellungen" geschrieben. Jedoch, wenn Sie in ihren Anwendungen ein Steuerelement, das als host für andere Entwickler fungiert erstellen, müssen Sie einige zusätzliche Schritte ausführen, für das Steuerelement seine Einstellungen beibehalten werden ordnungsgemäß.  
  
## <a name="application-settings-and-custom-controls"></a>Anwendungseinstellungen und benutzerdefinierte Steuerelemente  
 Für das Steuerelement, um die Einstellungen korrekt persistent zu speichern, müssen sie den Prozess kapseln, durch das Erstellen von eigenen dedizierten Anwendungen Wrapperklasse für Anwendungseinstellungen, abgeleitet <xref:System.Configuration.ApplicationSettingsBase>. Darüber hinaus muss die wichtigsten Steuerelementklasse implementieren die <xref:System.Configuration.IPersistComponentSettings>. Die Schnittstelle enthält mehrere Eigenschaften sowie zwei Methoden <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> und <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>. Wenn Sie das Steuerelement dem Formular mit Hinzufügen der **Windows Forms-Designer** in Visual Studio, Windows Forms rufen <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automatisch Wenn das Steuerelement initialisiert wird, rufen Sie <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> selbst in der `Dispose` die Methode des Steuerelements.  
  
 Darüber hinaus sollten Sie Folgendes in der Reihenfolge für Anwendungseinstellungen für benutzerdefinierte Steuerelemente zur Entwurfszeit Umgebungen wie Visual Studio ordnungsgemäß implementieren:  
  
1.  Eine benutzerdefinierte Anwendung Settings-Klasse mit einem Konstruktor, akzeptiert eine <xref:System.ComponentModel.IComponent> als einen einzelnen Parameter. Verwenden Sie diese Klasse zum Speichern und laden alle Einstellungen Ihrer Anwendung. Wenn Sie eine neue Instanz dieser Klasse erstellen, übergeben Sie das benutzerdefinierte Steuerelement mit dem Konstruktor.  
  
2.  Diese Klasse benutzerdefinierte Einstellungen erstellen, nachdem das Steuerelement erstellt und in einem Formular wie in der Form platziert wurde <xref:System.Windows.Forms.Form.Load> -Ereignishandler.  
  
 Anweisungen zum Erstellen einer CustomSettings-Klasse, finden Sie unter [Vorgehensweise: Erstellen von Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
## <a name="settings-keys-and-shared-settings"></a>Gemeinsam genutzte Einstellungen und Einstellungsschlüssel  
 Einige Steuerelemente können mehrere Male in derselben Form verwendet werden. In den meisten Fällen, sollten Sie diese Steuerelemente eigene individuellen Einstellungen beibehalten werden. Mit der <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> Eigenschaft <xref:System.Configuration.IPersistComponentSettings>, Sie können angeben, dass eine eindeutige Zeichenfolge, die fungiert, um mehrere Versionen eines Steuerelements in einem Formular eindeutig zu machen.  
  
 Die einfachste Methode zum Implementieren <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> ist die Verwendung der <xref:System.Windows.Forms.Control.Name%2A> Eigenschaft des Steuerelements für die <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>. Beim Laden oder speichern die Einstellungen des Steuerelements, übergeben Sie den Wert des <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> auf die <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> Eigenschaft von der <xref:System.Configuration.ApplicationSettingsBase> Klasse. Anwendungseinstellungen verwendet diesen eindeutigen Schlüssel an, wenn sie die Einstellungen des Benutzers in XML beibehalten wird. Das folgende Codebeispiel zeigt, wie eine `<userSettings>` Abschnitt sähe für eine Instanz eines benutzerdefinierten Steuerelements, das mit dem Namen `CustomControl1` , speichert eine Einstellung für die `Text` Eigenschaft.  
  
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
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.IPersistComponentSettings>  
 [Architektur der Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)
