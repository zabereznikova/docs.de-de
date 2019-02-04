---
title: Hohe DPI-Unterstützung in Windows Forms
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b5ad28fbfd668819b0bcab30c33892679b4bd8c
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674918"
---
# <a name="high-dpi-support-in-windows-forms"></a>Hohe DPI-Unterstützung in Windows Forms

Ab .NET Framework 4.7 enthält Windows Forms-Erweiterungen für allgemeine hohen dpi-WERTEN und dynamische DPI-Szenarien. Dazu gehören: 

- Verbesserungen bei der die Skalierung und das Layout einer Reihe von Windows Forms-Steuerelemente, z. B. die <xref:System.Windows.Forms.MonthCalendar> Steuerelement und die <xref:System.Windows.Forms.CheckedListBox> Steuerelement. 

- Single-Pass-Skalierung.  In .NET Framework 4.6 und früheren Versionen Skalierung über mehrere Durchläufe erfolgt die verursacht einige Steuerelemente skaliert werden, mehr als notwendig war.

- Unterstützung für dynamische DPI-Szenarien, in denen der Benutzer den Faktor für die DPI-Einstellung oder Skalierung geändert wird, nachdem eine Windows Forms-Anwendung gestartet wurde.

In Versionen von .NET Framework ab .NET Framework 4.7 ist die verbesserte Unterstützung für hohe DPI-Werte ein optionales Feature. Sie müssen Ihre Anwendung nutzen, konfigurieren.

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a>Konfigurieren der Windows Forms-app für die Unterstützung hoher DPI-Wert

Die neuen Windows Forms-Funktionen, die hohe DPI-Unterstützung unterstützen stehen nur in Anwendungen, die .NET Framework 4.7 und auf Windows-Betriebssystemen ab Windows 10 Creators Update ausgeführt werden. 

Um Unterstützung für hohe DPI-Werte in der Windows Forms-Anwendung konfigurieren zu können, müssen Sie außerdem Folgendes ausführen:

- Deklarieren Sie die Kompatibilität mit Windows 10.

  Zu diesem Zweck fügen Sie Folgendes zur Manifestdatei:

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- Aktivieren Sie monitorspezifische DPI-Unterstützung in den *"App.config"* Datei.

  Windows Forms wird ein neuer [ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../../../docs/framework/configure-apps/file-schema/winforms/index.md) Element zur Unterstützung der neuen Features und Anpassungen, die ab .NET Framework 4.7 hinzugefügt. Um die neuen Funktionen nutzen, die hohe DPI-Werte unterstützen, fügen Sie Folgendes der Konfigurationsdatei Ihrer Anwendung.   

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>      
  ```
   
  > [!IMPORTANT]
  > In früheren Versionen von .NET Framework müssen Sie das Manifest hinzuzufügende Unterstützung hohen DPI-Wert verwendet. Dieser Ansatz wird nicht mehr empfohlen, da er auf die Datei "App.config" definierte Einstellungen überschreibt.
   
- Rufen Sie die statische <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode.
   
  Dies sollte der erste Methodenaufruf in der Einstiegspunkt für Ihre Anwendung sein. Zum Beispiel:
   
  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());   
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a>Deaktivieren der einzelnen Funktionen für hohe DPI-Wert

Festlegen der `DpiAwareness` Wert `PerMonitorV2` hohe DPI-Awareness-Funktionen, die von .NET Framework-Versionen ab .NET Framework 4.7 unterstützt werden können. In der Regel ist dies ausreichend, für die meisten Windows Forms-Anwendungen. Möglicherweise möchten jedoch ein oder mehrere einzelne Features deaktivieren. Der wichtigste Grund dafür ist, dass es sich bei Ihrem vorhandenen Code der Anwendung bereits die Funktion behandelt.  Beispielsweise wenn Ihre Anwendung die automatische Skalierung, können Sie die automatische Größenänderung-Funktion wie folgt deaktivieren möchten:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" /> 
</System.Windows.Forms.ApplicationConfigurationSection>    
```

Eine Liste der einzelnen Schlüssel und deren Werte, finden Sie unter [hinzufügen Konfigurationselement für Windows Forms](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).

## <a name="new-dpi-change-events"></a>Änderungsereignisse für die neue DPI-Wert

Drei neue Ereignisse, die ab .NET Framework 4.7, können Sie programmgesteuerte Behandlung der dynamische DPI-Änderungen:

- <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, der Fehler wird ausgelöst, wenn die DPI-Einstellung für ein Steuerelement programmgesteuert, nachdem ein DPI-Änderungsereignis für das übergeordnete Steuerelement geändert wird oder Formular auftritt.
- <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, der Fehler wird ausgelöst, wenn die DPI-Einstellung für ein Steuerelement programmgesteuert, bevor ein DPI-Änderungsereignis für das übergeordnete Steuerelement geändert wird oder Formular auftritt.
- <xref:System.Windows.Forms.Form.DpiChanged>, der Fehler wird ausgelöst, wenn die DPI-Einstellung auf dem Anzeigegerät ändert, in dem das Formular zurzeit angezeigt wird.

## <a name="new-helper-methods-and-properties"></a>Neue Helper-Methoden und Eigenschaften

.NET Framework 4.7 fügt auch eine Reihe von neuen Helper-Methoden und Eigenschaften, die Aufschluss über die DPI-Skalierung und ermöglichen es Ihnen, führen Sie die DPI-Skalierung. Dazu gehören:

- <xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, die konvertiert einen Wert von logischen Koordinaten an.

- <xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, die skaliert, dass ein Bitmap-Bild, um den logischen DPI-Wert für ein Gerät.

- <xref:System.Windows.Forms.Control.DeviceDpi%2A>, womit der DPI-Wert für das aktuelle Gerät.

## <a name="versioning-considerations"></a>Überlegungen zur Versionskontrolle

Zusätzlich zu der auf .NET Framework 4.7 und Windows 10 Creators Update ausgeführt wird, kann Ihre Anwendung auch in einer Umgebung ausführen in dem er nicht kompatibel mit hohen DPI-Verbesserungen ist. In diesem Fall müssen Sie einen Fallback für Ihre Anwendung zu entwickeln. Hierzu können Sie zum Ausführen [benutzerdefinierte Zeichnung](./controls/user-drawn-controls.md) für die Skalierung.

Zu diesem Zweck müssen Sie auch das Betriebssystem zu ermitteln, auf dem Ihre app ausgeführt wird. Sie können dies tun, mit den folgenden Code:

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

Beachten Sie, dass die Anwendung erfolgreich Windows 10 erkennen wird nicht, wenn es als ein unterstütztes Betriebssystem im Anwendungsmanifest aufgeführt war nicht.

Sie können auch die Version von .NET Framework überprüfen, denen die Anwendung erstellt wurde:

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a>Siehe auch

- [Windows Forms hinzufügen Konfigurationselement](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [Anpassen der Größe und Skalieren von Windows Forms](../../../docs/framework/winforms/adjusting-the-size-and-scale-of-windows-forms.md)
