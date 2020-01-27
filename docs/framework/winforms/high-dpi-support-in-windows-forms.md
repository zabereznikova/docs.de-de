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
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="01212-102">Hohe dpi-Unterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01212-102">High DPI support in Windows Forms</span></span>

<span data-ttu-id="01212-103">Ab .NET Framework 4,7 umfasst Windows Forms Verbesserungen für gängige Szenarien mit hoher dpi und dynamischer dpi.</span><span class="sxs-lookup"><span data-stu-id="01212-103">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="01212-104">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="01212-104">These include:</span></span>

- <span data-ttu-id="01212-105">Verbesserungen an der Skalierung und dem Layout mehrerer Windows Forms Steuerelemente, wie z. b. das <xref:System.Windows.Forms.MonthCalendar>-Steuerelement und das <xref:System.Windows.Forms.CheckedListBox>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="01212-105">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span>

- <span data-ttu-id="01212-106">Skalierung mit einem Durchlauf</span><span class="sxs-lookup"><span data-stu-id="01212-106">Single-pass scaling.</span></span>  <span data-ttu-id="01212-107">In den .NET Framework 4,6 und früheren Versionen wurde die Skalierung über mehrere Durchgänge durchgeführt, was dazu führte, dass einige Steuerelemente mehr als notwendig skaliert wurden.</span><span class="sxs-lookup"><span data-stu-id="01212-107">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="01212-108">Unterstützung für dynamische dpi-Szenarien, in denen der Benutzer den dpi-oder Skalierungsfaktor ändert, nachdem eine Windows Forms Anwendung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="01212-108">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="01212-109">In Versionen der .NET Framework ab .NET Framework 4,7 ist die erweiterte Unterstützung für hohe dpi-Funktionen eine Opt-in-Funktion.</span><span class="sxs-lookup"><span data-stu-id="01212-109">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="01212-110">Sie müssen Ihre Anwendung so konfigurieren, dass Sie von ihr genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="01212-110">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="01212-111">Konfigurieren Ihrer Windows Forms-App für hohe dpi-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="01212-111">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="01212-112">Die neuen Windows Forms Features, die ein hohes dpi-Bewusstsein unterstützen, stehen nur in Anwendungen zur Verfügung, die auf die .NET Framework 4,7 abzielen und auf Windows-Betriebssystemen mit Windows 10 Creators Update ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="01212-112">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span>

<span data-ttu-id="01212-113">Außerdem müssen Sie die folgenden Schritte ausführen, um die Unterstützung für hohe dpi-Unterstützung in Ihrer Windows Forms Anwendung zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="01212-113">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="01212-114">Deklarieren Sie Kompatibilität mit Windows 10.</span><span class="sxs-lookup"><span data-stu-id="01212-114">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="01212-115">Fügen Sie hierzu der Manifest-Datei Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="01212-115">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="01212-116">Aktivieren Sie die dpi-Informationen pro Monitor in der Datei " *app. config* ".</span><span class="sxs-lookup"><span data-stu-id="01212-116">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="01212-117">Windows Forms führt ein neues [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) Element ein, um neue Features und Anpassungen zu unterstützen, die ab dem .NET Framework 4,7 hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="01212-117">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="01212-118">Fügen Sie der Anwendungs Konfigurationsdatei Folgendes hinzu, um die neuen Features zu nutzen, die hohe dpi-Unterstützung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="01212-118">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="01212-119">In früheren Versionen der .NET Framework wurde das Manifest verwendet, um eine hohe dpi-Unterstützung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="01212-119">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="01212-120">Diese Vorgehensweise wird nicht mehr empfohlen, da Sie Einstellungen überschreibt, die in der Datei "App. config" definiert sind.</span><span class="sxs-lookup"><span data-stu-id="01212-120">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>

- <span data-ttu-id="01212-121">Ruft die statische <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode auf.</span><span class="sxs-lookup"><span data-stu-id="01212-121">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>

  <span data-ttu-id="01212-122">Dies sollte der erste Methoden aufzurufen in Ihrem Anwendungs Einstiegspunkt sein.</span><span class="sxs-lookup"><span data-stu-id="01212-122">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="01212-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="01212-123">For example:</span></span>

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="01212-124">Deaktivieren einzelner hoher dpi-Features</span><span class="sxs-lookup"><span data-stu-id="01212-124">Opting out of individual high DPI features</span></span>

<span data-ttu-id="01212-125">Wenn Sie den `DpiAwareness` Wert auf `PerMonitorV2` festlegen, werden alle hohen dpi-Funktionen aktiviert, die von .NET Framework Versionen ab dem .NET Framework 4,7 unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="01212-125">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="01212-126">Dies ist in der Regel für die meisten Windows Forms Anwendungen ausreichend.</span><span class="sxs-lookup"><span data-stu-id="01212-126">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="01212-127">Möglicherweise möchten Sie jedoch eine oder mehrere einzelne Features ablehnen.</span><span class="sxs-lookup"><span data-stu-id="01212-127">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="01212-128">Der wichtigste Grund hierfür ist, dass Ihr vorhandener Anwendungscode diese Funktion bereits behandelt.</span><span class="sxs-lookup"><span data-stu-id="01212-128">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="01212-129">Wenn Ihre Anwendung z. b. die automatische Skalierung verarbeitet, empfiehlt es sich, das Feature für die automatische Anpassung der Größe wie folgt zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="01212-129">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

<span data-ttu-id="01212-130">Eine Liste der einzelnen Schlüssel und deren Werte finden Sie unter [Windows Forms Add Configuration-Elements](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span><span class="sxs-lookup"><span data-stu-id="01212-130">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="01212-131">Neue dpi-Änderungs Ereignisse</span><span class="sxs-lookup"><span data-stu-id="01212-131">New DPI change events</span></span>

<span data-ttu-id="01212-132">Beginnend mit dem .NET Framework 4,7 können Sie mithilfe von drei neuen Ereignissen dynamische dpi-Änderungen Programm gesteuert behandeln:</span><span class="sxs-lookup"><span data-stu-id="01212-132">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="01212-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, das ausgelöst wird, wenn die dpi-Einstellung für ein Steuerelement Programm gesteuert geändert wird, nachdem ein dpi-Änderungs Ereignis für das übergeordnete Steuerelement oder Formular aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="01212-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="01212-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, das ausgelöst wird, wenn die dpi-Einstellung für ein Steuerelement Programm gesteuert geändert wird, bevor ein dpi-Änderungs Ereignis für das übergeordnete Steuerelement oder Formular aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="01212-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="01212-135"><xref:System.Windows.Forms.Form.DpiChanged>, das ausgelöst wird, wenn die dpi-Einstellung auf dem Anzeigegerät geändert wird, auf dem das Formular derzeit angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="01212-135"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="01212-136">Neue Hilfsmethoden und-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="01212-136">New helper methods and properties</span></span>

<span data-ttu-id="01212-137">Der .NET Framework 4,7 fügt auch eine Reihe neuer Hilfsmethoden und-Eigenschaften hinzu, die Informationen zur DPI-Skalierung bereitstellen und Ihnen die Durchführung der DPI-Skalierung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="01212-137">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="01212-138">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="01212-138">These include:</span></span>

- <span data-ttu-id="01212-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, der einen Wert von "logisch" in "Geräte Pixel" konvertiert.</span><span class="sxs-lookup"><span data-stu-id="01212-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="01212-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, das ein Bitmap-Bild auf den logischen dpi-Wert für ein Gerät skaliert.</span><span class="sxs-lookup"><span data-stu-id="01212-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="01212-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, die den dpi-Wert für das aktuelle Gerät zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="01212-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="01212-142">Überlegungen zur Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="01212-142">Versioning considerations</span></span>

<span data-ttu-id="01212-143">Neben der Ausführung auf .NET Framework 4,7-und Windows 10 Creators Update kann die Anwendung auch in einer Umgebung ausgeführt werden, in der Sie nicht mit hohen dpi-Verbesserungen kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="01212-143">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="01212-144">In diesem Fall müssen Sie ein Fall Back für Ihre Anwendung entwickeln.</span><span class="sxs-lookup"><span data-stu-id="01212-144">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="01212-145">Hierfür können Sie eine [benutzerdefinierte Zeichnung](./controls/user-drawn-controls.md) zum Verarbeiten der Skalierung durchführen.</span><span class="sxs-lookup"><span data-stu-id="01212-145">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="01212-146">Zu diesem Zweck müssen Sie auch das Betriebssystem bestimmen, unter dem Ihre APP ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="01212-146">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="01212-147">Hierfür können Sie Code wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="01212-147">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="01212-148">Beachten Sie, dass Ihre Anwendung Windows 10 nicht erfolgreich erkennt, wenn Sie nicht als unterstütztes Betriebssystem im Anwendungs Manifest aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="01212-148">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="01212-149">Sie können auch die Version der .NET Framework überprüfen, für die die Anwendung erstellt wurde:</span><span class="sxs-lookup"><span data-stu-id="01212-149">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="01212-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01212-150">See also</span></span>

- [<span data-ttu-id="01212-151">Konfigurations Element Windows Forms hinzufügen</span><span class="sxs-lookup"><span data-stu-id="01212-151">Windows Forms Add Configuration Element</span></span>](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [<span data-ttu-id="01212-152">Anpassen der Größe und Skalieren von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01212-152">Adjusting the Size and Scale of Windows Forms</span></span>](adjusting-the-size-and-scale-of-windows-forms.md)
