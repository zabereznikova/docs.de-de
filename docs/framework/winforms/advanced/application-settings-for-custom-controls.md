---
title: "Anwendungseinstellungen f&#252;r benutzerdefinierte Steuerelemente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Anwendungseinstellungen [Windows Forms], Benutzerdefinierte Steuerelemente"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Anwendungseinstellungen"
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Anwendungseinstellungen f&#252;r benutzerdefinierte Steuerelemente
Sie müssen bestimmte Aufgaben ausführen, damit die benutzerdefinierten Steuerelemente in den Anwendungseinstellungen erhalten bleiben, wenn die Steuerelemente in Anwendungen von Drittanbietern gehostet werden.  
  
 Der Großteil der Dokumentation über das Feature Anwendungseinstellungen wird in der Annahme geschrieben, dass Sie eine eigenständige Anwendung erstellen.  Wenn Sie aber ein Steuerelement erstellen, das von anderen Entwicklern in deren Anwendungen gehostet wird, müssen Sie einige zusätzliche Schritte beachten, damit die Einstellungseigenschaft des Steuerelements erhalten bleibt.  
  
## Anwendungseinstellungen und benutzerdefinierte Steuerelemente  
 Damit die Einstellungen des Steuerelements erhalten bleiben, muss es den Prozess kapseln, indem es eine eigene Wrapperklasse für dedizierte Anwendungseinstellungen erstellt, die von <xref:System.Configuration.ApplicationSettingsBase> abgeleitet ist.  Zusätzlich muss die Hauptsteuerelementklasse <xref:System.Configuration.IPersistComponentSettings> implementieren.  Die Schnittstelle enthält mehrere Eigenschaften sowie zwei Methoden, nämlich <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> und <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>.  Wenn Sie das Steuerelement dem Formular mit dem **Windows Forms\-Designer** in Visual Studio hinzufügen, ruft Windows Forms <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automatisch auf, wenn das Steuerelement initialisiert wird. Sie müssen <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> in der  `Dispose` \-Methode des Steuerelements selbst aufrufen.  
  
 Zusätzlich sollten Sie die folgenden Elemente implementieren, sodass die Anwendungseinstellungen für benutzerdefinierte Steuerelemente in Entwurfszeitumgebungen wie Visual Studio ordnungsgemäß funktionieren:  
  
1.  Eine benutzerdefinierte Anwendungseinstellungsklasse mit einem Konstruktor, der eine <xref:System.ComponentModel.IComponent> als einzelnen Parameter verwendet.  Mit dieser Klasse können Sie alle Anwendungseinstellungen speichern und laden.  Wenn Sie eine neue Instanz dieser Klasse erstellen, übergeben Sie das benutzerdefinierte Steuerelement mithilfe des Konstruktors.  
  
2.  Erstellen Sie diese benutzerdefinierte Einstellungsklasse, nachdem das Steuerelement erstellt und in einem Formular platziert wurde, z. B. im <xref:System.Windows.Forms.Form.Load>\-Ereignishandler des Formulars.  
  
 Anweisungen zum Erstellen einer benutzerdefinierten Einstellungsklasse finden Sie unter [Gewusst wie: Erstellen von Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
## Einstellungsschlüssel und freigegebene Einstellungen  
 Einige Steuerelemente können im gleichen Formular mehrfach verwendet werden.  In der Regel sollen die Einstellungen dieser Steuerelemente erhalten bleiben.  Mithilfe der <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>\-Eigenschaft von <xref:System.Configuration.IPersistComponentSettings> können Sie eine eindeutige Zeichenfolge bereitstellen, mit der Sie mehrere Versionen eines Steuerelements auf einem Formular eindeutig machen können.  
  
 Die einfachste Art, <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> zu implementieren, besteht darin, die <xref:System.Windows.Forms.Control.Name%2A>\-Eigenschaft des Steuerelements für den <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> zu verwenden.  Wenn Sie die Einstellungen des Steuerelements laden oder speichern, übernehmen Sie den <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>\-Wert für die <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A>\-Eigenschaft der <xref:System.Configuration.ApplicationSettingsBase>\-Klasse.  Anwendungseinstellungen verwenden diesen eindeutigen Schlüssel, wenn die Einstellungen des Benutzers in XML erhalten bleiben.  Im folgenden Codebeispiel wird gezeigt, wie ein  `<userSettings>` \-Abschnitt für ein benutzerdefiniertes Steuerelement mit dem Namen  `CustomControl1`  aussehen könnte, das eine Einstellung für die  `Text` \-Eigenschaft speichert.  
  
```  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 Alle Instanzen eines Steuerelements, die keinen Wert für <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> bereitstellen, verfügen über die gleichen Einstellungen.  
  
## Siehe auch  
 <xref:System.Configuration.ApplicationSettingsBase>   
 <xref:System.Configuration.IPersistComponentSettings>   
 [Architektur der Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)