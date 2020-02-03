---
title: Unterstützung hoher DPI-Werte
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
ms.openlocfilehash: a5c3125475c2de2cf83a3d97e356b26c0acdde99
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741894"
---
# <a name="high-dpi-support-in-windows-forms"></a>Hohe dpi-Unterstützung in Windows Forms

Ab .NET Framework 4,7 umfasst Windows Forms Verbesserungen für gängige Szenarien mit hoher dpi und dynamischer dpi. Dazu gehören:

- Verbesserungen an der Skalierung und dem Layout mehrerer Windows Forms Steuerelemente, wie z. b. das <xref:System.Windows.Forms.MonthCalendar>-Steuerelement und das <xref:System.Windows.Forms.CheckedListBox>-Steuerelement.

- Skalierung mit einem Durchlauf  In den .NET Framework 4,6 und früheren Versionen wurde die Skalierung über mehrere Durchgänge durchgeführt, was dazu führte, dass einige Steuerelemente mehr als notwendig skaliert wurden.

- Unterstützung für dynamische dpi-Szenarien, in denen der Benutzer den dpi-oder Skalierungsfaktor ändert, nachdem eine Windows Forms Anwendung gestartet wurde.

In Versionen der .NET Framework ab .NET Framework 4,7 ist die erweiterte Unterstützung für hohe dpi-Funktionen eine Opt-in-Funktion. Sie müssen Ihre Anwendung so konfigurieren, dass Sie von ihr genutzt wird.

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a>Konfigurieren Ihrer Windows Forms-App für hohe dpi-Unterstützung

Die neuen Windows Forms Features, die ein hohes dpi-Bewusstsein unterstützen, stehen nur in Anwendungen zur Verfügung, die auf die .NET Framework 4,7 abzielen und auf Windows-Betriebssystemen mit Windows 10 Creators Update ausgeführt werden.

Außerdem müssen Sie die folgenden Schritte ausführen, um die Unterstützung für hohe dpi-Unterstützung in Ihrer Windows Forms Anwendung zu konfigurieren:

- Deklarieren Sie Kompatibilität mit Windows 10.

  Fügen Sie hierzu der Manifest-Datei Folgendes hinzu:

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- Aktivieren Sie die dpi-Informationen pro Monitor in der Datei " *app. config* ".

  Windows Forms führt ein neues [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) Element ein, um neue Features und Anpassungen zu unterstützen, die ab dem .NET Framework 4,7 hinzugefügt wurden. Fügen Sie der Anwendungs Konfigurationsdatei Folgendes hinzu, um die neuen Features zu nutzen, die hohe dpi-Unterstützung unterstützen.

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > In früheren Versionen der .NET Framework wurde das Manifest verwendet, um eine hohe dpi-Unterstützung hinzuzufügen. Diese Vorgehensweise wird nicht mehr empfohlen, da Sie Einstellungen überschreibt, die in der Datei "App. config" definiert sind.

- Ruft die statische <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode auf.

  Dies sollte der erste Methoden aufzurufen in Ihrem Anwendungs Einstiegspunkt sein. Beispiel:

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a>Deaktivieren einzelner hoher dpi-Features

Wenn Sie den `DpiAwareness` Wert auf `PerMonitorV2` festlegen, werden alle hohen dpi-Funktionen aktiviert, die von .NET Framework Versionen ab dem .NET Framework 4,7 unterstützt werden. Dies ist in der Regel für die meisten Windows Forms Anwendungen ausreichend. Möglicherweise möchten Sie jedoch eine oder mehrere einzelne Features ablehnen. Der wichtigste Grund hierfür ist, dass Ihr vorhandener Anwendungscode diese Funktion bereits behandelt.  Wenn Ihre Anwendung z. b. die automatische Skalierung verarbeitet, empfiehlt es sich, das Feature für die automatische Anpassung der Größe wie folgt zu deaktivieren:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

Eine Liste der einzelnen Schlüssel und deren Werte finden Sie unter [Windows Forms Add Configuration-Elements](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).

## <a name="new-dpi-change-events"></a>Neue dpi-Änderungs Ereignisse

Beginnend mit dem .NET Framework 4,7 können Sie mithilfe von drei neuen Ereignissen dynamische dpi-Änderungen Programm gesteuert behandeln:

- <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, das ausgelöst wird, wenn die dpi-Einstellung für ein Steuerelement Programm gesteuert geändert wird, nachdem ein dpi-Änderungs Ereignis für das übergeordnete Steuerelement oder Formular aufgetreten ist.
- <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, das ausgelöst wird, wenn die dpi-Einstellung für ein Steuerelement Programm gesteuert geändert wird, bevor ein dpi-Änderungs Ereignis für das übergeordnete Steuerelement oder Formular aufgetreten ist.
- <xref:System.Windows.Forms.Form.DpiChanged>, das ausgelöst wird, wenn die dpi-Einstellung auf dem Anzeigegerät geändert wird, auf dem das Formular derzeit angezeigt wird.

## <a name="new-helper-methods-and-properties"></a>Neue Hilfsmethoden und-Eigenschaften

Der .NET Framework 4,7 fügt auch eine Reihe neuer Hilfsmethoden und-Eigenschaften hinzu, die Informationen zur DPI-Skalierung bereitstellen und Ihnen die Durchführung der DPI-Skalierung ermöglichen. Dazu gehören:

- <xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, der einen Wert von "logisch" in "Geräte Pixel" konvertiert.

- <xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, das ein Bitmap-Bild auf den logischen dpi-Wert für ein Gerät skaliert.

- <xref:System.Windows.Forms.Control.DeviceDpi%2A>, die den dpi-Wert für das aktuelle Gerät zurückgibt.

## <a name="versioning-considerations"></a>Überlegungen zur Versionsverwaltung

Neben der Ausführung auf .NET Framework 4,7-und Windows 10 Creators Update kann die Anwendung auch in einer Umgebung ausgeführt werden, in der Sie nicht mit hohen dpi-Verbesserungen kompatibel ist. In diesem Fall müssen Sie ein Fall Back für Ihre Anwendung entwickeln. Hierfür können Sie eine [benutzerdefinierte Zeichnung](./controls/user-drawn-controls.md) zum Verarbeiten der Skalierung durchführen.

Zu diesem Zweck müssen Sie auch das Betriebssystem bestimmen, unter dem Ihre APP ausgeführt wird. Hierfür können Sie Code wie den folgenden verwenden:

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

Beachten Sie, dass Ihre Anwendung Windows 10 nicht erfolgreich erkennt, wenn Sie nicht als unterstütztes Betriebssystem im Anwendungs Manifest aufgeführt ist.

Sie können auch die Version der .NET Framework überprüfen, für die die Anwendung erstellt wurde:

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a>Weitere Informationen

- [Konfigurations Element Windows Forms hinzufügen](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [Anpassen der Größe und Skalieren von Windows Forms](adjusting-the-size-and-scale-of-windows-forms.md)
