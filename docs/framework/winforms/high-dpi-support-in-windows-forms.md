---
title: "Hohe DPI-Unterstützung in Windows Forms"
ms.custom: 
ms.date: 05/16/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a68c9278d4e8092be5c744109e56f7cb52498095
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="high-dpi-support-in-windows-forms"></a>Hohe DPI-Unterstützung in Windows Forms

Beginnend mit der .NET Framework-4.7, bietet Windows Forms Erweiterungen für allgemeine hohen dpi-WERTEN und dynamische DPI-Szenarien. Dazu gehören: 

- Verbesserungen bei der die Skalierung und das Layout einer Reihe von Windows Forms-Steuerelemente, z. B. die <xref:System.Windows.Forms.MonthCalendar> Steuerelement und dem <xref:System.Windows.Forms.CheckedListBox> Steuerelement. 

- Single-Pass-Skalierung.  In der .NET Framework 4.6 und früheren Versionen wurde Skalierung über mehrere Durchläufe ausgeführt verursacht einige Steuerelemente skaliert werden mehr als notwendig war.

- Unterstützung für dynamische DPI-Szenarien, in denen der Benutzer eine Faktor für die DPI-Wert oder der Dezimalstellen ändert, nachdem Windows Forms-Anwendung gestartet wurde.

In Versionen von .NET Framework, beginnend mit der .NET Framework-4.7 ist verbesserte Unterstützung für hohe DPI eine opt-in-Funktion. Konfigurieren Sie die Ihre Anwendung zu nutzen.

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a>Konfigurieren Ihre Windows Forms-Anwendung auf hoher DPI-Unterstützung

Die neue Windows Forms-Funktionen, die Unterstützung hoher DPI-Ausführung stehen nur in Anwendungen, die .NET Framework-4.7 und auf Windows-Betriebssystemen ab Windows 10-Ersteller-Update ausgeführt werden. 

Um hohe DPI-Unterstützung in der Windows Forms-Anwendung zu konfigurieren, müssen Sie außerdem Folgendes ausführen:

- Deklarieren Sie die Kompatibilität mit Windows 10.

  Zu diesem Zweck fügen Sie Folgendes in die Manifestdatei hinzu:

  ```xml
  <compatibility xmlns="urn:schemas-microsoft.comn:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- Aktivieren von pro-Monitor-DPI-wissen in der *"App.config"* Datei.

  Windows Forms bietet den neuen [ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../../../docs/framework/configure-apps/file-schema/winforms/index.md) -Element zur Unterstützung der neuen Features und Anpassungen, die beginnend mit der .NET Framework-4.7 hinzugefügt. Um die neuen Funktionen nutzen, die hohen dpi-WERTEN zu unterstützen, fügen Sie Folgendes in der Anwendungskonfigurationsdatei.   

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>      
  ```
   
  > [!IMPORTANT]
  > In früheren Versionen von .NET Framework können Sie zum Hinzufügen der Unterstützung für hohe DPI das Manifest verwendet. Dieser Ansatz wird nicht mehr empfohlen, da er auf die Datei "App.config" definierte Einstellungen überschreibt.
   
- Rufen Sie die statische <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode.
   
  Dies sollte der erste Methodenaufruf in der Einstiegspunkt der Anwendung sein. Zum Beispiel:
   
  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());   
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a>Wenn Sie keine einzelne hoher DPI-Funktionen

Festlegen der `DpiAwareness` Wert `PerMonitorV2` aktiviert alle hohe DPI Awareness Funktionen von .NET Framework-Versionen ab der .NET Framework-4.7 unterstützt. In der Regel ist dies ausreichend für die meisten Windows Forms-Anwendungen. Allerdings empfiehlt es sich um eine oder mehrere einzelne Funktionen zu beenden. Der wichtigste Grund dafür ist, dass der vorhandene Anwendungscode diese Funktion bereits verarbeitet.  Wenn eine Anwendung behandelt die automatische Skalierung, sollten Sie z. B. die automatische Größenänderung-Funktion wie folgt deaktivieren:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" /> 
</System.Windows.Forms.ApplicationConfigurationSection>    
```

Eine Liste der einzelnen Schlüssel und ihre Werte, finden Sie unter [hinzufügen Konfigurationselement für Windows Forms](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).

## <a name="new-dpi-change-events"></a>Neue DPI-Change-Ereignissen

Drei neue Ereignisse, die beginnend mit der .NET Framework-4.7, können Sie dynamische DPI Änderungen programmgesteuert zu verarbeiten:

- <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, der Fehler wird ausgelöst, wenn die DPI-Einstellung für ein Steuerelement programmgesteuert, nachdem ein Änderungsereignis DPI-Wert für das übergeordnete Steuerelement geändert wird oder Formular aufgetreten.
- <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, der Fehler wird ausgelöst, wenn die DPI-Einstellung für ein Steuerelement programmgesteuert, bevor ein Änderungsereignis DPI-Wert für das übergeordnete Steuerelement geändert wird oder Formular aufgetreten.
- <xref:System.Windows.Forms.Form.DpiChanged>, der Fehler wird ausgelöst, wenn die DPI-Einstellung auf dem Anzeigegerät ändert, in dem das Formular ist derzeit angezeigt.

## <a name="new-helper-methods-and-properties"></a>Neue Hilfsmethoden und Eigenschaften

Die .NET Framework-4.7 fügt auch eine Reihe von neuen Hilfsmethoden und Eigenschaften, die Aufschluss darüber geben DPI-Skalierung und ermöglichen es Ihnen, die DPI-Skalierung ausführen. Dazu gehören:

- <xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, der einen Wert von logischen Koordinaten in Gerätepixeln konvertiert.

- <xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, die ein Bitmapbild in der logischen DPI-Wert für ein Gerät skaliert.

- <xref:System.Windows.Forms.Control.DeviceDpi%2A>, wobei der DPI-Wert für das aktuelle Gerät zurückgegeben.

## <a name="versioning-considerations"></a>Versionsverwaltung Überlegungen

Zusätzlich zum auf .NET Framework 4.7 "und" Ersteller-Update für Windows 10 ausgeführt wird, kann die Anwendung auch in einer Umgebung ausführen in der er nicht kompatibel mit hohen DPI-Verbesserungen ist. In diesem Fall müssen Sie ein Fallback für Ihre Anwendung zu entwickeln. Hierzu können Sie zum Ausführen [benutzerdefinierte Zeichnung](./controls/user-drawn-controls.md) Skalierung behandelt.

Zu diesem Zweck müssen Sie auch das Betriebssystem zu bestimmen, auf dem die app ausgeführt wird. Sie können Code wie den folgenden verwenden:

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

Beachten Sie, dass die Anwendung erfolgreich Windows 10 erkennen wird nicht als ein unterstütztes Betriebssystem im Anwendungsmanifest danach wurde nicht.

Sie können auch die Version von .NET Framework suchen, denen für die Anwendung erstellt wurde:

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a>Siehe auch

[Windows Forms hinzufügen Konfigurationselement](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)  
[Anpassen der Größe und Skalieren von Windows Forms](../../../docs/framework/winforms/adjusting-the-size-and-scale-of-windows-forms.md)
