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
ms.openlocfilehash: fbf2d7b61b34a2cd4641a77ee1f2fcdff7f3c3fe
ms.sourcegitcommit: b7763f3435635850a76d4cbcf09bdce6c019208a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2018
ms.locfileid: "34483540"
---
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="7b32e-102">Hohe DPI-Unterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7b32e-102">High DPI support in Windows Forms</span></span>

<span data-ttu-id="7b32e-103">Beginnend mit der .NET Framework-4.7, bietet Windows Forms Erweiterungen für allgemeine hohen dpi-WERTEN und dynamische DPI-Szenarien.</span><span class="sxs-lookup"><span data-stu-id="7b32e-103">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="7b32e-104">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="7b32e-104">These include:</span></span> 

- <span data-ttu-id="7b32e-105">Verbesserungen bei der die Skalierung und das Layout einer Reihe von Windows Forms-Steuerelemente, z. B. die <xref:System.Windows.Forms.MonthCalendar> Steuerelement und dem <xref:System.Windows.Forms.CheckedListBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7b32e-105">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span> 

- <span data-ttu-id="7b32e-106">Single-Pass-Skalierung.</span><span class="sxs-lookup"><span data-stu-id="7b32e-106">Single-pass scaling.</span></span>  <span data-ttu-id="7b32e-107">In der .NET Framework 4.6 und früheren Versionen wurde Skalierung über mehrere Durchläufe ausgeführt verursacht einige Steuerelemente skaliert werden mehr als notwendig war.</span><span class="sxs-lookup"><span data-stu-id="7b32e-107">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="7b32e-108">Unterstützung für dynamische DPI-Szenarien, in denen der Benutzer eine Faktor für die DPI-Wert oder der Dezimalstellen ändert, nachdem Windows Forms-Anwendung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="7b32e-108">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="7b32e-109">In Versionen von .NET Framework, beginnend mit der .NET Framework-4.7 ist verbesserte Unterstützung für hohe DPI eine opt-in-Funktion.</span><span class="sxs-lookup"><span data-stu-id="7b32e-109">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="7b32e-110">Konfigurieren Sie die Ihre Anwendung zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="7b32e-110">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="7b32e-111">Konfigurieren Ihre Windows Forms-Anwendung auf hoher DPI-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="7b32e-111">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="7b32e-112">Die neue Windows Forms-Funktionen, die Unterstützung hoher DPI-Ausführung stehen nur in Anwendungen, die .NET Framework-4.7 und auf Windows-Betriebssystemen ab Windows 10-Ersteller-Update ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7b32e-112">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span> 

<span data-ttu-id="7b32e-113">Um hohe DPI-Unterstützung in der Windows Forms-Anwendung zu konfigurieren, müssen Sie außerdem Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="7b32e-113">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="7b32e-114">Deklarieren Sie die Kompatibilität mit Windows 10.</span><span class="sxs-lookup"><span data-stu-id="7b32e-114">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="7b32e-115">Zu diesem Zweck fügen Sie Folgendes in die Manifestdatei hinzu:</span><span class="sxs-lookup"><span data-stu-id="7b32e-115">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft.com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="7b32e-116">Aktivieren von pro-Monitor-DPI-wissen in der *"App.config"* Datei.</span><span class="sxs-lookup"><span data-stu-id="7b32e-116">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="7b32e-117">Windows Forms bietet den neuen [ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../../../docs/framework/configure-apps/file-schema/winforms/index.md) -Element zur Unterstützung der neuen Features und Anpassungen, die beginnend mit der .NET Framework-4.7 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7b32e-117">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../docs/framework/configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="7b32e-118">Um die neuen Funktionen nutzen, die hohen dpi-WERTEN zu unterstützen, fügen Sie Folgendes in der Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7b32e-118">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>   

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>      
  ```
   
  > [!IMPORTANT]
  > <span data-ttu-id="7b32e-119">In früheren Versionen von .NET Framework können Sie zum Hinzufügen der Unterstützung für hohe DPI das Manifest verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b32e-119">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="7b32e-120">Dieser Ansatz wird nicht mehr empfohlen, da er auf die Datei "App.config" definierte Einstellungen überschreibt.</span><span class="sxs-lookup"><span data-stu-id="7b32e-120">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>
   
- <span data-ttu-id="7b32e-121">Rufen Sie die statische <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="7b32e-121">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>
   
  <span data-ttu-id="7b32e-122">Dies sollte der erste Methodenaufruf in der Einstiegspunkt der Anwendung sein.</span><span class="sxs-lookup"><span data-stu-id="7b32e-122">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="7b32e-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7b32e-123">For example:</span></span>
   
  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());   
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="7b32e-124">Wenn Sie keine einzelne hoher DPI-Funktionen</span><span class="sxs-lookup"><span data-stu-id="7b32e-124">Opting out of individual high DPI features</span></span>

<span data-ttu-id="7b32e-125">Festlegen der `DpiAwareness` Wert `PerMonitorV2` aktiviert alle hohe DPI Awareness Funktionen von .NET Framework-Versionen ab der .NET Framework-4.7 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7b32e-125">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="7b32e-126">In der Regel ist dies ausreichend für die meisten Windows Forms-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="7b32e-126">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="7b32e-127">Allerdings empfiehlt es sich um eine oder mehrere einzelne Funktionen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="7b32e-127">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="7b32e-128">Der wichtigste Grund dafür ist, dass der vorhandene Anwendungscode diese Funktion bereits verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="7b32e-128">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="7b32e-129">Wenn eine Anwendung behandelt die automatische Skalierung, sollten Sie z. B. die automatische Größenänderung-Funktion wie folgt deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="7b32e-129">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" /> 
</System.Windows.Forms.ApplicationConfigurationSection>    
```

<span data-ttu-id="7b32e-130">Eine Liste der einzelnen Schlüssel und ihre Werte, finden Sie unter [hinzufügen Konfigurationselement für Windows Forms](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span><span class="sxs-lookup"><span data-stu-id="7b32e-130">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="7b32e-131">Neue DPI-Change-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="7b32e-131">New DPI change events</span></span>

<span data-ttu-id="7b32e-132">Drei neue Ereignisse, die beginnend mit der .NET Framework-4.7, können Sie dynamische DPI Änderungen programmgesteuert zu verarbeiten:</span><span class="sxs-lookup"><span data-stu-id="7b32e-132">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="7b32e-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, der Fehler wird ausgelöst, wenn die DPI-Einstellung für ein Steuerelement programmgesteuert, nachdem ein Änderungsereignis DPI-Wert für das übergeordnete Steuerelement geändert wird oder Formular aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7b32e-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="7b32e-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, der Fehler wird ausgelöst, wenn die DPI-Einstellung für ein Steuerelement programmgesteuert, bevor ein Änderungsereignis DPI-Wert für das übergeordnete Steuerelement geändert wird oder Formular aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7b32e-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="7b32e-135"><xref:System.Windows.Forms.Form.DpiChanged>, der Fehler wird ausgelöst, wenn die DPI-Einstellung auf dem Anzeigegerät ändert, in dem das Formular ist derzeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7b32e-135"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="7b32e-136">Neue Hilfsmethoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7b32e-136">New helper methods and properties</span></span>

<span data-ttu-id="7b32e-137">Die .NET Framework-4.7 fügt auch eine Reihe von neuen Hilfsmethoden und Eigenschaften, die Aufschluss darüber geben DPI-Skalierung und ermöglichen es Ihnen, die DPI-Skalierung ausführen.</span><span class="sxs-lookup"><span data-stu-id="7b32e-137">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="7b32e-138">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="7b32e-138">These include:</span></span>

- <span data-ttu-id="7b32e-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, der einen Wert von logischen Koordinaten in Gerätepixeln konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7b32e-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="7b32e-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, die ein Bitmapbild in der logischen DPI-Wert für ein Gerät skaliert.</span><span class="sxs-lookup"><span data-stu-id="7b32e-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="7b32e-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, wobei der DPI-Wert für das aktuelle Gerät zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7b32e-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="7b32e-142">Versionsverwaltung Überlegungen</span><span class="sxs-lookup"><span data-stu-id="7b32e-142">Versioning considerations</span></span>

<span data-ttu-id="7b32e-143">Zusätzlich zum auf .NET Framework 4.7 "und" Ersteller-Update für Windows 10 ausgeführt wird, kann die Anwendung auch in einer Umgebung ausführen in der er nicht kompatibel mit hohen DPI-Verbesserungen ist.</span><span class="sxs-lookup"><span data-stu-id="7b32e-143">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="7b32e-144">In diesem Fall müssen Sie ein Fallback für Ihre Anwendung zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="7b32e-144">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="7b32e-145">Hierzu können Sie zum Ausführen [benutzerdefinierte Zeichnung](./controls/user-drawn-controls.md) Skalierung behandelt.</span><span class="sxs-lookup"><span data-stu-id="7b32e-145">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="7b32e-146">Zu diesem Zweck müssen Sie auch das Betriebssystem zu bestimmen, auf dem die app ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7b32e-146">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="7b32e-147">Sie können Code wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="7b32e-147">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="7b32e-148">Beachten Sie, dass die Anwendung erfolgreich Windows 10 erkennen wird nicht als ein unterstütztes Betriebssystem im Anwendungsmanifest danach wurde nicht.</span><span class="sxs-lookup"><span data-stu-id="7b32e-148">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="7b32e-149">Sie können auch die Version von .NET Framework suchen, denen für die Anwendung erstellt wurde:</span><span class="sxs-lookup"><span data-stu-id="7b32e-149">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="7b32e-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b32e-150">See also</span></span>

[<span data-ttu-id="7b32e-151">Windows Forms hinzufügen Konfigurationselement</span><span class="sxs-lookup"><span data-stu-id="7b32e-151">Windows Forms Add Configuration Element</span></span>](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)  
[<span data-ttu-id="7b32e-152">Anpassen der Größe und Skalieren von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7b32e-152">Adjusting the Size and Scale of Windows Forms</span></span>](../../../docs/framework/winforms/adjusting-the-size-and-scale-of-windows-forms.md)
